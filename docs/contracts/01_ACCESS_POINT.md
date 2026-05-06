# Stage Contract 01 — Access Point

## Metadata
- Stage ID: 01
- Stage Name: Access Point
- Layer: Entry and composition
- Version: v0.2
- Status: Reviewed
- Reviewed on: 2026-05-06
- Owners: Protocol editor
- Reviewers: Example lead

## Review notes (v0.2)
- Two-candidate-minimum precondition makes "selection by team habit only" detectable; aligns with rubric D1.
- Inputs match the mandatory outputs of `00 Resonance (Self)`; hand-off contract preserved.
- Recovery protocol explicitly returns to stage 00, which matches the failure-handling pattern across the loop.
- Open question deferred: whether the rejected-alternatives log should be a separate artifact or embedded in the decision table; treated as an editorial choice for now.

## Intent
Identify the true entry anchor that is causally relevant to the objective.

## Inputs
- Required: calibration statement, uncertainty register
- Optional: incident history, stakeholder constraints

## Preconditions (MUST)
- At least two candidate entry points are compared.
- Entry point selection rationale is explicit.

## Invariants (MUST hold during stage)
- Selection is based on relevance, not convenience.
- Rejected entry points are documented with reasons.

## Anti-patterns (MUST NOT)
- Choosing the most visible symptom as the anchor.
- Selecting entry point by team habit only.

## Outputs
- Mandatory: selected entry point + rejected alternatives
- Optional: confidence rationale

## Exit criteria
- Selection rationale can be independently reviewed.
- The selected anchor maps to objective constraints.

## Evidence artifacts
- entry-point decision table

## Failure signals
- Only one candidate considered.
- No causal argument linking anchor to objective.

## Recovery protocol
Return to Resonance (Self), re-evaluate assumptions, then re-run candidate comparison.

## Hand-off contract
- Next stage: 02 Assembly
- Hand-off payload: selected anchor + rationale
- Hand-off quality checks: downstream assembler can explain relevance boundaries
