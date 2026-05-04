# Claude Code for Everything: Why AI Gets Dumber The Longer You Talk To It (And How to Fix It)

**Author:** Hannah Stulberg | **Published:** 2026-01-20

## Article Map

| Section | Line | Coverage | Substack |
|---------|------|----------|----------|
| Title & intro | 18 | ChatGPT degradation story; context management as the culprit | [Link](https://hannahstulberg.substack.com/p/claude-code-for-everything-why-ai) |
| By the end of this article, you'll have | 42 | Learning objectives | [Link](https://hannahstulberg.substack.com/i/185143249/by-the-end-of-this-article-youll-have) |
| Context 101 | 50 | Filing cabinet metaphor; four key concepts | [Link](https://hannahstulberg.substack.com/i/185143249/context-101) |
| 1. Context | 66 | What context is; drawer starts empty; fills with conversation | [Link](https://hannahstulberg.substack.com/i/185143249/1-context) |
| 2. Context window | 76 | Drawer size; 200K tokens (~3 novels); fills faster than expected | [Link](https://hannahstulberg.substack.com/i/185143249/2-context-window) |
| 3. Compaction | 88 | Auto-summarization at 70-80% full; fidelity loss | [Link](https://hannahstulberg.substack.com/i/185143249/3-compaction) |
| 4. Thinking room | 102 | Processing space for reasoning; quality drops before limit | [Link](https://hannahstulberg.substack.com/i/185143249/4-thinking-room) |
| Why this matters for you | 114 | Claude Code vs ChatGPT/web AI context control comparison | [Link](https://hannahstulberg.substack.com/i/185143249/why-this-matters-for-you) |
| Effective Context Management | 130 | Overview of five techniques | [Link](https://hannahstulberg.substack.com/i/185143249/effective-context-management) |
| 1. The status line: You can't manage what you can't see | 144 | Monitoring context usage; 0-50%, 50-70%, 70%+ zones | [Link](https://hannahstulberg.substack.com/i/185143249/1-the-status-line-you-cant-manage-what-you-cant-see) |
| How to turn on the status line | 164 | /statusline command; configuration prompt | [Link](https://hannahstulberg.substack.com/i/185143249/1-the-status-line-you-cant-manage-what-you-cant-see) |
| 2. Manual compaction: You decide what Claude carries forward | 182 | Controlling what survives compaction | [Link](https://hannahstulberg.substack.com/i/185143249/2-manual-compaction-you-decide-what-claude-carries-forward) |
| How to compact manually | 196 | Four-step process: understand context, decide, draft instructions, run /compact | [Link](https://hannahstulberg.substack.com/i/185143249/how-to-compact-manually) |
| 3. Parallel sessions: Separate tasks, separate drawers | 230 | Context isolation per task | [Link](https://hannahstulberg.substack.com/i/185143249/3-parallel-sessions-separate-tasks-separate-drawers) |
| 4. Session management: Pick up where you left off | 246 | Preserving drawer contents across time | [Link](https://hannahstulberg.substack.com/i/185143249/4-session-management-pick-up-where-you-left-off) |
| 5. Background agents: Split off related work to its own drawer | 260 | Delegating to separate context; John/Jane metaphor | [Link](https://hannahstulberg.substack.com/i/185143249/5-background-agents-split-off-related-work-to-its-own-drawer) |
| This is the foundation | 276 | Summary of five practices | [Link](https://hannahstulberg.substack.com/i/185143249/this-is-the-foundation) |
| Context management in Cowork | 280 | Feature comparison table: Claude Code vs Cowork | [Link](https://hannahstulberg.substack.com/i/185143249/context-management-in-cowork) |
| A note on Projects, Gems, and Custom GPTs | 286 | Why persistent context tools don't solve in-session management | [Link](https://hannahstulberg.substack.com/i/185143249/a-note-on-projects-gems-and-custom-gpts) |
| What you should have now | 298 | Recap of mental model and techniques | [Link](https://hannahstulberg.substack.com/i/185143249/what-you-should-have-now) |
| What comes next: CLAUDE.md files | 308 | Teaser for next article on persistent memory files | [Link](https://hannahstulberg.substack.com/i/185143249/what-comes-next-claudemd-files) |
| Want to go deeper? | 324 | Tal Raviv's article on compaction internals | — |
