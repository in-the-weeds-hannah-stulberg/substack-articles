# Claude Code for Everything: The Best Personal Assistant Remembers Things About You (A CLAUDE.md Deep Dive)

**Author:** Hannah Stulberg | **Published:** 2026-02-14

## Article Map

| Section | Line | Coverage | Substack |
|---------|------|----------|----------|
| Title & Subtitle | 18 | How CLAUDE.md files give Claude context automatically every session | [Link](https://hannahstulberg.substack.com/p/claude-code-for-everything-the-best-personal-assistant-remembers-everything-about-you) |
| By the end of this article, you'll have | 54 | Learning objectives: understanding, folder structure, framework, writing methods, first file | — |
| Prefer to watch? | 72 | Link to video walkthrough | — |
| Quick Refresher: Context 101 | 76 | Context window basics, thinking room trade-off, why more context isn't always better | [Link](https://hannahstulberg.substack.com/i/187471997/quick-refresher-context-101) |
| What CLAUDE.md Files Are (and How They Work) | 96 | Plain text markdown files as onboarding guides; Sarah at Acme example | [Link](https://hannahstulberg.substack.com/i/187471997/what-claudemd-files-are-and-how-they-work) |
| The CLAUDE.md How-To | 156 | Overview of four setup steps: folders, content, writing methods, maintenance | [Link](https://hannahstulberg.substack.com/i/187471997/the-claudemd-how-to) |
| The short version | 172 | Four-step summary: organize folders, create files, let Claude write them, keep lean | [Link](https://hannahstulberg.substack.com/i/187471997/the-short-version) |
| The deep dive | 190 | Full explanation of each step | [Link](https://hannahstulberg.substack.com/i/187471997/the-deep-dive) |
| 1. Your folders control what Claude knows | 192 | Folder structure as foundation; Level 0-3 hierarchy; rule of thumb for when to create files | [Link](https://hannahstulberg.substack.com/i/187471997/your-folders-control-what-claude-knows) |
| 2. What actually belongs in a CLAUDE.md file | 250 | Four types of content; length guidelines; 150-instruction limit | [Link](https://hannahstulberg.substack.com/i/187471997/what-actually-belongs-in-a-claudemd-file) |
| 2a. A document index | 274 | Map of what's where; @ imports for reuse; modularity benefits | [Link](https://hannahstulberg.substack.com/i/187471997/what-actually-belongs-in-a-claudemd-file) |
| 2b. The people involved | 290 | Names, roles, and what they do at the relevant level | [Link](https://hannahstulberg.substack.com/i/187471997/what-actually-belongs-in-a-claudemd-file) |
| 2c. What this is about | 294 | Identity, goals, key facts for useful background | [Link](https://hannahstulberg.substack.com/i/187471997/what-actually-belongs-in-a-claudemd-file) |
| 2d. How you want things done | 298 | Workflows, processes, preferences, guardrails, constraints | [Link](https://hannahstulberg.substack.com/i/187471997/what-actually-belongs-in-a-claudemd-file) |
| 3. How to write CLAUDE.md files | 322 | Three methods overview; filename must be all-caps CLAUDE.md | [Link](https://hannahstulberg.substack.com/i/187471997/how-to-write-claudemd-files) |
| Method 1: Plan mode interview | 336 | When context is in your head; Claude interviews you; dictation tip | [Link](https://hannahstulberg.substack.com/i/187471997/how-to-write-claudemd-files) |
| Method 2: Load the docs, then generate | 352 | When existing documents are available; save docs then generate | [Link](https://hannahstulberg.substack.com/i/187471997/how-to-write-claudemd-files) |
| Method 3: Generate from a session | 368 | Capture context at end of working session; best for new projects | [Link](https://hannahstulberg.substack.com/i/187471997/how-to-write-claudemd-files) |
| 4. Keeping CLAUDE.md files lean over time | 394 | Maintenance habits; signs a file needs trimming; when CLAUDE.md updates take effect | [Link](https://hannahstulberg.substack.com/i/187471997/keeping-claudemd-files-lean-over-time) |
| What this looks like in practice (reference examples) | 436 | Sarah's complete CLAUDE.md files at every level with annotations | [Link](https://hannahstulberg.substack.com/i/187471997/what-this-looks-like-in-practice-reference-examples) |
| Level 0: ~/ CLAUDE.md (Sarah's preferences) | 442 | Personal working style; portable across jobs | [Link](https://hannahstulberg.substack.com/i/187471997/what-this-looks-like-in-practice-reference-examples) |
| Level 1: ~/Acme/ CLAUDE.md (Company context) | 446 | Company, role, team, folder structure, connected tools | [Link](https://hannahstulberg.substack.com/i/187471997/what-this-looks-like-in-practice-reference-examples) |
| Level 2: ~/Acme/Marketing/ CLAUDE.md (Area context) | 450 | Brand voice, target audience, team, document index, workflows | [Link](https://hannahstulberg.substack.com/i/187471997/what-this-looks-like-in-practice-reference-examples) |
| Level 3: ~/Acme/Marketing/Q1 Campaign/ CLAUDE.md (Project context) | 454 | Messaging, product context, campaign team; most specific level | [Link](https://hannahstulberg.substack.com/i/187471997/what-this-looks-like-in-practice-reference-examples) |
| Putting it all together | 460 | How intra-session and inter-session context management work as a cycle | [Link](https://hannahstulberg.substack.com/i/187471997/putting-it-all-together) |
| What you should have now | 478 | Summary of outcomes from the article | [Link](https://hannahstulberg.substack.com/i/187471997/what-you-should-have-now) |
| Your first hour | 494 | Step-by-step first-hour plan: pick area, create top-level file, create project file, use it | [Link](https://hannahstulberg.substack.com/i/187471997/your-first-hour) |
| Want to go deeper? | 514 | Link to Claude Code Masterclass for developer-focused CLAUDE.md coverage | [Link](https://hannahstulberg.substack.com/i/187471997/want-to-go-deeper) |
