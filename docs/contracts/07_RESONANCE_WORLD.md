# Stage Contract 07 — Resonance (World)

## Metadata
- Stage ID: 07
- Stage Name: Resonance (World)
- Layer: Boundary calibration
- Version: v0.2
- Status: Reviewed
- Reviewed on: 2026-05-06
- Owners: QA/review lead
- Reviewers: Protocol editor

## Review notes (v0.2)
- Invariant "external contradiction has priority over internal satisfaction" is the load-bearing rule; aligned with rubric D7 and with the non-substitution principle in `BENCHMARK_BRIDGE.md`.
- Verdict enum (`validated` / `partial` / `invalidated`) matches the `world_verdict` field in `cycle_trace.schema.json`.
- Recovery protocol re-enters at stage 00 with contradiction-informed assumptions, closing the loop into the next cycle.
- Open question deferred: whether "external validation channel" should require a typed taxonomy (e.g., user feedback, downstream metric, third-party audit). Left untyped for v0.2 because worked examples already demonstrate diverse channels.

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
