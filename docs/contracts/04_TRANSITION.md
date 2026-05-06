# Stage Contract 04 — Transition

## Metadata
- Stage ID: 04
- Stage Name: Transition
- Layer: State organization
- Version: v0.3
- Status: Reviewed
- Reviewed on: 2026-05-06 (v0.2), 2026-05-06 (v0.3 — rollback promoted to Mandatory)
- Owners: Protocol editor
- Reviewers: QA/review lead

## Review notes (v0.2)
- Anti-pattern coverage matches "abrupt transition" from `STRESS_TEST.md`; trigger-condition precondition makes the failure detectable.
- Rollback condition was promoted from Optional to Mandatory in v0.3 (additive output strengthening per `VERSIONING.md`); all worked examples in `docs/examples/` already treat it as required for D4 (Transition continuity).
- Hand-off Inputs to `05 Movement` are consistent.
- Open question deferred: minimum number of trigger conditions before transition is allowed.

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
- Mandatory: transition plan, trigger checklist, rollback conditions
- Optional: state-shift annotations

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
