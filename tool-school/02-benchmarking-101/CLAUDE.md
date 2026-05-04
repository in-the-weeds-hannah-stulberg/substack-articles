# Tool School: Benchmarking 101 (How To Read AI Model Report Cards)

**Author(s):** Hannah Stulberg, Akshat Khandelwal | **Published:** 2026-03-31 | **Series:** Tool School #2

## Companion data: model releases

This article has a `releases/` subfolder with structured data for individual model launches that the Benchmarking 101 framework can be applied to. Each release is a folder containing extracted scorecard data, source chart images, and pricing — curated by Hannah from the announcement page (since vendor scorecards are typically image-based and unreadable by WebFetch).

The `explain-ai-model-release` skill reads from this folder before falling back to web fetching. To add a new release, create `releases/YYYY-MM-MODEL-SLUG/release.md` following the schema established by existing entries.

| Release | Folder |
|---|---|
| Claude Opus 4.7 (2026-04-16) | `releases/2026-04-opus-4-7/` |

## Article Map

| Section | Line | Coverage | Substack |
|---------|------|----------|----------|
| Title & Subtitle | 23 | How to read AI model report cards - learn to read the scorecard behind every AI model launch | [Link](https://hannahstulberg.substack.com/p/tool-school-benchmarking-101-how-to-read-ai-model-report-cards) |
| Series Introduction | 26 | Tool School series context, link to GitHub 101 | [Link](https://hannahstulberg.substack.com/p/tool-school-benchmarking-101-how-to-read-ai-model-report-cards) |
| Opening & Motivation | 31 | Why benchmark literacy matters - 40 models in 14 months, scorecards you can't read | [Link](https://hannahstulberg.substack.com/p/tool-school-benchmarking-101-how-to-read-ai-model-report-cards) |
| Co-author Introduction | 39 | Akshat Khandelwal (PM at DoorDash, Help Me Unpack Substack) | [Link](https://hannahstulberg.substack.com/p/tool-school-benchmarking-101-how-to-read-ai-model-report-cards) |
| Learning Outcomes | 47 | 5 things you'll have by the end: benchmark understanding, major benchmarks, scorecard reading, cost awareness, confidence | [Link](https://hannahstulberg.substack.com/p/tool-school-benchmarking-101-how-to-read-ai-model-report-cards) |
| Guide Organization | 55 | 5-section roadmap of the article | [Link](https://hannahstulberg.substack.com/p/tool-school-benchmarking-101-how-to-read-ai-model-report-cards) |
| The Short Version | 63 | 2-minute framework: 4 benchmark categories, 3 questions to ask, relevance tiers, 4 things to watch | [Link](https://hannahstulberg.substack.com/i/192682753/the-short-version) |
| The Pace of Change: 40 Models in 14 Months | 99 | Full timeline of model launches Jan 2025 - Mar 2026 across Anthropic, OpenAI, Google | [Link](https://hannahstulberg.substack.com/i/192682753/the-pace-of-change-40-models-in-14-months) |
| Every Launch Changes What You Can Build | 125 | Why the accelerating pace matters for your work - build for the model coming in 6 months | [Link](https://hannahstulberg.substack.com/i/192682753/the-pace-of-change-40-models-in-14-months) |
| Benchmarks 101 | 137 | What benchmarks actually measure, how models are scored, terms you need to know | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| A High SAT Score Doesn't Make Someone a Great Colleague | 141 | SAT metaphor - benchmark scores are standardized tests for AI, each measures one narrow skill | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| What a Benchmark Actually Is | 155 | Definition: standardized test for AI models - fixed questions, tasks with answers, or head-to-head | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| Benchmarks Use One of 3 Grading Systems | 161 | Pass@1 (one attempt), Pass@k (multiple attempts), Elo rating (head-to-head via Chatbot Arena) | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| There Are 4 Major Categories of Benchmarks | 177 | Knowledge & Reasoning, Coding, Reasoning, Agentic & Computer Use | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| Why Only a Handful of Benchmarks Become Standard | 193 | 3 bars: hard enough, simple enough metric, interpretable to non-researchers | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| The Benchmark Reference Table | 203 | Complete table of every major benchmark: category, year, creator, what it tests, scoring | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| The Major Benchmarks | 226 | Deep dive on each benchmark with example cards | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| Knowledge & Reasoning Benchmarks | 228 | MMLU (2020), GPQA Diamond (2023), HLE (2025), GDPval (2025) | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| Coding Benchmarks | 256 | SWE-bench Verified (2024), SWE-bench Pro (2025), SWE-Lancer (2025), plus the real-world gap | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| Reasoning Benchmarks | 284 | ARC-AGI-3 (2026) and ARC-AGI-2 (2025) - novel problem-solving the model has never seen | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| Agentic & Computer Use Benchmarks | 300 | OSWorld, tau2-bench, BigLaw Bench, Terminal-Bench 2.0 - sustained professional work | [Link](https://hannahstulberg.substack.com/i/192682753/benchmarks-101) |
| Why Benchmarks Expire | 326 | When everyone gets an A, the A stops meaning anything - saturation, contamination, optimization | [Link](https://hannahstulberg.substack.com/i/192682753/why-benchmarks-expire-when-everyone-gets-an-a-the-a-stops-meaning-anything) |
| Models Improve Faster Than New Tests | 338 | Saturation: scores converge, spread disappears, test becomes noise | [Link](https://hannahstulberg.substack.com/i/192682753/why-benchmarks-expire-when-everyone-gets-an-a-the-a-stops-meaning-anything) |
| Training Data Gets Contaminated | 344 | Contamination: models see test answers in training data - SWE-bench Verified example | [Link](https://hannahstulberg.substack.com/i/192682753/why-benchmarks-expire-when-everyone-gets-an-a-the-a-stops-meaning-anything) |
| Optimization Pressure (Goodhart's Law) | 354 | When a measure becomes a target, it ceases to be a good measure | [Link](https://hannahstulberg.substack.com/i/192682753/why-benchmarks-expire-when-everyone-gets-an-a-the-a-stops-meaning-anything) |
| The Cycle Compounds and Accelerates | 358 | ImageNet lasted 5 years, MMLU 3, SWE-bench Verified 2 - ARC-AGI-3's radical response | [Link](https://hannahstulberg.substack.com/i/192682753/why-benchmarks-expire-when-everyone-gets-an-a-the-a-stops-meaning-anything) |
| Which Benchmarks Are Still Working Right Now? | 374 | 3 questions: How long public? Who created it? Scores still spread out? | [Link](https://hannahstulberg.substack.com/i/192682753/why-benchmarks-expire-when-everyone-gets-an-a-the-a-stops-meaning-anything) |
| Where Each Benchmark Stands Right Now | 384 | Trust tiers: High (ARC-AGI-3, ARC-AGI-2, HLE, SWE-bench Pro, OSWorld, Terminal-Bench 2.0), Moderate, Low | [Link](https://hannahstulberg.substack.com/i/192682753/why-benchmarks-expire-when-everyone-gets-an-a-the-a-stops-meaning-anything) |
| Where to Check Scores Yourself | 421 | 5 independent sources: Chatbot Arena, Artificial Analysis, ARC Prize, Scale AI, Stanford CRFM | [Link](https://hannahstulberg.substack.com/i/192682753/why-benchmarks-expire-when-everyone-gets-an-a-the-a-stops-meaning-anything) |
| Apply What You've Learned: Read the Scorecard | 433 | Real benchmark table from Anthropic's Opus 4.6 launch - read and evaluate every line | [Link](https://hannahstulberg.substack.com/i/192682753/apply-what-youve-learned-you-can-now-read-the-scorecard) |
| You Recognize Every Name on This Table | 452 | Applying benchmark knowledge to identify each test in the Opus 4.6 scorecard | [Link](https://hannahstulberg.substack.com/i/192682753/apply-what-youve-learned-you-can-now-read-the-scorecard) |
| You Know What the Scores Actually Mean | 456 | Understanding pass@1 vs Elo rating in context | [Link](https://hannahstulberg.substack.com/i/192682753/apply-what-youve-learned-you-can-now-read-the-scorecard) |
| You Can Evaluate How Relevant Every Score Is | 462 | Relevance assessment of each Opus 4.6 benchmark score with reasoning | [Link](https://hannahstulberg.substack.com/i/192682753/apply-what-youve-learned-you-can-now-read-the-scorecard) |
| How to Read the Next Model Launch | 479 | Head-to-head comparison and what to watch for in any announcement | [Link](https://hannahstulberg.substack.com/i/192682753/how-to-read-the-next-model-launch) |
| No Single Model Wins | 483 | Side-by-side comparison: Opus 4.6 vs Sonnet 4.6 vs GPT-5.4 vs Gemini 3.1 Pro | [Link](https://hannahstulberg.substack.com/i/192682753/how-to-read-the-next-model-launch) |
| 4 Things to Watch for in Any Launch Announcement | 495 | Missing benchmarks, baseline comparisons, human preference vs benchmarks, methodology transparency | [Link](https://hannahstulberg.substack.com/i/192682753/how-to-read-the-next-model-launch) |
| What the Scorecard Leaves Out: Cost | 523 | API pricing, tokens, input/output costs - the dimension most tables omit | [Link](https://hannahstulberg.substack.com/i/192682753/what-the-scorecard-leaves-out-the-sat-doesnt-tell-you-about-tuition) |
| Same Scores, Wildly Different Prices | 539 | Output token pricing comparison across models, DeepSeek R1 cost advantage | [Link](https://hannahstulberg.substack.com/i/192682753/what-the-scorecard-leaves-out-the-sat-doesnt-tell-you-about-tuition) |
| Cost-Adjusted Evaluation Is Coming | 551 | ARC-AGI-2 measures cost-per-task, Artificial Analysis price-performance rankings | [Link](https://hannahstulberg.substack.com/i/192682753/what-the-scorecard-leaves-out-the-sat-doesnt-tell-you-about-tuition) |
| Reading Recent Model Launches | 559 | Informed reads of Opus 4.6, Sonnet 4.6, and GPT-5.4 launches | [Link](https://hannahstulberg.substack.com/i/192682753/reading-the-3-february-march-2026-launches) |
| Best for What? At What Price? On Which Tests? | 581 | Summary: no single model wins across the board | [Link](https://hannahstulberg.substack.com/i/192682753/best-for-what-at-what-price-on-which-tests) |
| You Can Read the Next Model Announcement Yourself | 587 | Closing recap of 5 learning outcomes and confidence statement | [Link](https://hannahstulberg.substack.com/i/192682753/you-can-read-the-next-model-announcement-yourself) |
