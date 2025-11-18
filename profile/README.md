# ShiftLefter

**ShiftLefter** is an open-source test runner and quality toolkit that puts **traceability and observability first**. It treats a test run as a stream of facts—validated, timestamped, and easy to diff—so you catch problems earlier and explain them faster. Built in Clojure, it’s designed for teams who want clean seams, reproducible results, and a clear story from requirements to releases. The runner speaks events, not language-specific APIs, so your step implementations can stay in your existing language (one per suite)—no rewrite to Clojure required. Early builds are under active development.

## What ShiftLefter aims to provide

- **Traceability graph, end-to-end.** Model and navigate links from **requirements → prototypes → use cases → features → scenarios → checks**. Snapshot the graph per release so you can review impact (“what changed?”) in terms your PMs, auditors, and engineers actually care about.

- **Event-native runner.** Every action emits structured events to an observable hub (console/JSONL), enabling golden-file diffs, time-travel debugging, and lightweight analytics without bolting on yet another logger.

- **Language-agnostic step executors.** Step functions live in a single language of your choice—Java, JavaScript, Python, etc.—as long as they can speak the event protocol. The runner doesn’t force you into Clojure; it orchestrates and observes whatever step library you already have.

- **Strict, legible configs.** Configs are validated with **clojure.spec** at load time—no silent coercions—so bad setups fail fast with precise “what and where” instead of mystery behavior halfway through a run.

- **Deterministic by design.** Pluggable clock and ID sources (fixed seeds, anchored-monotonic, or real time) make runs reproducible across machines and CI, killing a whole class of flakiness.

- **Clean seams: parser → binder → executor.** A pure Cucumber parser yields a normalized AST; a binder maps steps to functions; an executor runs them and emits step events. You can swap each layer without rewriting the whole suite.

- **Preflight plan checks.** Plans are validated (shape + filesystem) before a run starts, so missing feature files, broken selectors, and bad filters are caught before CI burns a build.

- **Adopt piecemeal, not all-or-nothing.** Start by dropping IDs and lightweight annotations into your existing codebase. Turn on optional enforcement gradually—labels first, use-case links next, full requirements mapping when you’re ready.

- **Shared glossaries that can bite (if you want).** Maintain project glossaries for actors, users, domain nouns/verbs, and interfaces. Initially they’re advisory; later, toggle enforcement to flag unknown users, undefined nouns, or verb drift in specs and steps.

- **Release diffs that mean something.** Beyond code and test diffs, see which **features and requirements** changed, how coverage shifted, and how key quality metrics compare to prior deployments—so product, QA, and engineering are looking at the same picture.

- **Built for real teams.** Quiet CI runs, a simple CLI, humane errors, and a roadmap for **semi-automated checks** (human/LLM-in-the-loop) when binary pass/fail isn’t enough.

Early builds are under active development. If you’re interested in early use or collaboration, open an issue or reach out.

---

### About the project

ShiftLefter is being built by a career QA/SDET who has:

- Done manual and automated testing for everything from PC hardware and drivers (including WHQL certification) to network/security appliances, web apps, and payment systems
- Run network and server infrastructure (mail, DNS, web, Cisco gear) for a few hundred users
- Spent the last seven years in regulated healthcare and lab systems, where audits, traceability, and “what exactly broke for which patients?” are not hypothetical questions

Across all of those, the patterns were the same: spreadsheets and wikis trying to stand in for real traceability, brittle Cucumber harnesses, and test runners that could only talk about pass/fail — not *which requirements, users, or workflows* were actually at risk.

ShiftLefter is an event-native runner and traceability toolkit that turns each test run into a stream of facts you can trace, diff, and explain — instead of just another mysterious red build — and is designed to be adopted gradually inside the messy systems teams already have.
