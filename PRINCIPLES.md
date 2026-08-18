# TRACE Principles

TRACE is intentionally small. These principles describe the invariants that should survive changes in model provider, repository host, hardware, language, and project type.

## 1. Durable state over temporary state

Consequential project state should live in a durable, named location with an understood ownership and persistence boundary.

Temporary directories, transient shells, chat context, and agent memory may accelerate work, but they must not become the only place where critical experiment state exists.

**Test:** Could a new operator recover the required state after a restart without reconstructing it from memory?

## 2. Explicit responsibility boundaries

Separate who defines intent, who implements, who reviews, who executes, and who interprets.

One person or model may perform more than one role, but the roles should remain logically distinct so confidence in one stage does not silently certify another.

**Test:** Can the project identify which role made each consequential decision?

## 3. Freeze before observation

Any criterion that could be conveniently changed after seeing a result should be frozen before that result becomes visible.

Examples include:

- success and failure criteria;
- inclusion or exclusion rules;
- model and prompt selection;
- packetization or sampling logic;
- comparison procedures;
- stop conditions.

The goal is not rigidity. The goal is to distinguish a precommitted test from a post-hoc redesign.

**Test:** If the result disappoints us, which decisions are we still allowed to change without invalidating the current run?

## 4. Fingerprint consequential inputs

When the identity of an input matters, preserve a stable fingerprint such as a cryptographic digest together with enough metadata to identify what was hashed.

Useful candidates include:

- manuscripts and datasets;
- prompts and protocol files;
- model artifacts;
- configuration bundles;
- generated manifests;
- binaries used in execution.

A digest is evidence of identity, not evidence of correctness.

**Test:** Can we prove that the artifact interpreted later is the artifact that was actually executed?

## 5. Evidence is not interpretation

Execution workers produce observations, logs, measurements, outputs, and failures. They do not acquire authority merely because they produced them.

Interpretation should state what was observed separately from what is inferred.

**Test:** Could another reviewer inspect the same evidence and disagree with the conclusion without disputing the underlying record?

## 6. Implementation cannot self-certify

An implementation agent's confidence is not validation.

Prefer independent checks appropriate to the project:

- tests;
- mutation tests;
- static analysis;
- diff review;
- schema validation;
- independent model review;
- human inspection;
- real-world execution.

Independence is a gradient, not a binary property. The reviewer should be less coupled to the implementation path than the implementer was.

**Test:** What evidence would still exist if the implementation agent's explanation were removed?

## 7. Preflight before consequential execution

Before an expensive, destructive, public, safety-relevant, or difficult-to-repeat run, verify the environment that will make the evidence meaningful.

Preflight may include:

- machine or device identity;
- model identity and digest;
- source revision;
- input fingerprints;
- available storage;
- authentication state;
- persistence paths;
- clock and timestamp assumptions;
- expected output locations;
- dry-run validation.

**Test:** What could make a technically successful run scientifically or operationally unusable?

## 8. Preserve failures as first-class evidence

Do not quietly overwrite malformed output, failed runs, unexpected counts, validator rejections, or environmental failures.

A failure can expose a missing boundary more clearly than a successful run.

Corrections should create a new state or run rather than erase the prior record when the prior record matters to interpretation.

**Test:** Can we reconstruct what failed, when it failed, and what changed afterward?

## 9. Durable handoffs over conversational continuity

Assume that the next engineer, agent, session, or model begins without access to the current conversation.

Use durable artifacts to communicate:

- current state;
- frozen decisions;
- unresolved questions;
- next permitted actions;
- known failures;
- required validation.

Chat can coordinate work. It should not be the sole institutional memory.

**Test:** Could a competent newcomer resume safely from the repository and referenced artifacts?

## 10. Make project history legible

The repository should preserve enough context that important design choices can be traced to evidence, constraints, or explicit judgment.

This does not mean storing every thought. TRACE favors concise decision records over exhaustive transcripts.

**Test:** Can the project answer "why is it this way?" without requiring access to the original author's memory?

## 11. Scale process to consequence

TRACE should not turn every edit into a ceremony.

The amount of freezing, review, fingerprinting, and evidence preservation should increase with:

- irreversibility;
- cost;
- safety impact;
- public impact;
- experimental consequence;
- difficulty of reproduction;
- number of autonomous actors involved.

**Test:** Is the protocol reducing risk, or merely producing paperwork?

## 12. Formalize before automating

Do not build orchestration around a workflow that has only happened once.

First identify repeated reasoning and stable boundaries across different projects. Then automate the mechanics that repeatedly support those invariants.

**Test:** Are we automating a principle, or preserving an accident of one implementation?

---

## Working maxim

> **The project, not the participant, should become the durable holder of its own history.**
