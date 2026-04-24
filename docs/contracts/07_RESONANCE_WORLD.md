# Stage Contract 07 — Resonance (World)

## Metadata
- Stage ID: 07
- Stage Name: Resonance (World)
- Layer: Boundary calibration
- Version: v0.1
- Status: Draft
- Owners: QA/review lead
- Reviewers: Protocol editor

## Intent
Close the loop by validating outcomes against external reality feedback.

## Inputs
- Required: trajectory assessment, evidence links
- Optional: stakeholder feedback, external metrics

## Preconditions (MUST)
- External validation channel is identified.
- Success/failure criteria are defined before reading outcomes.

## Invariants (MUST hold during stage)
- External contradiction has priority over internal satisfaction.
- Completion claim requires world-facing evidence.

## Anti-patterns (MUST NOT)
- Marking cycle complete on internal confidence alone.
- Discarding contradictory feedback without documented rationale.

## Outputs
- Mandatory: world-feedback report, cycle verdict (validated/invalidated/partial)
- Optional: next-cycle recalibration notes

## Exit criteria
- Verdict is evidence-backed and reproducible.
- If invalidated, next-cycle entry conditions are explicit.

## Evidence artifacts
- external feedback packet
- validation decision record

## Failure signals
- No external signal used.
- Completion declared without contradiction handling.

## Recovery protocol
Reject completion, reopen cycle at Resonance (Self) with contradiction-informed assumptions.

## Hand-off contract
- Next stage: 00 Resonance (Self) (new cycle)
- Hand-off payload: world-feedback report + recalibration inputs
- Hand-off quality checks: next cycle starts with explicit learning transfer
