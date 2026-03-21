# Claude Code for Everything: Draft in Claude Code, Collaborate in Notion

**Author:** Hannah Stulberg | **Published:** 2026-01-27

## Article Map

| Section | Line | Coverage |
|---------|------|----------|
| Title & intro | 18 | The collaboration gap: drafting in Claude Code vs sharing with teams |
| By the end of this article, you'll have | 42 | Learning objectives |
| What you need before starting | 56 | Prerequisites: Claude Code running, Notion account |
| How Claude Code talks to Notion | 62 | MCP explained; what the Notion connection enables |
| Setting Up Notion MCP | 84 | Full setup walkthrough |
| Step 0: Make sure Claude Code is running | 94 | Prerequisite check |
| Step 1: Add the Notion MCP server | 98 | Adding MCP; global vs project-level |
| Step 2: Restart Claude Code | 110 | Why restart is needed |
| Step 3: Authenticate with Notion | 114 | /mcp command, OAuth flow |
| Step 4: Verify it's working | 122 | Testing the connection |
| If you need to re-authenticate later | 130 | Fixing expired connections |
| Setting Up Your Notion Workspace | 148 | Creating a database to track synced documents |
| The Sync Workflow: Sending Documents to and from Notion | 170 | Overview of sync operations |
| Creating New Documents | 172 | First-time push to Notion |
| Updating Existing Documents | 190 | Targeted updates to avoid overwriting |
| Pulling edits from Notion to Claude Code | 198 | Compare-then-pull workflow |
| Pushing edits from Claude Code to Notion | 206 | Compare-then-push workflow |
| Handling conflicts: changes on both sides | 214 | Conflict detection and resolution strategies |
| A note on comments | 238 | Page comments vs in-line comments; MCP limitation |
| Making It One Step: Custom Commands | 254 | Creating /push-to-notion and /pull-from-notion |
| Why I'm showing you my commands (but you shouldn't copy them) | 266 | Teaching fundamentals over magic configs |
| My Push Command (/push-to-notion) | 276 | Full push command spec |
| Push to Notion (command body) | 286 | Process: read, search, create-or-update, confirm |
| My Pull Command (/pull-from-notion) | 326 | Full pull command spec |
| Pull from Notion (command body) | 336 | Process: search, fetch, compare, update local |
| Now go review the commands Claude made for you | 377 | Checklist for validating custom commands |
| Document Your Setup | 395 | Adding Notion config to CLAUDE.md for persistence |
| Notion Sync (CLAUDE.md example) | 408 | Example CLAUDE.md documentation block |
| When to Use This Workflow | 432 | Best use cases and when NOT to use it |
| Bonus: Pulling Context from Notion | 450 | Using Notion as a context source for Claude Code |
| What You Should Have Now | 458 | Recap of capabilities |
| Next Steps | 476 | Start with low-stakes docs; iterate on setup |
