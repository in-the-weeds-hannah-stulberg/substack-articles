---
name: add-substack-article-to-repo
description: Mirror a Substack article into the In the Weeds public learning repo at `~/in-the-weeds-substack-articles/`. Handles two source modes - local (slug from `~/hannah-personal-agent/`) and firecrawl (URL from any Substack-hosted post). Copies article + images, generates the article-level CLAUDE.md, cascades index updates across root CLAUDE.md, series CLAUDE.md, welcome.md, CONTRIBUTORS.md, and LICENSE, then opens a clean PR. Use this skill whenever Hannah says "add this article to in-the-weeds", "publish [slug] to the repo", "mirror [URL] into the learning repo", "add the [slug] article", or runs /add-substack-article-to-repo. Also use when she pastes a Substack URL (https://...substack.com/p/... or any /p/ pattern) and asks to bring it into the repo.
---

# Add Substack Article To Repo

End-to-end skill for getting a Substack article into the public learning repo `/Users/hannahstulberg/in-the-weeds-substack-articles/`. Covers everything from source discovery to a clean PR.

## When the skill triggers

Hannah just published an In the Weeds article (or wants to add an external article by a collaborator) and needs to mirror it into the public repo so the AI learning assistant can teach from it. Two patterns:

- She says a slug like `add the curiosity-is-the-only-prerequisite article to the repo` — assume the source is local under `~/hannah-personal-agent/`.
- She pastes a URL like `add this article: https://www.pathtostaff.com/p/business-sense-for-engineers-the` — assume the source is the live Substack post and use firecrawl-cli to scrape it.

## Mode selection (Stage 0)

Inspect the input:
- Matches `^https?://` → **firecrawl mode**. Load `references/source-mode-firecrawl.md`. Derive slug from the last `/p/<slug>` segment of the URL.
- Otherwise → **local mode**. Load `references/source-mode-local.md`. Treat input as the slug.

Hannah can override: "use firecrawl on <url>" forces firecrawl, "fetch from local <slug>" forces local.

Write `/tmp/add-substack-article-<slug>.json`:
```json
{"state": "mode_selected", "mode": "local|firecrawl", "input": "<input>", "slug": "<slug>"}
```

## Workflow (after mode selection)

The two source modes diverge at Stages 1–2 (discovery + metadata read), then re-converge from Stage 3 onward. Mode-specific reference files spell out Stages 1–2 in detail; Stages 3–8 below apply to both modes (Stage 7 is firecrawl-only, but Stage 8 still gates on it).

### Stage 3 — Determine target paths

Read the live repo structure at runtime — do NOT assume a snapshot. Source of truth is the repo's root CLAUDE.md (`/Users/hannahstulberg/in-the-weeds-substack-articles/CLAUDE.md`).

Series → target folder mapping (current):
- `Standalone` → `standalone/<slug>/`
- `Claude Code for Everything` → `claude-code-for-everything/<NN>-<slug>/` where `NN` = next zero-padded number
- `Tool School` → `tool-school/<NN>-<slug>/`

To find `<NN>`: `ls` the series folder, find highest existing `<NN>-` prefix, add 1, zero-pad to 2 digits.

If the root CLAUDE.md describes a series that isn't in the table above, follow whatever convention root CLAUDE.md documents — the live file always wins over this skill's defaults.

Compute:
- `target_folder = <series-folder>/<slug>/` (Standalone) or `<series-folder>/<NN>-<slug>/`
- `target_article = <target-folder>/article.md`
- `target_claude_md = <target-folder>/CLAUDE.md`
- `target_images = <target-folder>/images/`

### Stage 4 — Branch + copy

Sequential — branch must exist before any writes.

```bash
git pull origin main
git checkout -b add/<slug>
mkdir -p <target-folder>/images
```

**Local mode:**
```bash
cp <source-article-md> <target-folder>/article.md
[ -d <source-images> ] && cp -r <source-images>/* <target-folder>/images/
```

**Firecrawl mode:**
```bash
mv .firecrawl/<slug>/<scraped>.md <target-folder>/article.md
# For each image URL in the scraped content, download to images/
# Then rewrite article body so image refs point at images/<filename>
```

Update temp file: `{"state": "files_copied", "branch": "add/<slug>", "files": [...]}`.

### Stage 5 — Generate article-level CLAUDE.md

Format MUST match the existing repo pattern. Two canonical examples Claude can read for reference:
- `standalone/stop-typing-start-talking/CLAUDE.md` (4-column with all rows filled with Substack links)
- `claude-code-for-everything/05-claudemd-files/CLAUDE.md` (4-column with mixed `[Link]` and `—` rows)

Required output structure:

```markdown
# <Article Title>

**Author:** <names> | **Published:** <YYYY-MM-DD>

## Article Map

| Section | Line | Coverage | Substack |
|---------|------|----------|----------|
| <heading> | <line> | <coverage> | — |
| ... | ... | ... | ... |
```

Notes:
- For featured-contributor articles (e.g., Aakash's Team OS): `**Author:** Aakash Gupta (featuring Hannah Stulberg) | **Published:** ...`.
- One row per H2 (`^## `) and H3 (`^### `) heading. H1 is the title (already in the file header), don't include it in the map.
- `Line` = `grep -n "^## \|^### " <target>/article.md` returns the line numbers.
- `Coverage` = a 1-phrase summary auto-drafted by reading 2-3 lines after each heading. Keep under 15 words. No filler.
- `Substack` = `—` for every row in local mode. In firecrawl mode, Stage 7 replaces these with verified URLs.

### Stage 6 — Cascade updates

Batch ALL of these edits in ONE message (independent files). Read the live root CLAUDE.md first to identify exact insertion points; do not assume line numbers.

**1. Root `CLAUDE.md` — Article index table**

Insert one new row in the article index. Format mirrors existing rows:
```
| <#> | <Title> | <Series> | <Author(s)> | <key topics, comma-separated> | `<path>` |
```

`<#>` = next sequential article number across the whole repo (count existing rows + 1).

**2. Root `CLAUDE.md` — Topic quick lookup table**

Auto-draft topic entries by reading the article's H2/H3 headings. For each meaningful heading (skip purely decorative ones like "Title & subtitle"), insert:
```
| <Topic phrase> | <Article short name> | <Section heading> |
```

Insert at the bottom of the existing Topic quick lookup table. Don't try to alphabetize — append.

**3. Root `CLAUDE.md` — Key metaphors table**

Only add rows IF the article uses an explicit metaphor pattern. Heuristic: scan the article body for phrases like:
- `is like a <noun>`
- `the <noun> metaphor`
- `think of it like <noun>`
- `imagine a <noun>`

If found, draft a row:
```
| **<Metaphor name>** | <What it represents> | <Article name>, "<Section>" |
```

If no clear metaphor, skip this entirely. Don't force it.

**4. Root `CLAUDE.md` — About / Contributors list**

Inside the "About" section near the bottom, the contributor bullet list. If the article introduces a NEW contributor (one not already listed), add:
```
- [<Full Name>](<their-url>) - <Role>, <Article title>
```

If the contributor is already listed, no edit here.

**5. Series-level `CLAUDE.md`**

Pick the right one based on series:
- `standalone/CLAUDE.md`
- `claude-code-for-everything/CLAUDE.md`
- `tool-school/CLAUDE.md`

Insert one new row in the series articles table. Format mirrors existing rows in that file (read the live file for the exact column schema).

**6. `.claude/welcome.md`**

Two edits:
- Bump the article count number by 1 (currently says "12 published articles" or similar — find and increment).
- If new contributor: add their name to the credit list line. Format follows existing pattern.

**7. `CONTRIBUTORS.md`**

Only edit if the article introduces a NEW contributor. Append a new bio block following the existing pattern:
```
## <Full Name>

<1-2 sentence bio>

- [<Publication> (<Substack/blog>)](<url>)
- [LinkedIn](<linkedin-url>)
- [<Other relevant link>](<url>)

**Articles in this repo:** <Article title> (<role: co-author / collaborator / author featuring Hannah>)
```

If the bio info isn't available from the source metadata, draft a stub like `<TODO: bio>` and surface it in the PR body for Hannah to fill before merging.

For repeat contributors: update their existing bio block's `**Articles in this repo:**` line to include the new article. Don't add a new bio block.

**8. `LICENSE`**

Add per-article copyright entry under "Individual Article Attribution:" based on relationship.

| Relationship | Template |
|---|---|
| Hannah + co-author (e.g., GitHub 101 with Sidwyn) | `"<Title>"`<br>`Copyright (c) <year> Hannah Stulberg and <Co-author Name>`<br>`Co-authored. Included with co-author's permission.` |
| Hannah + collaborator originally elsewhere (e.g., Joel) | `"<Title>"`<br>`Copyright (c) <year> Hannah Stulberg and <Name>`<br>`Originally published on <Publication>. Included with permission.` |
| External author featuring Hannah (e.g., Aakash) | `"<Title>"`<br>`Copyright (c) <year> Hannah Stulberg`<br>`Written by <Name> (<Publication>), based on Hannah Stulberg's original content and expertise.`<br>`Originally published on <Publication>. Included with permission.` |
| Hannah only | No LICENSE entry — covered by the catch-all "All other articles" line. |

For repeat contributors (e.g., Sidwyn already has GitHub 101 entry, now adding a second article): add a brand-NEW entry for the new article. Each article gets its own copyright line. Don't consolidate or modify the existing entry.

If the relationship is ambiguous, draft the most permissive template (`Co-authored`) and call it out in the PR body for Hannah to refine before merging.

After all edits: `{"state": "cascade_done", "files_modified": [...]}` in temp file.

### Stage 7 — Substack URL backfill (firecrawl mode ONLY)

Skip this stage entirely in local mode (post may not be live yet — Hannah will run the companion skill later). In local mode, write `{"substack_backfill": {"skipped": true, "reason": "local mode"}}` to the temp file so the Stage 8 pre-commit gate knows it wasn't forgotten.

In firecrawl mode the live URL is the input — fill the per-row `Substack` column inline before commit. **This stage is mandatory in firecrawl mode. Skipping it ships a CLAUDE.md with `—` placeholders that should have been real anchor URLs.**

Invoke the companion skill via an explicit Skill tool call (not prose intent — actually call it):

```
Skill(skill="add-substack-urls-to-article", args="slug=<slug> url=<input-url> subroutine=true")
```

The companion runs Stages 0–3 (resolve target → fetch post → match headings → edit CLAUDE.md) but skips its own branch/commit/push/PR. All edits stay on the same `add/<slug>` branch.

After the companion returns, write to temp file:
```json
{"substack_backfill": {"rows_filled": N, "rows_left_as_dash": M, "skipped": false}}
```

If companion fails (404, anchor map empty, etc.), write:
```json
{"substack_backfill": {"skipped": false, "failed": true, "error": "<reason>", "rows_left_as_dash": <total>}}
```
Then continue to Stage 8 — Hannah can re-run the companion skill manually later. Don't abort the pipeline.

### Stage 8 — Pre-commit gate + commit + push + PR

**Pre-commit gate (MANDATORY before `git add`):**

1. Read the temp file. Confirm `substack_backfill` key exists. If missing in firecrawl mode → ABORT with: `"Stage 7 not run. Invoke /add-substack-urls-to-article before proceeding."`
2. Grep the target article-level `CLAUDE.md` for unfilled rows: `grep -c '| —$' <target>/CLAUDE.md`. In firecrawl mode, if any non-intro rows are still `—` AND `substack_backfill.skipped == false` AND `substack_backfill.failed != true` → ABORT with the row count and the message: `"Stage 7 ran but rows still empty. Re-check companion output."`
3. Only proceed to `git add` once the gate passes.

Then sequential:

```bash
git add <specific-files>  # never use -A or .
git commit -m "Add new article to repo"
git push -u origin add/<slug>
gh pr create --title "Add new article to repo" --body "<body>"
```

Sequential:

```bash
git add <specific-files>  # never use -A or .
git commit -m "Add new article to repo"
git push -u origin add/<slug>
gh pr create --title "Add new article to repo" --body "<body>"
```

Public-repo rules apply (per `commit-push-pr` conventions):
- Title ≤70 chars, vanilla, no article name / series number / contributor name.
- Body: 1-2 sentences. Don't list the article title, series number, or any specifics. List counts only ("8 files updated", "1 new contributor added").

If LICENSE was updated with a "draft template" (ambiguous relationship), call that out in the PR body so Hannah refines before merging.

If Stage 7 fired but had partial failures, list count of unfilled rows in PR body.

Final temp file: `{"state": "done", "pr_url": "..."}`.

## Crash recovery

Single temp file: `/tmp/add-substack-article-<slug>.json`. Updated after every stage. Schema:

```json
{
  "state": "mode_selected | source_found | metadata_read | files_copied | article_claude_md_generated | cascade_done | substack_backfill_done | committed | pushed | done",
  "slug": "<slug>",
  "mode": "local | firecrawl",
  "input": "<original input>",
  "source_path": "/abs/path",
  "source_article_md": "/abs/path",
  "title": "<title>",
  "series": "Standalone | Claude Code for Everything | Tool School",
  "series_number": 8,
  "target_folder": "/abs/path",
  "target_files_to_modify": ["/abs/path/...", ...],
  "contributors": ["..."],
  "new_contributors_added": ["..."],
  "branch": "add/<slug>",
  "commit_sha": "...",
  "pr_url": "...",
  "substack_backfill": {"rows_filled": N, "rows_left_as_dash": M}
}
```

A fresh session can read this file and resume from the last completed stage. On resumption: read the temp file first, check current branch + git state, jump to the next stage past `state`. Don't redo completed stages (e.g., don't re-copy files if `state >= "files_copied"`).

## Source-of-truth rules

- **Title, series, date, contributors [local mode]:** read from source `CLAUDE.md` first (`<source>/CLAUDE.md`), `manifest.yaml` fallback. If both missing, ask user.
- **Title, date, author [firecrawl mode]:** extract from scraped markdown (H1 + byline + date). Ask user only for the field that fails extraction, not all three.
- **Slug [local mode]:** strip `[DD-MM-YYYY]-` date prefix from published folder names; otherwise use the unpublished folder name as-is.
- **Slug [firecrawl mode]:** the last `/p/<slug>` segment of the URL.
- **Series [local mode]:** as specified in source CLAUDE.md / manifest.yaml.
- **Series [firecrawl mode]:** default to `Standalone` for external posts. User can override at invocation.
- **Article number in series:** scan target repo's series folder for highest `<NN>-` prefix; new = highest + 1, zero-padded. Standalone has no number prefix.
- **Substack column:** `—` in local mode. Filled inline by Stage 7 in firecrawl mode.
- **Topic + metaphor entries:** auto-draft, no pause. Hannah reviews in the PR.

## Things this skill must NOT do

- Don't ask the user mid-run for topic / metaphor / coverage entries. Auto-draft, ship to PR, let Hannah edit there.
- Don't `git add -A` or `git add .`. Always specific files.
- Don't put article titles, series numbers, or contributor names in the commit message or PR title (public repo).
- Don't overwrite an existing target folder. If `<target-folder>` already exists, abort with a clear message naming the collision.
- Don't proceed if the source can't be located. Ask user; don't guess.
- Don't fabricate a Substack URL. In local mode, leave column as `—`. Only firecrawl mode (where URL is the input) fills it.

## References

- `references/source-mode-local.md` — loaded only when input is a slug. Personal-agent folder discovery, source CLAUDE.md / manifest.yaml metadata extraction, version-suffix selection (prefer `-final.md`, else highest `-v<N>.md`).
- `references/source-mode-firecrawl.md` — loaded only when input is a URL. Firecrawl CLI invocation per `~/.claude/docs/firecrawl.md`, scrape format expectations, image download + rewriting, metadata extraction from scraped content.
