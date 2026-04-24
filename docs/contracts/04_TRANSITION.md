# Stage Contract 04 — Transition

## Metadata
- Stage ID: 04
- Stage Name: Transition
- Layer: State organization
- Version: v0.1
- Status: Draft
- Owners: Protocol editor
- Reviewers: QA/review lead

## Intent
Cross from orientation into an operative state without rupture or loss of coherence.

## Inputs
- Required: orientation map, prioritized direction set
- Optional: operational constraints, risk limits

## Preconditions (MUST)
- The target operative state is explicitly described.
- Transition trigger conditions are documented.

## Invariants (MUST hold during stage)
- Continuity is preserved between orientation and action.
- No hidden redefinition of priorities during hand-off.

## Anti-patterns (MUST NOT)
- Abrupt mode-switch with no transition checks.
- Replacing orientation with urgency-driven improvisation.

## Outputs
- Mandatory: transition plan, trigger checklist
- Optional: rollback conditions

## Exit criteria
- Transition conditions are testable by reviewer.
- Risks and rollback path are documented.

## Evidence artifacts
- transition checklist
- state-shift note

## Failure signals
- Team/agent cannot explain why transition is safe now.
- Transition starts before trigger conditions are met.

## Recovery protocol
Freeze action start, revalidate orientation priorities, then restart transition with explicit gate checks.

## Hand-off contract
- Next stage: 05 Movement
- Hand-off payload: approved transition plan + trigger checklist
- Hand-off quality checks: mover can execute without reinterpreting intent
