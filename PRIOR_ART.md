# Prior Art and Naming Collision

## External TRACE paper (2026)

A separate research project now uses the same acronym:

- Edward Y. Chang and Emily J. Chang, *TRACE: An Operational Reasoning Schema for Auditable Agentic Commitments* (2026)
- Expansion: **Typed Reasoning And Commitment Evidence**
- arXiv: https://arxiv.org/abs/2607.12480

This is **not** the same project as this repository:

- this repository: **Transparent, Reproducible Agentic Collaboration & Experimentation**
- external paper: **Typed Reasoning And Commitment Evidence**

The naming collision should remain explicit in future writing, citations, search, and publication.

## Relevant convergence

Despite being independent projects, the external TRACE paper overlaps several concerns in this repository:

```text
durable record
versioned state
append-only revision
measurement gates
evidence before commitment
consumer obligations
auditable downstream reuse
```

The external paper's operating discipline — **no durable state change without a record** — is especially close to this repository's existing emphasis on durable state, immutable fingerprints, preserved execution evidence, and separation of evidence from interpretation.

This convergence is useful prior art, not evidence that either project subsumes the other.

## Important differences

This repository is currently a lightweight protocol for **human + agent collaboration and experimental governance** across an end-to-end lifecycle:

```text
Intent
→ Freeze
→ Implement
→ Review
→ Preflight
→ Execute
→ Interpret
```

The external TRACE paper is centered on a **typed reasoning/commitment record and downstream consumer contracts**.

Therefore:

```text
external TraceRecord
!= this TRACE protocol
```

but:

```text
external TraceRecord
may implement one durable-record mechanism inside a TRACE-governed workflow
```

## Reuse opportunity

Before this repository creates a proprietary reasoning-record schema, compare against the external TRACE paper's:

- `TraceRecord`;
- causal specialization;
- eight-stage writer;
- gate-first measurement regime;
- append-only revisions;
- commitment/defer semantics;
- consumer contracts;
- TRACE-Bench methodology.

If those constructs satisfy a recurring need, inherit or adapt them rather than duplicating them.

## Boundary

A durable reasoning record is still not automatically:

```text
correct reasoning
!= valid evidence
!= authorization
!= successful execution
!= intended outcome
```

This repository's existing separation between execution evidence and later human interpretation remains necessary.

## Best next research question

Can an existing real TRACE lifecycle case emit an external TRACE-style `TraceRecord` at the Freeze, Preflight, or Execute boundary and improve handoff/auditability without adding process burden that exceeds the risk being controlled?

Do not add a record type merely because the acronyms match. Require a concrete repeated need.
