# TRACE Case Studies

TRACE case studies are chronological evidence records, not polished success stories.

Their purpose is to test whether TRACE's proposed invariants survive real projects with real failures, changing implementations, external execution environments, and incomplete information.

## Case-study rules

1. **Preserve chronology.** Record what was known before execution separately from what was learned afterward.
2. **Do not retrofit success criteria.** Criteria frozen before observing a result must remain distinguishable from later interpretation.
3. **Link to primary artifacts.** Issues, commits, pull requests, manifests, logs, fingerprints, and review records outrank recollection.
4. **Negative results count.** A clean falsification is evidence about the protocol and the project, not a failed case study.
5. **Implementation confidence is not validation.** Tests, mutation evidence, review, and execution evidence should remain attributable to their own stages.
6. **Execution evidence is not interpretation.** Measurements and model outputs should be preserved before conclusions are added.
7. **Corrections remain visible.** If a case-study record is later corrected, the correction should state what changed and why rather than silently rewriting the historical claim.
8. **Do not import private or held-out source material merely to make the case study readable.** Reference durable fingerprints and repository artifacts instead.

## Cases

- [001 — Performance Manuscript](001-performance-manuscript/README.md) — in progress; real-manuscript two-model execution not yet recorded.
