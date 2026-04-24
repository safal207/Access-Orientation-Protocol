# Stage Contract 01 — Access Point

## Metadata
- Stage ID: 01
- Stage Name: Access Point
- Layer: Entry and composition
- Version: v0.1
- Status: Draft
- Owners: Protocol editor
- Reviewers: Example lead

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
