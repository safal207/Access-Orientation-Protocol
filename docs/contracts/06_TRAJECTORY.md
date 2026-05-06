# Stage Contract 06 — Trajectory

## Metadata
- Stage ID: 06
- Stage Name: Trajectory
- Layer: Action and observation
- Version: v0.2
- Status: Reviewed
- Reviewed on: 2026-05-06
- Owners: QA/review lead
- Reviewers: Protocol editor

## Review notes (v0.2)
- "Judgments on temporal patterns, not isolated events" defends against "illusory trajectory" from `STRESS_TEST.md`; rubric D6 alignment confirmed.
- Observation-window precondition is the falsifiable check that an external reviewer can run.
- Hand-off to `07 Resonance (World)` correctly carries trajectory assessment + evidence links for external validation.
- Open question deferred: whether "drift thresholds" should be standardized across system types or kept context-specific. Kept context-specific to preserve cross-system applicability.

## Intent
Observe and evaluate the pattern of movement over time, not just single-step outputs.

## Inputs
- Required: movement log, deviation/correction records
- Optional: historical baseline, benchmark traces

## Preconditions (MUST)
- Observation window and sampling method are defined.
- Evaluation criteria for drift/stability are explicit.

## Invariants (MUST hold during stage)
- Judgments are made on temporal patterns, not isolated events.
- Signal and noise are explicitly separated in analysis.

## Anti-patterns (MUST NOT)
- Declaring success from one positive snapshot.
- Ignoring slow drift because near-term outputs look good.

## Outputs
- Mandatory: trajectory assessment, drift/stability findings
- Optional: reorientation recommendation

## Exit criteria
- Pattern assessment is reproducible from logs.
- Drift thresholds and interpretations are explicit.

## Evidence artifacts
- trajectory report
- trend chart or comparable temporal summary

## Failure signals
- No observation horizon defined.
- Conclusions cannot be traced back to timeline evidence.

## Recovery protocol
Extend observation window and rerun trajectory analysis with explicit thresholds.

## Hand-off contract
- Next stage: 07 Resonance (World)
- Hand-off payload: trajectory assessment + evidence links
- Hand-off quality checks: validator can test claims against external response
