# Stage Contract 03 — Orientation

## Metadata
- Stage ID: 03
- Stage Name: Orientation
- Layer: State organization
- Version: v0.2
- Status: Reviewed
- Reviewed on: 2026-05-06
- Owners: Protocol editor
- Reviewers: Example lead

## Review notes (v0.2)
- "Orientation remains relational, not just task listing" is the load-bearing invariant; the anti-pattern entry against checklist-conversion makes it falsifiable.
- Aligned with rubric D3 (Orientation depth) and with the architectural principle that orientation is broader than planning.
- Hand-off to `04 Transition` provides the prioritized direction set required by the next contract's Inputs.
- Open question deferred: whether trade-off documentation should be a separate evidence artifact rather than a sub-section of the orientation map.

## Intent
Restore internal coordinates: relation, direction, and priority structure.

## Inputs
- Required: curated assembly set, relevance map
- Optional: historical trajectories

## Preconditions (MUST)
- Key entities and relationships are explicitly mapped.
- Direction hypotheses are written and ranked.

## Invariants (MUST hold during stage)
- Orientation remains relational (not just task listing).
- Trade-offs are explicit when priorities conflict.

## Anti-patterns (MUST NOT)
- Converting orientation into a generic checklist.
- Ignoring conflicts between constraints.

## Outputs
- Mandatory: orientation map, prioritized direction set
- Optional: decision boundary notes

## Exit criteria
- Map is legible to an external reviewer.
- Priorities align with selected anchor and assembly evidence.

## Evidence artifacts
- orientation map document

## Failure signals
- Pure task list with no relational model.
- Priority claims without trade-off analysis.

## Recovery protocol
Rebuild relation map from assembly set and repeat prioritization with explicit criteria.

## Hand-off contract
- Next stage: 04 Transition
- Hand-off payload: orientation map + prioritized directions
- Hand-off quality checks: transition plan can be derived without reinterpretation
