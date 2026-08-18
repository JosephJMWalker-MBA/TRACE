# TRACE Protocol

TRACE defines a seven-stage lifecycle for consequential agentic development and experimentation.

The lifecycle is not meant to force every project into ceremony. It creates explicit checkpoints where intent, implementation, evidence, and interpretation can otherwise blur together.

## Stage 1 — Intent

State what is being attempted before deciding how to build it.

Record, at minimum:

- the question or objective;
- why the work matters;
- the decision owner;
- known constraints;
- what is out of scope;
- what evidence would be useful;
- what consequence follows from the result.

### Exit condition

A competent implementer should be able to explain the goal without inventing product intent.

---

## Stage 2 — Freeze

Identify decisions that should not move after the result is visible.

Possible frozen elements include:

- success/failure criteria;
- protocol version;
- prompts;
- models;
- datasets or manuscripts;
- sampling or packetization rules;
- exclusion criteria;
- validators;
- comparison method;
- retry policy;
- stop conditions.

Create stable fingerprints for consequential artifacts when appropriate.

A frozen protocol may be revised, but a revision creates a new protocol state. Do not retroactively pretend the earlier run used the revised rules.

### Exit condition

The project can answer:

> What are we no longer allowed to change merely because we dislike the outcome?

---

## Stage 3 — Implement

Build the smallest implementation capable of executing the frozen intent faithfully.

The implementation record should make clear:

- source revision;
- configuration;
- dependencies that materially affect behavior;
- tests performed;
- known limitations;
- deviations from the frozen protocol, if any.

Prefer deterministic machinery where deterministic behavior is available and useful.

### Exit condition

The implementation is reviewable as an artifact rather than requiring trust in the implementing agent's explanation.

---

## Stage 4 — Review

Review the implementation independently of implementation confidence.

The reviewer should ask:

1. Does the implementation match the frozen protocol?
2. Can malformed or partial outputs pass as success?
3. Are important assumptions encoded or merely implied?
4. Are persistence boundaries clear?
5. Are retries observable rather than silent?
6. Could stale state contaminate a new run?
7. Are reported counts derived from the actual deterministic path?
8. Is failure evidence preserved?
9. Can outputs be traced back to inputs and source revision?

Where appropriate, use tests, mutation tests, validators, static checks, independent model review, or human inspection.

### Exit condition

There is evidence supporting execution readiness that does not depend solely on the implementer's self-assessment.

---

## Stage 5 — Preflight

Verify the real execution environment immediately before consequential execution.

A preflight manifest should capture the subset relevant to the project, such as:

```text
run_id
protocol_version
source_revision
operator
execution_host
host_architecture
model_name
model_digest
input_paths
input_digests
configuration_digest
output_root
persistent_storage_verified
available_storage
authentication_verified
started_at
```

Also verify assumptions that are easy to overlook:

- the intended machine is actually being addressed;
- required identities or credentials are loaded;
- persistent paths exist and are writable;
- temporary storage is not being mistaken for durable state;
- model and data identities match the frozen record;
- expected output directories are empty or intentionally resumable;
- clocks and timestamps are usable for later reconstruction.

### Exit condition

A successful execution would produce evidence that is attributable, durable, and interpretable.

---

## Stage 6 — Execute

Run the system without changing frozen criteria in response to emerging results.

Preserve:

- raw outputs;
- stdout/stderr or equivalent logs;
- validator failures;
- retry events;
- unexpected counts;
- timing information when relevant;
- machine-readable run status;
- final artifact digests when useful.

Do not silently repair evidence in place.

If the run must be interrupted or invalidated, record that explicitly.

### Exit condition

The run has a durable evidence bundle whose provenance can be reconstructed.

---

## Stage 7 — Interpret

Interpret only after execution evidence has been preserved.

Separate the record into three layers:

### Observation

What happened?

Examples:

- 351 items entered review;
- a model produced malformed structured output;
- two implementations disagreed on a count;
- an SSH identity was absent from the agent;
- a run completed with a specific digest.

### Inference

What does the observation plausibly imply?

Examples:

- the validator caught a real failure mode;
- the product shape may generate too much human review;
- a temporary-state assumption is operationally fragile.

### Decision

What changes next?

Examples:

- revise the protocol and create a new version;
- change implementation while preserving the original evidence;
- run a new experiment;
- abandon a product shape;
- promote a repeated practice into TRACE itself.

### Exit condition

The next cycle begins from an explicit decision grounded in preserved evidence.

---

# Minimal TRACE record

For lower-consequence work, TRACE may be compressed to a short record:

```text
Intent:
Frozen decisions:
Implementation revision:
Review evidence:
Preflight identity:
Execution artifacts:
Observations:
Inferences:
Decision:
```

The protocol should become more rigorous only when consequence justifies it.

# Change rule

A change belongs in TRACE's core protocol only when there is evidence that it generalizes beyond one project.

Case studies should therefore distinguish:

- **project-specific mechanism** — useful locally;
- **candidate pattern** — repeated but not yet proven general;
- **protocol invariant** — demonstrated across materially different contexts.

This distinction is intended to keep TRACE from becoming an automation framework built around the accidents of its first case study.
