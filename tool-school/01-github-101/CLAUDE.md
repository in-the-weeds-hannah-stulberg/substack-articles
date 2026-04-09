# Tool School: GitHub 101 (GitHub is the New Google Drive)

**Authors:** Hannah Stulberg & Sidwyn Koh | **Published:** 2026-02-27

## Article Map

| Section | Line | Coverage |
|---------|------|----------|
| Title & Subtitle | 24 | Everything you need to start using GitHub: setup, workflow, interactive lesson |
| Introduction | 28 | Hannah's personal story of GitHub mistakes; teaming up with Sidwyn Koh |
| By the end of this article, you'll have | 54 | Learning objectives: concepts, setup, practice repo, daily workflow, collaboration, troubleshooting |
| Here's how this guide is organized | 69 | Table of contents for the guide's seven major sections |
| GitHub in Plain Language | 90 | What GitHub is, why it matters, how collaboration works |
| GitHub isn't just for engineers | 94 | GitHub as collaboration platform for any knowledge work; version history, review, rollback |
| Why GitHub matters even more now | 113 | AI-native teams need shared context, skills, commands; review for AI-generated changes |
| How collaboration actually works | 127 | Sarah and Jake walkthrough: clone, branch, commit, push, PR, review, merge |
| Meet the Practice Repo | 156 | Introduction to sidwyn/acme-ops; fork vs clone; article included as markdown in repo |
| Part 1: Setup & Installation | 183 | Five things to install before collaborating |
| 1. Create a GitHub Account | 204 | github.com/signup |
| 2. Install Git | 208 | Claude Code way and manual way (Mac/Windows) |
| 3. Configure Git | 226 | Set name and email for commit attribution |
| 4. Set Up SSH Keys | 238 | SSH key pairs explained; generation and GitHub registration |
| 5. Install the GitHub CLI | 260 | gh CLI for terminal-based GitHub management |
| 6. Install the GitHub MCP (optional) | 272 | MCP plugin for direct Claude Code-GitHub integration |
| You're set up | 284 | Summary of installed toolchain |
| Part 2: GitHub Repositories 101 | 296 | Where work lives and how to organize it |
| What is a Repository? | 307 | Project folder with version history; scope and isolation |
| What a Repo Looks Like on GitHub | 319 | File list, README, commit history |
| How to Organize Your Repos | 331 | One repo per project/domain; team repos vs personal repo |
| Before You Create: Key Decisions | 353 | Three decisions GitHub asks when creating a repo |
| Public vs. Private | 357 | Default to private; when to go public |
| Public repos need a license | 371 | MIT license recommendation; license chooser |
| Initialize with a README | 381 | Always check the box |
| GitHub vs. Cloud Storage | 385 | When to use each; moving existing folders to GitHub |
| Finding and Using Other People's Repos | 417 | Searching, cloning, forking other projects |
| Finding repos | 423 | GitHub search; awesome-claude-code curated list |
| Cloning repos | 429 | Download a copy; read the README |
| Forking repos | 445 | Your own modifiable copy on GitHub |
| Your First Repo: Fork and Clone acme-ops | 451 | Hands-on fork and clone of the practice repo |
| Step 1: Fork the repo on GitHub | 457 | One-click fork |
| Step 2: Clone your fork to your machine | 461 | Where to keep repos; don't nest repos; Claude Code and manual way |
| You're Ready to Work | 491 | IDE, terminal, and GitHub web interface orientation |
| Part 3: The Daily GitHub Workflow | 503 | Everything needed to start working daily |
| GitHub Is the New Google Drive | 514 | Six core concepts mapped to Google Drive equivalents |
| The Short Version | 522 | Complete six-step workflow: branch, edit, commit, push, PR, merge |
| The Deep Dive | 555 | Each step explained in full with what's happening under the hood |
| Step 1: Get to your branch | 561 | Branches explained; creating, naming; when to branch vs work on main |
| Pulling | 587 | Two pulling scenarios: your branch and main into your branch |
| Pulling your branch | 595 | Keep local copy in sync with GitHub |
| Pulling main into your branch | 605 | Merge vs rebase; when to use each |
| Stashing | 623 | Pause uncommitted work to switch branches safely |
| Step 2: Make your edits | 647 | Just edit normally; Git tracks in background |
| Step 3: Commit | 653 | Review changes, save snapshot; commit messages; commit early and often |
| Step 4: Push | 701 | Upload commits to GitHub |
| Step 5: Open a pull request (PR) | 713 | Creating PRs; push vs PR distinction |
| Creating a pull request | 721 | Claude Code and manual way; PR title and description |
| Adding reviewers to your PR | 740 | How to choose and add reviewers |
| Reviewing a pull request | 757 | Three parts: diff, comments, close review |
| Looking at the diff | 769 | Browser and Claude Code approaches |
| Leaving comments | 779 | Line-level and general feedback |
| Closing out your review | 787 | Comment, approve, or request changes |
| How to know when your PR is approved | 803 | Email, GitHub bell, Slack, PR page status |
| Step 6: Merge | 826 | Combine changes into main |
| Merge conflicts | 830 | What they are; Claude Code resolution; manual markers |
| Merging a pull request | 850 | Three merge options: squash, merge commit, rebase; branch cleanup |
| Beyond the Daily Workflow | 874 | Additional GitHub features |
| Notifications | 876 | Email, bell, Slack, mobile; customization |
| Putting It All Together: Sarah's Full Workflow | 895 | Complete end-to-end example with all nine steps |
| When Things Go Wrong | 923 | Four common Git errors and fixes |
| "Your branch is behind 'origin/main'" | 929 | Local copy out of date; git pull |
| "Merge conflict in [filename]" | 939 | Two people changed same lines; resolution |
| "HEAD detached at [some hash]" | 949 | Checked out a commit instead of branch |
| "Permission denied (publickey)" | 959 | SSH key not set up correctly |
| "I accidentally cloned a repo inside another repo" | 969 | Nested repos; move to fix |
| The Big Reassurance | 975 | Git is recoverable; errors look scarier than they are |
| .gitignore: What NOT to Upload | 981 | API keys, node_modules, .env security; templates |
| What You Should Have Now | 997 | Summary of all outcomes |
| Your Turn: Submit Your First PR | 1009 | Interactive exercise: easy path and challenge path |
| The easy path | 1026 | Create takeaways file, commit, push, open PR |
| The challenge path | 1032 | Edit community-board.md, resolve merge conflict |
| Preview: GitHub 102 | 1038 | Upcoming topics: worktrees, Actions, Issues, Pages |
| Want to Go Deeper? | 1051 | External resources: Learn Git Branching, GitHub skills, Pro Git, Oh Shit Git |
