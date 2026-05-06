# Stage Contract 00 — Resonance (Self)

## Metadata
- Stage ID: 00
- Stage Name: Resonance (Self)
- Layer: Boundary calibration
- Version: v0.2
- Status: Reviewed
- Reviewed on: 2026-05-06
- Owners: Protocol editor
- Reviewers: QA/review lead

## Review notes (v0.2)
- Anti-pattern coverage verified against `docs/STRESS_TEST.md`: "false self-resonance" addressed by the invariant pairing confidence with uncertainty; "skipped self-resonance" addressed by the anti-pattern against jumping directly to execution.
- Hand-off to `01 Access Point` is consistent with the Inputs section of the next contract.
- Outputs map to rubric D1 (Entry integrity) and to the `evidence` array of `cycle_trace.schema.json`.
- Open question deferred to next review cycle: whether a minimum granularity for the uncertainty register should be normative or remain advisory.

## Intent
Calibrate to actual internal state before selecting a problem entry point.

## Inputs
- Required: current objective context, state snapshot
- Optional: prior cycle notes, known constraints

## Preconditions (MUST)
- Internal state is explicitly recorded (not assumed).
- The system can name at least one uncertainty and one risk.

## Invariants (MUST hold during stage)
- No action-plan commitment is finalized before calibration.
- Confidence claims must be paired with uncertainty claims.

## Anti-patterns (MUST NOT)
- Jumping directly to execution tasks.
- Treating mood/urgency as evidence.
- Backfilling calibration after actions already started.

## Outputs
- Mandatory: calibration statement, uncertainty register
- Optional: readiness score

## Exit criteria
- Calibration statement is reviewable and concrete.
- Uncertainty register includes mitigation assumptions.

## Evidence artifacts
- `resonance_self.md` note
- uncertainty checklist

## Failure signals
- Vague or purely motivational language.
- No explicit uncertainty declared.

## Recovery protocol
Pause forward motion; rerun calibration with explicit constraints and assumptions.

## Hand-off contract
- Next stage: 01 Access Point
- Hand-off payload: calibration statement + uncertainty register
- Hand-off quality checks: reviewer can reconstruct why entry selection is safe
