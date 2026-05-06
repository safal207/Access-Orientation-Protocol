# Stage Contract 05 — Movement

## Metadata
- Stage ID: 05
- Stage Name: Movement
- Layer: Action and observation
- Version: v0.2
- Status: Reviewed
- Reviewed on: 2026-05-06
- Owners: Example lead
- Reviewers: QA/review lead

## Review notes (v0.2)
- "Deviations are logged at the moment they occur" is the invariant that prevents the "silent recovery" anti-pattern flagged by rubric D5/D8.
- Recovery protocol routes back to either Orientation or Transition depending on drift source; this matches the multi-target rollback observed in worked examples (e.g., `human_team`, `ai_agent`).
- Hand-off payload to `06 Trajectory` includes deviation/correction records, which trajectory analysis depends on.
- Open question deferred: whether "high activity with no directional progress" should be tied to a quantitative threshold or remain qualitative. Kept qualitative for v0.2 to avoid premature numericization.

## Intent
Execute action from centered orientation instead of panic, inertia, or compulsion.

## Inputs
- Required: approved transition plan, trigger checklist
- Optional: operating telemetry, guardrail thresholds

## Preconditions (MUST)
- Movement objective is explicit and measurable.
- Guardrails for safe execution are declared.

## Invariants (MUST hold during stage)
- Action remains aligned with orientation priorities.
- Deviations are logged at the moment they occur.

## Anti-patterns (MUST NOT)
- Blind execution after context drift.
- Escalating effort to compensate for direction loss.

## Outputs
- Mandatory: movement log, deviation log
- Optional: correction notes

## Exit criteria
- Movement outcomes are traceable to initial objective.
- Deviations and corrections are reviewable.

## Evidence artifacts
- action run log
- guardrail event log

## Failure signals
- High activity with no directional progress.
- Repeated deviations without correction decisions.

## Recovery protocol
Pause movement, re-enter Orientation or Transition depending on drift source.

## Hand-off contract
- Next stage: 06 Trajectory
- Hand-off payload: movement log + deviation/correction records
- Hand-off quality checks: observer can reconstruct motion pattern over time
