# Orientation Lineage — Reproducibility and Error Localization

**Repository:** TRACE  
**Status:** `PREREGISTRATION_DRAFT_ONLY`  
**Execution authorized:** no  
**Study:** 2 in the orientation research program

## Abstract

Agent-assisted inquiry becomes more scientifically interpretable when orientation, authority selection, evidence acquisition, and their observable lineage are externalized as experimental conditions rather than left as hidden preprocessing.

This study asks whether preserving that lineage improves an independent reviewer's ability to reconstruct inquiry conditions, detect authority violations, and localize where two agent-assisted inquiry trajectories first observably diverged.

The study does **not** attempt to capture private chain-of-thought.

## Independence from Study 1

Study 1 is:

`experiments/orientation-variance/PREREGISTRATION_DRAFT.md`

Its research question is:

> Does constrained orientation reduce task-irrelevant variance?

This study asks a different question:

> Does preserved orientation lineage improve reproducibility and error localization?

The studies are independent.

- Study 1 may succeed while Study 2 fails.
- Study 2 may succeed while Study 1 fails.
- A lower-variance answer is not automatically more reproducible.
- A more diagnosable inquiry trajectory does not require identical answers.

Study 1's preregistration is not modified by this study.

## Research question

Does explicit, observable orientation lineage improve the ability of independent reviewers to reconstruct, explain, and localize differences in agent-generated outputs?

## Experimental object

The unit of analysis is an **inquiry trajectory**, represented externally as:

```text
Task
  -> Scope / Route
  -> Authority Selection
  -> Evidence Acquisition
  -> Access Ordering
  -> Bounded Interpretation
  -> Output
```

Only the externally observable conditions are treated as lineage evidence.

Private internal reasoning is outside the measurement boundary.

## Declared versus observed lineage

The study distinguishes:

```text
declared trajectory
!=
observed trajectory
```

Declared lineage includes the model's externally stated route, authority claims, uncertainty, and brief route rationale.

Observed lineage includes instrumented repository access, artifact identity, access order, tool-visible actions, environment metadata, and human intervention where the execution surface exposes them.

A model's description of what it used does not certify the observed trajectory.

When declared and observed lineage disagree, both are preserved.

## Observation boundary

Observed lineage is only as complete as the instrumentation.

Every run record must therefore state:

- telemetry source;
- whether the instrumented surface is complete, partial, or unknown;
- known blind spots.

Absence from a partial trace must not be interpreted as proof that an event did not occur.

Records with insufficient telemetry may remain valid evidence of what *was* observed, but they are excluded from any primary analysis that requires proof of complete lineage equivalence.

## Orientation-lineage schema

Run records use:

`schemas/orientation-lineage.schema.json`

Draft schema version:

`0.1.0`

The schema preserves raw run conditions and may also include a derived lineage signature over:

```text
L = (T, R, A, E, O, I, P)
```

where:

- `T` = task identity;
- `R` = route / router state;
- `A` = authority artifacts;
- `E` = evidence artifacts;
- `O` = observable access order;
- `I` = instruction environment;
- `P` = permissions / tool surface.

The signature is a comparison aid, not a replacement for the raw lineage record.

A partial or unknown component must remain explicit rather than being silently hashed as if complete.

## Primary hypotheses

### H1 — Reconstruction

Reviewers given output + orientation lineage will reconstruct frozen inquiry conditions more accurately than reviewers given output alone.

### H2 — Divergence localization

Reviewers given output + orientation lineage will identify the first **observable** divergence between paired runs more accurately than reviewers given output alone.

### H3 — Authority violation detection

Reviewers given lineage will detect controlled authority-order violations more accurately than reviewers without lineage.

### H4 — Reviewer agreement

Independent reviewer agreement on divergence classification will be higher when orientation lineage is available.

## Secondary / exploratory questions

Exploratory analyses may examine:

- time required to localize a divergence;
- model-version drift diagnosis;
- declared-versus-observed mismatch frequency;
- whether access-order differences predict output differences;
- whether identical lineage signatures are associated with semantically equivalent outputs;
- whether excessive lineage detail harms reviewer performance.

These analyses are secondary unless promoted before execution through a new frozen protocol version.

## Divergence taxonomy

The primary localization target is the **first observable divergence**, not a claim about hidden cognition.

Allowed classes are:

1. **scope / route divergence**  
   Different routing or project-selection state.

2. **authority divergence**  
   Different authority artifacts, versions, or authority order.

3. **evidence divergence**  
   Different evidence sets or evidence versions.

4. **ordering divergence**  
   Materially different observable acquisition order with otherwise matched evidence sets.

5. **environment divergence**  
   Different instruction environment, permissions surface, provider/model identity, or other frozen execution condition.

6. **human-intervention divergence**  
   Different human override or intervention in the observable trajectory.

7. **matched-observable-lineage output divergence**  
   Observable lineage is matched within the defined instrumentation boundary, but outputs differ materially.

8. **presentation-only divergence**  
   Wording or formatting differs while the governed substantive claims are equivalent under the frozen scoring rubric.

9. **insufficient telemetry**  
   The available record cannot support a defensible localization.

The class `matched-observable-lineage output divergence` must not be automatically renamed "reasoning divergence." TRACE does not observe private reasoning.

## Study design

The primary evaluation uses paired runs.

Each pair has a known or reconstructable relationship between inquiry conditions.

Two reviewer conditions are compared:

### Condition A — Output only

The reviewer receives:

- task identifier or task text as permitted by the protocol;
- final outputs;
- no orientation-lineage record.

### Condition B — Output + lineage

The reviewer receives:

- the same task material;
- the same final outputs;
- the orientation-lineage records permitted by the frozen protocol.

Reviewers are not told which divergence, if any, was intentionally introduced.

Pair order and run identifiers should be randomized where practical.

## Controlled perturbation set

The strongest ground-truth localization trials should intentionally vary one observable factor at a time while freezing the others as far as practical.

Candidate perturbations:

- route;
- authority artifact/version;
- evidence artifact/version;
- evidence access order;
- instruction environment;
- permissions/tool surface;
- model version, when exact versions are exposed;
- human override.

A perturbation trial is valid only if the intended difference and frozen controls are recorded before the outputs are reviewed.

## Naturalistic pairs

Naturalistic cross-model or repeated-session pairs may also be collected.

They are useful for ecological validity but do not automatically provide causal ground truth.

For naturalistic pairs, the study should report what the observed lineage supports rather than assigning an internal cause that was not measured.

## Frozen inputs required before execution

Before the first scored run, freeze:

- task set;
- repository commit SHAs;
- router version and hash where used;
- orientation-lineage schema version;
- instrumentation surface;
- provider/model identifiers to the extent exposed;
- instruction environments;
- permissions/tool surfaces;
- controlled perturbation matrix;
- number of repeated runs;
- reviewer count;
- reviewer assignment process;
- scoring rubric;
- semantic-equivalence rubric for presentation-only divergence;
- exclusion rules;
- analysis plan.

A model update creates a new model/version stratum. It must not silently replace an earlier identity.

## Primary outcome measures

### 1. Condition reconstruction accuracy

Proportion of frozen conditions correctly reconstructed by the reviewer.

Possible scored fields include:

- selected route;
- authority set;
- evidence set;
- material ordering difference;
- environment difference;
- human override presence.

### 2. First-observable-divergence localization accuracy

Proportion of paired trials where the reviewer correctly identifies the earliest divergence class supported by the controlled record.

### 3. Authority-violation detection

At minimum report:

- true positives;
- false positives;
- true negatives;
- false negatives.

The final frozen analysis may select a summary measure such as balanced accuracy before execution.

### 4. Reviewer agreement

Use an agreement statistic appropriate to the number of reviewers and label structure.

The exact statistic must be frozen before execution.

## Ground truth

Primary localization ground truth should come from deliberately controlled perturbations and the preserved execution record.

The model's self-report is not ground truth.

For naturalistic runs, use "supported localization" rather than causal ground truth when the record cannot establish causality.

## Lineage signature

The schema supports an optional derived lineage signature.

Its purpose is mechanical comparison, not epistemic authority.

The signature should expose component hashes for:

- task;
- route;
- authority;
- evidence;
- order;
- instruction environment;
- permissions surface.

A top-level signature value must not be interpreted without its component status and raw lineage record.

Before execution, the project must freeze:

- canonicalization method;
- hash algorithm;
- component sorting rules;
- treatment of null / unknown values;
- signature version.

If any required component is not adequately observed, the signature basis must be marked partial or not computed.

## Exclusions

Exclude a trial from an analysis requiring complete observed lineage when:

- telemetry completeness is unknown or partial for the required stage;
- required repository/artifact identities cannot be reconstructed;
- the run record fails schema validation;
- the task or frozen condition was changed after output inspection;
- a supposedly single-factor controlled perturbation unintentionally changed another frozen primary condition and cannot be repaired without post-hoc judgment.

Excluded trials remain preserved with the exclusion reason.

## Chain-of-thought boundary

This study does not request, store, infer, or score private chain-of-thought.

Allowed model-authored material is limited to externally declared artifacts such as:

- selected route;
- stated authority;
- declared uncertainty;
- concise route-rationale summary;
- final answer.

The scientific target is the observable inquiry envelope, not hidden cognition.

## Interpretation rules

A positive Study 2 result means lineage improved reconstruction or diagnosis under the frozen protocol.

It does **not** establish that:

- the underlying answers were correct;
- the router improved accuracy;
- identical lineage causes identical answers;
- model internals became reproducible;
- private reasoning was recovered;
- the lineage schema captures every relevant causal variable.

Likewise, different outputs under matched observable lineage establish an output difference under the measured inquiry envelope. They do not by themselves establish why the model internally diverged.

## Candidate falsifiers

The central proposition is weakened if:

- lineage does not improve reconstruction accuracy;
- lineage does not improve first-divergence localization;
- reviewers become more confident but not more accurate;
- authority violations are not more detectable;
- reviewer agreement does not improve;
- instrumentation gaps make "observed lineage" too incomplete to support the intended claims;
- lineage signatures classify materially different inquiry envelopes as equivalent;
- the capture burden materially changes the inquiry behavior being measured;
- the lineage record is too complex for independent reviewers to use reliably.

## Relationship to Hermeneia

TRACE owns the reproducibility record for the inquiry trajectory.

Hermeneia may later study how interpretations develop from preserved inquiry conditions.

This study does not merge the two responsibilities.

```text
TRACE
  -> what observable inquiry conditions existed and where trajectories diverged

Hermeneia
  -> how understanding developed, differed, survived challenge, or received stewardship
```

## Evidence preservation

For every included and excluded run, preserve where permitted:

- task identity;
- repository snapshot identifiers;
- schema version;
- lineage record;
- raw final output;
- controlled perturbation assignment;
- reviewer judgments;
- exclusion reason;
- analysis artifacts.

Corrections create a new record or protocol version rather than silently rewriting the original evidence.

## Execution gate

Execution is **not authorized** by this draft.

Before any scored run:

1. validate the schema against representative fixtures;
2. freeze the signature derivation or explicitly defer signatures;
3. freeze the controlled perturbation set;
4. freeze the reviewer rubric;
5. freeze sample size and repetition counts;
6. freeze the statistical analysis plan;
7. verify the instrumentation can actually observe the stages claimed by the study.

Only then should the study move from preregistration draft to an executable frozen protocol.
