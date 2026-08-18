# Case Study 001 — Evidence Register

This file is the evidence-first boundary for TRACE Case Study 001.

It is not a narrative and it does not decide whether the experiment succeeded. Its job is to preserve what artifact existed, what role it played, when it entered the chronology, and whether it was available before or only after real-manuscript inference.

## Evidence classes

- **PRE** — existed before the first real-manuscript inference request.
- **RUN** — produced by the actual execution.
- **HUMAN** — produced by human verification of frozen run artifacts.
- **INTERPRETATION** — derived conclusion; belongs only after RUN/HUMAN evidence is frozen.

A later conclusion must not be promoted into PRE evidence merely because it explains an earlier event well.

## Pre-execution register

| Class | Artifact | Role | Durable reference | Status before real inference |
|---|---|---|---|---|
| PRE | Product Trial 01 | Product failure/pressure that motivated the new experiment | Performance Manuscript issue #64 | concluded before #65 |
| PRE | Experiment charter | Intent, non-goals, stop conditions, acceptance question | Performance Manuscript issue #65 | open; authoritative experiment charter |
| PRE | Orin capability preflight | Device/runtime measurements and structured-output probe | issue #65 comment `5299088226` | recorded before implementation run |
| PRE | Semantic proposal architecture | Deterministic packetization, validation, sidecars, comparison, routing | merged PR #66 | merged before real inference |
| PRE | Real-manuscript execution freeze | Precommitted execution protocol | issue #65 comment `5334293496` | frozen before real inference |
| PRE | Prompt-safety + retry hardening | Removes source-newline prompt ambiguity; implements frozen retry/evidence policy | draft PR #67 | in review; no manuscript inference in PR |

## Pre-execution facts that must remain distinguishable from later results

- The acceptance question was written before the real run.
- A negative answer was explicitly allowed.
- Local-model proposals were not permitted to mutate canonical attribution automatically.
- Both models were to evaluate the same frozen question universe.
- Model identity required immutable digest-level binding, not merely a tag.
- The deterministic baseline was comparison evidence and was excluded from inference prompts.
- Contract-invalid model output was failure evidence, not material to repair or partially salvage.
- Human review was intended to prioritize disagreements, failures, identity-missing cases, baseline contradictions, and a deterministic audit sample rather than replay every decision.
- Execution telemetry was separated from deterministic proposal artifacts when retry evidence was added.

## Run evidence — intentionally empty until execution

Do not populate this section from estimates, smoke tests, deterministic packet planning, or expectations.

When the real run occurs, record immutable references where available:

| Class | Artifact | Required binding/evidence | Reference | Recorded value |
|---|---|---|---|---|
| RUN | source specimen | work id + source fingerprint + raw hash where permitted | pending | pending |
| RUN | code under execution | exact commit SHA | pending | pending |
| RUN | packet policy | version + fingerprint + packet/target universe | pending | pending |
| RUN | Qwen model | runtime + full digest + quantization + settings fingerprint | pending | pending |
| RUN | Gemma model | runtime + full digest + quantization + settings fingerprint | pending | pending |
| RUN | Qwen proposal artifact | source/policy/model/settings bindings + final packet outcomes | pending | pending |
| RUN | Qwen execution log | per-attempt outcomes, timing, token evidence | pending | pending |
| RUN | Gemma proposal artifact | source/policy/model/settings bindings + final packet outcomes | pending | pending |
| RUN | Gemma execution log | per-attempt outcomes, timing, token evidence | pending | pending |
| RUN | agreement artifact | same question universe + two distinct model identities | pending | pending |
| RUN | review-routing artifact | manuscript binding + frozen audit rule | pending | pending |

## Human verification evidence — intentionally empty until review

Record only what the reviewer actually checked and changed. Do not infer human accuracy from model agreement.

| Class | Measurement | Reference | Recorded value |
|---|---|---|---|
| HUMAN | items reviewed | pending | pending |
| HUMAN | human corrections to model proposals | pending | pending |
| HUMAN | review duration | pending | pending |
| HUMAN | seconds per checked item | pending | pending |
| HUMAN | false confident agreements found in audit | pending | pending |
| HUMAN | residual genuinely unresolved cases | pending | pending |

## Interpretation gate

Interpretation may begin only after the relevant RUN and HUMAN rows above point to durable artifacts or explicitly state why an artifact does not exist.

The eventual analysis should answer at least four separate questions:

1. **Product:** Did the workflow move the human from primary resolver toward verifier?
2. **Model:** How did the two local models differ in validity, agreement, and reviewed correctness?
3. **System:** Did the governance boundaries refuse malformed or unsupported output without contaminating canonical state?
4. **TRACE:** Which TRACE principles were genuinely useful, which were ceremonial, and which important boundary was missing?

A favorable product result does not automatically validate TRACE, and a negative model-quality result does not automatically falsify the governance protocol.

## Correction log

Use this section for factual corrections to this evidence register after creation. Do not silently alter historical chronology.

- Initial register created before the real-manuscript execution was recorded in TRACE.
