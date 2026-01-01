# ShiftLefter

Building BDD testing tools with **traceability and observability at the core**. Designed for teams who need clean seams, reproducible results, and a clear story from requirements to releases.

## Current Status

**v0.1.0 (December 2025):** [**shiftlefter**](https://github.com/SHIFT-LEFTER/shiftlefter) - 100% Cucumber-compatible Gherkin parser with lossless roundtrip guarantees. The foundation is solid: 268 tests, zero failures.

**Next (January 2026):** Production CLI features (multi-file validation, in-place formatting, progress reporting).

**Roadmap:** Event-native runner, traceability graph, macro expansion (`+` syntax for executable domain requirements).

---

## Long-Term Vision

ShiftLefter aims to solve the traceability problem that plagues real teams: spreadsheets and wikis standing in for actual requirement tracking, brittle test harnesses that can only report pass/fail, and no clear answer to "which requirements or workflows are actually at risk when this build goes red?"

**What ShiftLefter will provide:**

- **End-to-end traceability graph** linking requirements → prototypes → use cases → features → scenarios → test results. Snapshot the graph per release to review impact in terms stakeholders actually care about ("what changed and why does it matter?").

- **Language-agnostic execution** where step implementations can stay in your existing language (Java, Python, JavaScript, etc.). The runner orchestrates via events, not language-specific APIs - no rewrite required.

- **Event-native runner** that treats test runs as observable streams of facts, not just pass/fail. Pluggable clock and seeded randomness enable time-travel testing (run tests "as if it's 2am" or "February 29th") and exact run reproduction for debugging. Enable golden-file diffs, time-travel debugging, and meaningful analytics without bolting on yet another logger.

- **Executable domain requirements** via macro expansion (`Given Log in as admin +`). Bridge the gap between stakeholder language and executable tests with provenance tracking.

- **Strict, validated configs** using clojure.spec - bad setups fail fast with precise "what and where" instead of mystery behavior halfway through a run.

- **Gradual adoption** via optional enforcement. Start with lightweight annotations and IDs, turn on stricter validation (glossaries, requirement links) when you're ready.

- **Release diffs that mean something.** Beyond code and test diffs, see which features and requirements changed, how coverage shifted, and how quality metrics compare to prior deployments.

Built for real teams working in messy, regulated environments where "what exactly broke for which patients/customers/users?" isn't a hypothetical question.

---

### About the Project

ShiftLefter is being built by a QA professional with 25 years across dramatically different domains - from hardware drivers and network infrastructure to payment systems and regulated healthcare, from startups to Fortune 500s, from manual testing to full-stack automation.

Across all of them, the patterns were the same: requirements lived in spreadsheets and wikis instead of being traceable artifacts, test runners could only say "red" or "green" without explaining *which requirements or workflows* were at risk, and traceability was something teams talked about wanting but couldn't actually achieve with existing tools.

ShiftLefter is built to make requirements traceability and test observability accessible to real teams working in messy, real-world codebases - not just to people building greenfield systems with perfect processes.
