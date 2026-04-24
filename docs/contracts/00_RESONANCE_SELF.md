# Stage Contract 00 — Resonance (Self)

## Metadata
- Stage ID: 00
- Stage Name: Resonance (Self)
- Layer: Boundary calibration
- Version: v0.1
- Status: Draft
- Owners: Protocol editor
- Reviewers: QA/review lead

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
