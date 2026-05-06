# Versioning Policy

The Access Orientation Protocol is a **documentation-first protocol**, not a software library. Versioning rules below are calibrated to that reality: they protect the **conceptual core** rather than an API surface.

## Version identifiers
- `vMAJOR.MINOR-draft` while the protocol is pre-release (current state).
- `vMAJOR.MINOR` after the first non-draft tag is cut.

The current published draft is `v1.0-draft` (see `CHANGELOG.md`).

## What constitutes a breaking change
A change is **breaking** (requires MAJOR bump) if it:
- renames or removes any of the 8 canonical stages,
- alters the meaning of `Resonance (Self)` as mandatory entry gate,
- alters the meaning of `Resonance (World)` as mandatory completion gate,
- removes or weakens the non-substitution principle in `BENCHMARK_BRIDGE.md`,
- removes a required field from `docs/schema/cycle_trace.schema.json`,
- changes the `enum` values of `status` or `world_verdict` in the schema,
- promotes any extension into the protocol core, or vice versa, without explicit governance review.

## What constitutes a non-breaking change
A change is **non-breaking** (MINOR or patch) if it:
- adds a new worked example, scenario, or contract review,
- adds an **optional** field to the cycle trace schema,
- clarifies wording without altering normative semantics,
- promotes a stage contract from Draft to Reviewed/Approved,
- adds new dimensions to the evaluation rubric **as additions**, not substitutions.

## What is explicitly out of scope for versioning
- Editorial fixes (typos, formatting) do not require a version note.
- Internal review notes and decision-log updates do not bump the version.

## Schema evolution rules
- `docs/schema/cycle_trace.schema.json` follows additive evolution: new optional fields are allowed; required fields cannot be added or removed without MAJOR bump.
- `enum` extensions to `status` or `world_verdict` are **breaking** because consumers may pattern-match on them.
- A migration note must accompany any schema change in `CHANGELOG.md`.

## Core vs extension
- The **core** is the 8-stage loop, its two gates, and the non-substitution principle.
- Everything else (examples, scenarios, rubric weighting suggestions, benchmark mappings) is **extension**.
- An extension change can never silently rewrite a core invariant. If governance review concludes that an extension has effectively done so, the change is reclassified as breaking and a MAJOR bump is required retroactively.

## Release cadence
- No fixed cadence. Releases are governance-driven, not calendar-driven.
- A new draft is cut when one of: (a) a phase from the implementation plan completes, (b) external review surfaces a structural correction, (c) a new core invariant is added.

## Deprecation policy
- Concepts are not silently removed. A deprecation entry in `CHANGELOG.md` must precede removal by at least one tagged draft.
- Removed concepts are listed in the changelog with rationale and pointer to replacement (if any).
