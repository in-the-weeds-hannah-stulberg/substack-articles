# CC4E #8: Keeping Up with the Claude Code Treadmill (30 Claude Code Tips & Tricks)

**Author:** Hannah Stulberg | **Published:** 2026-05-04

## Article Map

| Section | Line | Coverage | Substack |
|---------|------|----------|----------|
| Want your whole team working together in Claude Code? | 58 | Team OS workshop CTA with Carl Vellotti | — |
| Every In the Weeds guide comes with an AI tutor | 77 | Pitch for the In the Weeds learning repo as an AI tutor | — |
| The short version | 95 | All 30 tips listed at-a-glance, grouped by category | — |
| Make Cursor feel like yours | 155 | Intro to the first cluster: customizing your Cursor environment | — |
| 1. Pick a Cursor theme that's actually yours | 167 | Switching themes via Color Theme picker and Extensions panel | [Link](https://hannahstulberg.substack.com/i/196381201/1-pick-a-cursor-theme-thats-actually-yours) |
| 2. Tame your terminal panel | 197 | Split panes, drag terminal into editor, name tabs | [Link](https://hannahstulberg.substack.com/i/196381201/2-tame-your-terminal-panel) |
| 3. Install a markdown editor extension to work with markdown files like a Google doc | 229 | Mark Sharp, Markdown Live Editor, Markdown Inline Editor, built-in preview | [Link](https://hannahstulberg.substack.com/i/196381201/3-install-a-markdown-editor-extension-to-work-with-markdown-files-like-a-google-doc) |
| 4. Make sure you can see your `~/.claude/` folder | 289 | Cmd+Shift+G to reveal hidden .claude folder in Cursor | [Link](https://hannahstulberg.substack.com/i/196381201/4-make-sure-you-can-see-your-claude-folder) |
| 5. Build a Cursor workspace for each kind of work you do | 316 | One workspace per project to keep context clean | [Link](https://hannahstulberg.substack.com/i/196381201/5-build-a-cursor-workspace-for-each-kind-of-work-you-do) |
| See what Claude is actually doing | 332 | Intro to visibility cluster: stop flying blind | — |
| 6. Watch Claude think in real time with Ctrl+O | 343 | Ctrl+O reveals Claude's live reasoning stream | [Link](https://hannahstulberg.substack.com/i/196381201/6-watch-claude-think-in-real-time-with-ctrl-o) |
| 7. Run `/context` to see what's eating your context window | 351 | /context breakdown of token usage by source | [Link](https://hannahstulberg.substack.com/i/196381201/7-run-context-to-see-whats-eating-your-context-window) |
| 8. Track context usage claude.ai (Claude on the web) with claude-counter | 363 | Chrome extension that shows session and weekly usage bars | [Link](https://hannahstulberg.substack.com/i/196381201/8-track-context-usage-claude-ai-claude-on-the-web-with-claude-counter) |
| 9. Map any GitHub repo in minutes with DeepWiki | 386 | DeepWiki turns any repo into a navigable wiki for orientation | [Link](https://hannahstulberg.substack.com/i/196381201/9-map-any-github-repo-in-minutes-with-deepwiki) |
| Give Claude cleaner source material | 406 | Intro to source-material cluster: in = out | — |
| 10. Pull Google Workspace files in as Markdown | 420 | Convert Google Docs to markdown for Claude to read | [Link](https://hannahstulberg.substack.com/i/196381201/10-pull-google-workspace-files-in-as-markdown) |
| 11. Convert PDFs, Word docs, and more with markitdown | 450 | markitdown CLI for PDF/Word/PPT to markdown | [Link](https://hannahstulberg.substack.com/i/196381201/11-convert-pdfs-word-docs-and-more-with-markitdown) |
| 12. Pull any webpage into Claude Code with Firecrawl | 474 | Firecrawl CLI to scrape webpages cleanly | [Link](https://hannahstulberg.substack.com/i/196381201/12-pull-any-webpage-into-claude-code-with-firecrawl) |
| Connect Claude Code to the web | 497 | Intro to web-connection cluster: give Claude a browser | — |
| 13. Install the Claude in Chrome extension | 509 | Chrome extension lets Claude read your active tab | [Link](https://hannahstulberg.substack.com/i/196381201/13-install-the-claude-in-chrome-extension) |
| 14. Install the Playwright MCP | 531 | Playwright MCP for testing local dev with screenshots | [Link](https://hannahstulberg.substack.com/i/196381201/14-install-the-playwright-mcp) |
| 15. Install the Chrome DevTools MCP | 549 | DevTools MCP for perf profiling, network inspection, Lighthouse | [Link](https://hannahstulberg.substack.com/i/196381201/15-install-the-chrome-devtools-mcp) |
| Use Claude for visual work | 583 | Intro to visual cluster: images, diagrams, previews | — |
| 16. Generate images directly in Claude Code | 594 | In-session image generation without switching tools | [Link](https://hannahstulberg.substack.com/i/196381201/16-generate-images-directly-in-claude-code) |
| 17. Edit and batch-process images without leaving Claude | 608 | Bulk crop, resize, rename images via Claude | [Link](https://hannahstulberg.substack.com/i/196381201/17-edit-and-batch-process-images-without-leaving-claude) |
| 18. Add editable diagrams to any markdown file with Mermaid | 622 | Mermaid extension renders code-defined diagrams in markdown | [Link](https://hannahstulberg.substack.com/i/196381201/18-add-editable-diagrams-to-any-markdown-file-with-mermaid) |
| 19. Spin up quick visual previews with a local HTML file | 672 | Drop an HTML file in the workspace for a live preview | [Link](https://hannahstulberg.substack.com/i/196381201/19-spin-up-quick-visual-previews-with-a-local-html-file) |
| Get more out of every session | 709 | Intro to session-efficiency cluster | — |
| 20. Master the built-in terminal shortcuts | 723 | Keyboard shortcut reference table | [Link](https://hannahstulberg.substack.com/i/196381201/20-master-the-built-in-terminal-shortcuts) |
| 21. Fork your session with `/branch` | 735 | /branch creates a parallel session from a checkpoint | [Link](https://hannahstulberg.substack.com/i/196381201/21-fork-your-session-with-branch) |
| 22. Ask side questions with `/btw` - don't derail your main task | 769 | /btw answers tangential questions without polluting context | [Link](https://hannahstulberg.substack.com/i/196381201/22-ask-side-questions-with-btw-dont-derail-your-main-task) |
| 23. Cut Claude's output bloat with Caveman mode | 777 | Caveman skill compresses Claude's output ~75% | [Link](https://hannahstulberg.substack.com/i/196381201/23-cut-claudes-output-bloat-with-caveman-mode) |
| 24. Cut Claude's input bloat with RTK | 808 | RTK skill trims input tokens before they hit the model | [Link](https://hannahstulberg.substack.com/i/196381201/24-cut-claudes-input-bloat-with-rtk) |
| 25. Talk to Claude with `/voice` (or Wispr Flow) instead of typing | 830 | /voice and Wispr Flow for dictation in Claude Code | [Link](https://hannahstulberg.substack.com/i/196381201/25-talk-to-claude-with-voice-or-wispr-flow-instead-of-typing) |
| 26. Trigger Claude on an interval with `/loop` | 850 | /loop runs a prompt or skill on a recurring schedule | [Link](https://hannahstulberg.substack.com/i/196381201/26-trigger-claude-on-an-interval-with-loop) |
| Take Claude Code off your laptop | 872 | Intro to mobile cluster: work from anywhere | — |
| 27. Use the Claude mobile app to work from your phone | 887 | Continue sessions on the Claude mobile app | [Link](https://hannahstulberg.substack.com/i/196381201/27-use-the-claude-mobile-app-to-work-from-your-phone) |
| 28. Move sessions between devices with `/teleport` and `/remote-control` | 910 | /teleport hands off a session, /remote-control drives one remotely | [Link](https://hannahstulberg.substack.com/i/196381201/28-move-sessions-between-devices-with-teleport-and-remote-control) |
| 29. Text Claude from anywhere with Claude Code Channels | 935 | Channels let you message Claude over SMS/chat | [Link](https://hannahstulberg.substack.com/i/196381201/29-text-claude-from-anywhere-with-claude-code-channels) |
| Just for fun | 979 | Intro to the bonus tip | — |
| 30. Change Claude's thinking verbs to your own | 983 | Customize the verbs Claude uses while thinking | [Link](https://hannahstulberg.substack.com/i/196381201/30-change-claudes-thinking-verbs-to-your-own) |
| What you should have now | 1021 | Recap of what the reader can do after applying tips | — |
| The bottom line | 1034 | Treadmill metaphor close: pick 2-3 tips, come back later | — |
