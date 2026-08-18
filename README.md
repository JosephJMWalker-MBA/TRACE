# TRACE

**Transparent, Reproducible Agentic Collaboration & Experimentation**

TRACE is a provider-neutral development protocol for human + agent teams working on consequential software, research, and experiments.

Its central premise is simple:

> **Build projects that can explain why they are the way they are without requiring access to the minds that built them.**

Version control preserves code. TRACE is concerned with preserving enough **reasoning, intent, evidence, and decision boundaries** that a project can survive changes in people, models, sessions, tools, and hardware.

## Why TRACE exists

Agentic development can move quickly while quietly accumulating fragile assumptions:

- project state exists only in a chat session or temporary directory;
- an implementation agent evaluates its own work;
- success criteria drift after results are visible;
- important inputs change without a durable fingerprint;
- failures are overwritten instead of preserved as evidence;
- a future agent cannot tell why a decision was made;
- execution output is treated as interpretation rather than evidence.

TRACE treats these as governance and reproducibility problems, not merely prompting problems.

## Core architecture

```text
Human Owner
  intent / judgment / accountability
        |
        v
Architect / Reviewer
  boundaries / protocol / critique
        |
        +-------------------+
        |                   |
        v                   v
Implementation Agent     Frozen Protocol
  code / tests / PR        precommitted rules
        |                   |
        +---------+---------+
                  |
                  v
            Merge Boundary
                  |
                  v
          Execution Worker
       model / hardware / world
                  |
                  v
               Evidence
                  |
                  v
         Human Interpretation
                  |
                  +----> next cycle
```

The roles are logical, not necessarily different people or products. The important requirement is that their responsibilities remain distinguishable.

## What TRACE protects

TRACE is designed around several separations:

- **Intent is not implementation.**
- **Implementation is not validation.**
- **Execution is not interpretation.**
- **Evidence is not authority.**
- **Failure is not disposable.**
- **Project memory is not a model session.**

These separations make it easier to use capable agents without requiring any agent to be infallible.

## Lifecycle

TRACE uses a seven-stage cycle:

1. **Intent** — state the question, goal, constraints, and decision owner.
2. **Freeze** — precommit criteria that should not change after results are visible.
3. **Implement** — build the smallest system capable of testing the frozen intent.
4. **Review** — inspect implementation independently of the implementing agent's confidence.
5. **Preflight** — verify environment, identities, inputs, digests, persistence, and execution readiness.
6. **Execute** — run the experiment or system while preserving logs and artifacts.
7. **Interpret** — distinguish observations from conclusions and decide what changes next.

See [`PROTOCOL.md`](PROTOCOL.md) for the operational version.

## Principles

The protocol is intentionally small. Its current invariants are documented in [`PRINCIPLES.md`](PRINCIPLES.md), including:

- durable state over temporary state;
- explicit responsibility boundaries;
- freeze before observation;
- immutable fingerprints for consequential inputs;
- evidence separated from interpretation;
- independent review;
- reproducible preflight;
- durable handoffs;
- failure preservation;
- repository-backed institutional memory.

## What TRACE is not

TRACE is **not** currently:

- an agent framework;
- an orchestration engine;
- a replacement for Git, CI, testing, or scientific method;
- tied to Claude, GPT, Gemini, Ollama, GitHub, or any particular provider;
- a claim that every project requires heavyweight process.

The protocol should remain lighter than the risk it is controlling.

## Current maturity

**Status: experimental / pre-specification.**

TRACE is being extracted from real development work rather than designed as a framework first. Practices should become protocol-level only after they survive reuse across materially different projects.

The first reference case is expected to come from the Performance Manuscript experiment. Additional cases can test whether the same boundaries generalize to projects such as DRAGON and Pyxis.

## Development rule

> **Formalize repeated reasoning before automating repeated mechanics.**

Code belongs here only after repeated use shows that a mechanism is genuinely invariant rather than an accident of one project.

## Repository direction

Near-term work should favor:

- protocol refinement;
- role definitions;
- lifecycle checklists;
- manifests and evidence templates;
- case studies;
- counterexamples and failure analysis.

Tooling can follow once the protocol has earned it.
