# AOP Stage Contracts

This directory contains the normative stage-contract artifacts for the Access Orientation Protocol cycle.

## Template
- `STAGE_CONTRACT_TEMPLATE.md`

## Contracts (00–07)
- `00_RESONANCE_SELF.md`
- `01_ACCESS_POINT.md`
- `02_ASSEMBLY.md`
- `03_ORIENTATION.md`
- `04_TRANSITION.md`
- `05_MOVEMENT.md`
- `06_TRAJECTORY.md`
- `07_RESONANCE_WORLD.md`

## Status
- Coverage: 8/8 stages drafted.
- Contract status: **Reviewed (v0.2)** as of 2026-05-06. Each contract carries a `Review notes (v0.2)` section documenting anti-pattern coverage, schema/rubric alignment, and any items deferred to the next review cycle.
- Next governance milestone: promotion from Reviewed to Approved, gated on external review and on resolving the v0.3 changes flagged in individual contracts (notably promoting the rollback condition in `04_TRANSITION` from Optional to Mandatory).

## Review summary (v0.2)
- Hand-off chain `00 → 01 → 02 → 03 → 04 → 05 → 06 → 07 → 00` verified end-to-end.
- Anti-patterns from `docs/STRESS_TEST.md` mapped to at least one stage each.
- Stage outputs map to rubric dimensions in `docs/EVALUATION_RUBRIC.md` and to the `evidence` array of `docs/schema/cycle_trace.schema.json`.
- No structural rewrites required at v0.2; deferred items recorded inline in each contract for the next iteration.
