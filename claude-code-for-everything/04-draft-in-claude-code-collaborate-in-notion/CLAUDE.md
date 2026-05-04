# Claude Code for Everything: Draft in Claude Code, Collaborate in Notion

**Author:** Hannah Stulberg | **Published:** 2026-01-27

## Article Map

| Section | Line | Coverage | Substack |
|---------|------|----------|----------|
| Title & intro | 18 | The collaboration gap: drafting in Claude Code vs sharing with teams | [Link](https://hannahstulberg.substack.com/p/claude-code-for-everything-draft-in-claude-code-collaborate-in-notion) |
| By the end of this article, you'll have | 42 | Learning objectives | [Link](https://hannahstulberg.substack.com/i/184213725/by-the-end-of-this-article-youll-have) |
| What you need before starting | 56 | Prerequisites: Claude Code running, Notion account | [Link](https://hannahstulberg.substack.com/i/184213725/what-you-need-before-starting) |
| How Claude Code talks to Notion | 62 | MCP explained; what the Notion connection enables | [Link](https://hannahstulberg.substack.com/i/184213725/how-claude-code-talks-to-notion) |
| Setting Up Notion MCP | 84 | Full setup walkthrough | [Link](https://hannahstulberg.substack.com/i/184213725/setting-up-notion-mcp) |
| Step 0: Make sure Claude Code is running | 94 | Prerequisite check | [Link](https://hannahstulberg.substack.com/i/184213725/setting-up-notion-mcp) |
| Step 1: Add the Notion MCP server | 98 | Adding MCP; global vs project-level | [Link](https://hannahstulberg.substack.com/i/184213725/setting-up-notion-mcp) |
| Step 2: Restart Claude Code | 110 | Why restart is needed | [Link](https://hannahstulberg.substack.com/i/184213725/setting-up-notion-mcp) |
| Step 3: Authenticate with Notion | 114 | /mcp command, OAuth flow | [Link](https://hannahstulberg.substack.com/i/184213725/setting-up-notion-mcp) |
| Step 4: Verify it's working | 122 | Testing the connection | [Link](https://hannahstulberg.substack.com/i/184213725/setting-up-notion-mcp) |
| If you need to re-authenticate later | 130 | Fixing expired connections | [Link](https://hannahstulberg.substack.com/i/184213725/setting-up-notion-mcp) |
| Setting Up Your Notion Workspace | 148 | Creating a database to track synced documents | [Link](https://hannahstulberg.substack.com/i/184213725/setting-up-your-notion-workspace) |
| The Sync Workflow: Sending Documents to and from Notion | 170 | Overview of sync operations | [Link](https://hannahstulberg.substack.com/i/184213725/the-sync-workflow-sending-documents-to-and-from-notion) |
| Creating New Documents | 172 | First-time push to Notion | [Link](https://hannahstulberg.substack.com/i/184213725/the-sync-workflow-sending-documents-to-and-from-notion) |
| Updating Existing Documents | 190 | Targeted updates to avoid overwriting | [Link](https://hannahstulberg.substack.com/i/184213725/the-sync-workflow-sending-documents-to-and-from-notion) |
| Pulling edits from Notion to Claude Code | 198 | Compare-then-pull workflow | [Link](https://hannahstulberg.substack.com/i/184213725/the-sync-workflow-sending-documents-to-and-from-notion) |
| Pushing edits from Claude Code to Notion | 206 | Compare-then-push workflow | [Link](https://hannahstulberg.substack.com/i/184213725/the-sync-workflow-sending-documents-to-and-from-notion) |
| Handling conflicts: changes on both sides | 214 | Conflict detection and resolution strategies | [Link](https://hannahstulberg.substack.com/i/184213725/the-sync-workflow-sending-documents-to-and-from-notion) |
| A note on comments | 238 | Page comments vs in-line comments; MCP limitation | [Link](https://hannahstulberg.substack.com/i/184213725/the-sync-workflow-sending-documents-to-and-from-notion) |
| Making It One Step: Custom Commands | 254 | Creating /push-to-notion and /pull-from-notion | [Link](https://hannahstulberg.substack.com/i/184213725/making-it-one-step-custom-commands) |
| Why I'm showing you my commands (but you shouldn't copy them) | 266 | Teaching fundamentals over magic configs | [Link](https://hannahstulberg.substack.com/i/184213725/making-it-one-step-custom-commands) |
| My Push Command (/push-to-notion) | 276 | Full push command spec | [Link](https://hannahstulberg.substack.com/i/184213725/making-it-one-step-custom-commands) |
| Push to Notion (command body) | 286 | Process: read, search, create-or-update, confirm | [Link](https://hannahstulberg.substack.com/i/184213725/making-it-one-step-custom-commands) |
| My Pull Command (/pull-from-notion) | 326 | Full pull command spec | [Link](https://hannahstulberg.substack.com/i/184213725/making-it-one-step-custom-commands) |
| Pull from Notion (command body) | 336 | Process: search, fetch, compare, update local | [Link](https://hannahstulberg.substack.com/i/184213725/making-it-one-step-custom-commands) |
| Now go review the commands Claude made for you | 377 | Checklist for validating custom commands | [Link](https://hannahstulberg.substack.com/i/184213725/making-it-one-step-custom-commands) |
| Document Your Setup | 395 | Adding Notion config to CLAUDE.md for persistence | [Link](https://hannahstulberg.substack.com/i/184213725/document-your-setup) |
| Notion Sync (CLAUDE.md example) | 408 | Example CLAUDE.md documentation block | [Link](https://hannahstulberg.substack.com/i/184213725/document-your-setup) |
| When to Use This Workflow | 432 | Best use cases and when NOT to use it | — |
| Bonus: Pulling Context from Notion | 450 | Using Notion as a context source for Claude Code | — |
| What You Should Have Now | 458 | Recap of capabilities | [Link](https://hannahstulberg.substack.com/i/184213725/what-you-should-have-now) |
| Next Steps | 476 | Start with low-stakes docs; iterate on setup | [Link](https://hannahstulberg.substack.com/i/184213725/next-steps) |
