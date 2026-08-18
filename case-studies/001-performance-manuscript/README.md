# Case Study 001 — Performance Manuscript

**Status:** in progress  
**TRACE purpose:** test whether the protocol can preserve intent, frozen criteria, implementation boundaries, execution evidence, and later interpretation across a real agentic development cycle.

This record is intentionally incomplete. It was created **before** the real-manuscript two-model execution closed, so the case study cannot quietly become a retrospective success narrative.

## Source project

Repository: `JosephJMWalker-MBA/performance-manuscript`

Primary experiment: issue **#65 — Local semantic attribution: Orin Nano LLM proposals with deterministic governance**.

The experiment exists because Product Trial 01 stopped at a human gate with 351 required attribution decisions on an 80,687-word novel. The new hypothesis is that local semantic models should do the reading while Performance Manuscript governs their proposals, preserves provenance, validates contracts, and routes residual uncertainty to a person.

## TRACE mapping before execution

### 1. Intent

Issue #65 states the product question before the real run:

> Can two compact local models perform the manuscript's semantic speaker-attribution work well enough that the human becomes a verifier of disagreements and audits rather than the primary resolver?

The issue explicitly permits a negative result. Success is evidence, not a predetermined yes.

### 2. Freeze

The experiment freezes consequential decisions before real-manuscript inference, including:

- the manuscript/source binding;
- deterministic packet policy;
- model identities and immutable digests;
- common runtime/settings envelope;
- output contract;
- proposal-sidecar semantics;
- two-model agreement classifications;
- review-routing priorities;
- deterministic audit requirements;
- non-mutation of canonical Performance Manuscript state;
- stop conditions and acceptance question.

A later issue comment, `#issuecomment-5334293496`, records the real-manuscript execution protocol as frozen and states that no manuscript inference had occurred before that freeze.

### 3. Implement

Merged PR **#66 — Let a local model read the book, and govern everything it says** implements the provider-neutral semantic proposal path without a canonical apply operation.

Among the implemented boundaries:

- deterministic packets;
- supplied identity vocabulary only;
- runtime schema plus independent deterministic validation;
- proposal sidecars bound to work, source, model, settings, and packet policy;
- two-model comparison;
- human review routing;
- explicit prohibition on automatic canonical attribution;
- synthetic tests and mutation evidence.

### 4. Review

Review is not represented by the implementation agent's confidence alone. The project records executable tests, mutation batteries, fresh-clone reproduction, cross-artifact binding checks, and structural non-mutation guards.

The experiment has already preserved rejected work as evidence. Earlier attribution research branches were closed without merge when held-out evaluation falsified their development fit rather than being rewritten as successes.

### 5. Preflight

The Orin Nano environment was measured before the real run rather than assumed. Recorded evidence includes runtime version, GPU acceleration, memory/storage constraints, local-model identity, structured-output behavior, and context limits.

A synthetic structured-output probe exposed a contract-shape failure: a nullable schema allowed incoherent decisions, while a closed union of decision variants produced contract-valid outputs. Semantic correctness was explicitly not inferred from that probe.

Merged PR #66 then performed a synthetic two-model smoke test on the actual Orin. One Gemma response was refused by the independent validator, demonstrating that runtime schema compliance and application contract validity are separate boundaries.

### 6. Execute

**Pending in this case-study record.**

At the time this shell was created, draft PR **#67 — Give each identity one line, and each packet one retry** remained open. It addresses two pre-inference blockers: prompt-line safety for source labels containing newlines and a frozen one-retry policy with separate attempt evidence.

PR #67 explicitly reports that neither Qwen nor Gemma was shown manuscript text during that work and that the Orin was not contacted for the PR's deterministic structural proofs.

No real-manuscript execution result is recorded here yet.

### 7. Interpret

**Pending.**

Interpretation must be appended only after execution artifacts are frozen. This section must distinguish:

- direct observations;
- derived measurements;
- human verification findings;
- supported conclusions;
- unsupported hypotheses;
- protocol lessons for TRACE itself.

## Why this is a useful TRACE test

This project stresses several proposed TRACE invariants at once:

- durable state versus temporary state;
- precommitment before observation;
- human, reviewer, implementation-agent, and execution-worker role separation;
- immutable identities for code, source, models, and settings;
- failure preserved as evidence rather than repaired invisibly;
- implementation output separated from canonical truth;
- execution logs separated from deterministic semantic artifacts;
- negative experimental results retained in history;
- future-agent legibility through repository artifacts rather than chat memory.

## Historical integrity rule

The pre-execution sections above may be corrected for factual errors or improved with primary-source references, but they must not be rewritten after results arrive to make the experiment appear better designed than it was.

Post-execution evidence belongs in [`EVIDENCE.md`](EVIDENCE.md) first. Interpretation follows after the evidence record is frozen.
