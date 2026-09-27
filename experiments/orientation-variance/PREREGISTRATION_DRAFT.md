# Orientation Variance Experiment — Preregistration Draft

**Repository:** TRACE  
**Status:** `PREREGISTRATION_DRAFT_ONLY`  
**Execution authorized:** no  
**Purpose:** test whether deterministic repository routing reduces task-irrelevant variability across AI systems without suppressing legitimate disagreement.

## Research question

When different AI systems, model versions, or repeated fresh sessions are given the same portfolio task, does a fixed orientation router reduce errors and response dispersion caused by irrelevant context-selection choices?

The experiment is concerned with **orientation variance**, not with forcing deterministic language generation.

## Core hypothesis

```text
raw portfolio entry
    -> model chooses its own discovery path
    -> reasoning
```

should produce more task-irrelevant variance than:

```text
raw portfolio entry
    -> fixed task classification
    -> fixed routing rules
    -> canonical local authority
    -> reasoning
```

when the routing rules are appropriate to the task.

## Nuisance variables the router attempts to control

- repository discovery order;
- which similarly named project is opened first;
- stale prior-chat assumptions;
- historical artifacts encountered before current authority;
- lexical similarity between unrelated projects;
- provider-specific onboarding conventions;
- unnecessary context breadth;
- arbitrary cross-project expansion.

The experiment does **not** attempt to eliminate:

- legitimate interpretive disagreement;
- differences in model capability;
- differences caused by model updates;
- uncertainty inherent in the task;
- useful creative variation.

## Conditions

### Condition A — Unrouted baseline

Provide:

- the same user task;
- the public profile repository as the starting point;
- no explicit routing instruction beyond ordinary repository access.

The model chooses its own orientation path.

### Condition B — Routed

Provide:

- the same user task;
- the same repository snapshot;
- `AI_START_HERE.md`;
- `data/ai-orientation-router.json`;
- ordinary provider adapter if naturally discovered.

The model must follow the narrowest justified route before broader exploration.

## Fixed inputs

Before execution, freeze:

- task set;
- repository commit SHAs;
- router version;
- provider/model identifiers;
- whether prior conversation context is available;
- tool permissions;
- maximum run count;
- scoring rubric;
- human raters, if used.

A model update creates a new comparison stratum rather than silently replacing an earlier model identity.

## Suggested task families

1. **Named-local task**  
   Example: "Explain what TRACE is and what it is not."

2. **Cross-project distinction task**  
   Example: "Should Hermeneia and Performance Manuscript be merged?"

3. **Routing task**  
   Example: "Which project should handle persistent human intent across changing models?"

4. **Historical-vs-current authority task**  
   Ask a question where an old prototype exists but does not hold current authority.

5. **Current-state task**  
   Ask what work is currently authorized in ChessHeat or another preregistered project.

6. **Ambiguous-vocabulary task**  
   Use terms like provenance, authority, or continuity that occur across several repositories.

## Primary outcome measures

Score each run for:

- **route accuracy** — did the system enter the correct repository or candidate branch?
- **canonical-source coverage** — did it consult the required current authority?
- **authority-order violations** — did historical or summary material override canonical local state?
- **false equivalence rate** — did it infer shared ontology/product identity from shared vocabulary?
- **unsupported consolidation rate** — did it recommend merger/framework extraction without local evidence?
- **current-state accuracy** — did it distinguish current, proposed, historical, reverted, blocked, and validated states?
- **uncertainty discipline** — did it say insufficient orientation when required?
- **context efficiency** — how many repositories/files were loaded before a supported answer was possible?

## Response-variability measures

Do not use raw wording similarity as the main metric.

Prefer structured comparison of:

- selected route;
- cited/used authority files;
- project identity classification;
- current-state classification;
- boundary claims;
- recommended next action;
- unsupported claims.

A semantic-dispersion measure may be added, but it should not punish stylistic diversity when the governed conclusions are equivalent.

## Repeated-run design

For each provider/model/version/task/condition:

- run multiple fresh sessions;
- prevent conversational carryover unless testing carryover explicitly;
- preserve raw outputs;
- record model identifier and date;
- record files accessed where tooling exposes that evidence;
- score without changing the rubric after results are visible.

The initial sample size should be frozen before execution.

## Interpretation rule

A lower-variance result is not automatically a better result.

The router succeeds only if it reduces **task-irrelevant** variance while maintaining or improving:

- route correctness;
- canonical-source use;
- local semantic fidelity;
- uncertainty discipline.

A router that forces consistent but wrong answers fails.

## Candidate falsifiers

The hypothesis is weakened or falsified if:

- routed runs are no more accurate than baseline runs;
- the router systematically sends ambiguous tasks to the wrong project;
- reduced variance comes mainly from suppressing legitimate uncertainty;
- routing adds enough context overhead to increase cross-project contamination;
- model capability dominates routing so strongly that the router has no measurable effect;
- provider-specific adapters create inconsistent authority despite the shared canonical router.

## Why TRACE is the right home

This experiment directly tests TRACE principles:

- durable handoffs over conversational continuity;
- explicit authority boundaries;
- repository-backed institutional memory;
- provider neutrality;
- reproducible preflight;
- preserving evidence before interpretation.

The router itself should remain outside TRACE's core protocol until repeated evidence shows that the pattern generalizes.
