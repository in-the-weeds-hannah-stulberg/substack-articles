# Article Frontmatter Schema

Canonical YAML frontmatter for every `article.md` in this repo. Every article must use this shape exactly. The `add-substack-article-to-repo` skill emits this shape automatically; this doc is the source of truth when the skill or a human is unsure.

## Canonical block

```yaml
---
title: "<Title>"
subtitle: "<Subtitle>"
authors:
  - name: "Hannah Stulberg"
    publication:
      name: "In the Weeds"
      url: "https://hannahstulberg.substack.com/"
  - name: "<Co-author>"
    publication:
      name: "<Their Pub>"
      url: "<https://...>"
published: YYYY-MM-DD
series: "Claude Code for Everything"   # OMIT for standalone
series_number: 8                       # OMIT for standalone
original_url: "https://..."            # canonical Substack/blog URL of the published post
license: "CC BY-NC 4.0"
media:                                 # OMIT unless real podcast/video companion exists
  spotify: "https://..."
  apple:   "https://..."
  youtube: "https://..."
---
```

## Field rules

- **`title`** — full article title with series prefix where applicable (e.g., `"Tool School: Benchmarking 101..."`).
- **`subtitle`** — one line. No surrounding asterisks or italics — markdown lives in the body, not the frontmatter.
- **`authors`** — ordered list. First entry is the lead author (the person whose publication owns the original post). Each entry has `name` and `publication`.
- **`authors[].publication`** — object with `name` (display label) and `url` (publication homepage). Use the canonical URL per author × publication pair (see table below). Don't add `links:`, `role:`, or any other sub-keys.
- **`published`** — ISO date `YYYY-MM-DD`. Date the post went live (or planned publish date for unpublished articles).
- **`series`** — string (e.g., `"Claude Code for Everything"`, `"Tool School"`). Omit the field entirely for standalone articles. Don't write `series: null`.
- **`series_number`** — integer. Same rule as `series` — omit for standalones.
- **`original_url`** — the canonical Substack/blog URL of the post. For unpublished articles, use the planned URL once known; otherwise empty string.
- **`license`** — always `"CC BY-NC 4.0"` unless explicitly overridden.
- **`media`** — optional object. Only include when the article has a real companion podcast/video. Flat keys: `spotify`, `apple`, `youtube`. Omit any platform that doesn't have a published companion. Omit the entire `media:` block if no media exists.

## Canonical author → publication URL mapping

One canonical URL per (author, publication) pair. If the same author writes for a different publication, use that publication's URL there.

| Author | Publication | URL |
|---|---|---|
| Hannah Stulberg | In the Weeds | https://hannahstulberg.substack.com/ |
| Joel Salinas | Leadership in Change | https://leadershipinchange.com/ |
| Sidwyn Koh | Path to Staff | https://www.pathtostaff.com/ |
| Akshat Khandelwal | Help Me Unpack | https://helpmeunpack.substack.com/ |
| Aakash Gupta | Product Growth | https://www.news.aakashg.com/ |

## Why no `links` block, no `role` field

Earlier versions of the schema embedded `authors[].links.{substack,linkedin,youtube,github,website}` and `authors[].role`. Both got removed:

- **`links` was dead metadata.** Nothing in the repo, the skills, or any external script reads it. Bio links live in [`CONTRIBUTORS.md`](../CONTRIBUTORS.md), which is the actual source of truth. Duplicating them in every article frontmatter created drift risk and added zero value.
- **`role` strings were inconsistent and unused.** Across 4 co-authored articles, the same concept showed up as "author", "Author", "Guest contributor", "Collaborator", "Co-author", and "guest". No reader, no standard. The order of `authors[]` already conveys lead vs. co-author.
- **Unconditional `links.youtube` was lying.** It pointed at Hannah's YouTube channel even on articles with no companion video. Misleading metadata is worse than missing metadata.

If a future need surfaces (e.g., generating an authors page), reach for `CONTRIBUTORS.md` first. Don't reintroduce `links` here.

## Canonical examples

- **Single-author + media:** `claude-code-for-everything/01-finally-that-personal-assistant-youve-always-wanted/article.md`
- **Single-author no media:** `claude-code-for-everything/02-how-the-guy-who-built-it-actually-uses-it/article.md`
- **Co-authored standalone (no series, no media):** `standalone/business-sense-for-engineers/article.md`
- **Co-authored series article:** `claude-code-for-everything/06-the-one-file-that-can-save-your-team-thousands-of-hours/article.md`
- **Co-authored + full media block:** `standalone/build-a-team-os-with-claude-code/article.md`

## Who writes this

The [`add-substack-article-to-repo`](skills/add-substack-article-to-repo/SKILL.md) skill emits this shape automatically when mirroring a Substack post into the repo (Stage 4 sanitize). When that skill changes, update this doc and the skill in the same commit.
