# AI Onboarding Contract

**Status:** candidate TRACE pattern  
**Purpose:** make repository entry, task resumption, and handoff more accurate across AI systems without making any one model or vendor the project memory.

TRACE assumes that a future agent may begin with:

- no access to the prior chat;
- a different model or provider;
- a different tool harness;
- incomplete knowledge of repository history;
- stale external context;
- strong pattern-matching ability that can still collapse important project distinctions.

The repository must therefore carry enough orientation for a competent human or AI collaborator to recover the project's identity, current authority, boundaries, and next safe actions from durable artifacts.

> **Onboarding is not prompt decoration. It is part of reproducibility.**

## 1. Canonical authority

Provider-specific instruction files are discovery adapters, not independent sources of project truth.

For TRACE itself, use this authority order:

1. `README.md` — canonical project identity, purpose, maturity, and scope.
2. `PRINCIPLES.md` — protocol invariants.
3. `PROTOCOL.md` — operational lifecycle and stage boundaries.
4. `PRIOR_ART.md` — naming collision and relevant external prior art.
5. Task-specific issues, pull requests, manifests, case-study artifacts, or frozen records.
6. Conversation history only as supplementary context unless the relevant decision was durably recorded.

If two durable artifacts conflict, do not silently choose the one that best fits the current task. Identify the conflict and resolve authority before making a consequential change.

## 2. Cross-repository orientation

TRACE is one repository inside a larger portfolio.

Before making portfolio-level claims, consolidation proposals, cross-project ontology claims, or statements that one project subsumes another, read:

`JosephJMWalker-MBA/JosephJMWalker-MBA/PORTFOLIO_ORIENTATION.md`

The portfolio orientation file is a navigation layer. It does not outrank a project's own canonical source.

The required rule is:

```text
orient at portfolio level
        ->
read the named repository's canonical source
        ->
make the local decision from local authority
```

Shared words such as `evidence`, `provenance`, `authority`, `canonical`, `human review`, or `append-only` do not prove that two projects share an ontology, runtime, or product identity.

## 3. Minimal onboarding sequence

A new agent or collaborator should do only the reading required for the task, but should complete these checks before consequential work.

### A. Identify the task scope

State internally or in the work record:

- repository being changed;
- requested outcome;
- whether the task is local or cross-repository;
- whether the task changes code, protocol, research claims, evidence, public wording, or governance.

### B. Load the relevant authority

For a small documentation correction, the README and target file may be enough.

For protocol changes, read `PRINCIPLES.md` and `PROTOCOL.md`.

For cross-project reasoning, also read the portfolio orientation file and the canonical source of every named project.

For a consequential experiment, locate the frozen protocol, preflight record, and current execution boundary before acting.

Do not require every agent to read every document for every task.

### C. Verify current state

Do not infer current project state from:

- an old chat;
- repository name;
- one familiar file;
- a previous branch;
- a generated artifact;
- a model's remembered summary.

Check the current branch, relevant canonical file, and current issue/PR or status artifact when one exists.

### D. Preserve distinctions

Before changing anything, identify which distinctions matter to the task.

TRACE's recurring distinctions include:

- intent != implementation;
- implementation != validation;
- execution != interpretation;
- evidence != authority;
- observation != inference != decision;
- current authority != historical artifact;
- local project semantics != portfolio-wide vocabulary.

### E. Act within the smallest justified boundary

Do not broaden a local change into a framework, ontology, refactor, or portfolio merger merely because a reusable pattern appears.

Formalize a repeated reasoning pattern before automating repeated mechanics.

### F. Verify the result

For repository writes:

```text
read -> change -> commit -> fetch/inspect -> verify
```

Validation should be proportionate to consequence.

### G. Leave a durable handoff

If the work creates a consequential decision, unresolved blocker, frozen condition, new evidence, or next-step constraint, record it durably.

A future agent should not need the current conversation to learn:

- what changed;
- why it changed;
- what evidence supports it;
- what remains unresolved;
- what is not authorized next.

## 4. Accuracy rules for AI collaborators

An AI system working in a TRACE-oriented repository should:

- distinguish what it **read** from what it **inferred**;
- identify uncertainty instead of filling gaps with a plausible story;
- preserve negative results and reverted directions when they matter to interpretation;
- avoid upgrading a proposal, prototype, or experiment into a validated system claim;
- avoid treating implementation output as authority;
- avoid treating a shared design pattern as proof of a shared ontology;
- verify dates, counts, versions, and current status from repository evidence before repeating them as current facts;
- prefer exact project terms when a repository defines them;
- say **insufficient orientation** when the available canonical record does not support a confident synthesis.

## 5. Provider-neutral core, provider-specific adapters

TRACE does not require any particular AI provider.

Different agent systems currently discover repository instructions through different conventional files. As of 2026-09-27, this repository uses thin adapters for interoperability:

| Environment | Discovery adapter |
| --- | --- |
| OpenAI Codex and tools that honor Agents.md | `AGENTS.md` |
| Anthropic Claude Code | `CLAUDE.md` |
| Google Gemini CLI | `GEMINI.md` |
| GitHub Copilot | `.github/copilot-instructions.md` |

These adapters should stay short. They should point to canonical project sources rather than copy a second project definition into each vendor-specific file.

A future provider may ignore all of them. The repository must still remain understandable from ordinary durable documentation.

## 6. Adapter rule

A provider-specific instruction file may:

- tell the agent where canonical authority lives;
- identify task-dependent reading;
- state critical safety or governance boundaries;
- define verification expectations.

It should not:

- create a vendor-specific project ontology;
- override the canonical README or protocol;
- contain unique project decisions that exist nowhere else;
- assume the model has access to prior conversations;
- require excessive context loading for trivial tasks.

If an adapter and canonical project documentation disagree, canonical project documentation wins and the adapter should be corrected.

## 7. Handoff quality test

Before ending consequential work, ask:

> Could a capable agent from a different provider, with no access to this conversation, enter the repository tomorrow and accurately determine what happened, what is authoritative, what remains uncertain, and what it is allowed to do next?

If not, the handoff is incomplete.

## 8. TRACE research question

Cross-provider onboarding should itself be treated as an empirical protocol problem.

Useful future case-study questions include:

- Do different agents identify the same canonical project purpose?
- Do they preserve the same authority order?
- Do they correctly distinguish current state from historical state?
- Do they avoid false cross-project unification?
- Can they resume a bounded task without hidden conversational context?
- Which instructions materially improve accuracy, and which merely add context overhead?

The goal is not to make every model behave identically.

The goal is to make the repository sufficiently explicit that different capable systems can recover the same important constraints without relying on private conversational continuity.

## 9. Orientation-variance evaluation

The profile repository now uses a deterministic front-door router (`AI_START_HERE.md` plus a machine-readable routing map) to reduce arbitrary repository discovery choices before reasoning begins.

TRACE treats the effectiveness of that pattern as an empirical question rather than an assumption.

See:

`experiments/orientation-variance/PREREGISTRATION_DRAFT.md`

The experiment tests whether constrained orientation reduces task-irrelevant response variance across providers, model versions, and fresh sessions without merely making wrong answers more consistent.

