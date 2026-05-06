# Changelog

All notable changes to the Access Orientation Protocol are recorded here.
Versioning policy is defined in `VERSIONING.md`.

The format follows the spirit of [Keep a Changelog](https://keepachangelog.com/),
adapted for a documentation-first protocol.

## [Unreleased]
- Future changes prior to the next tagged draft.

## [v1.0-draft] — 2026-05-06

This is the first **publication-ready draft** of the protocol. It is a draft, not a v1.0 release: the conceptual core is stable, examples and rubric are complete, and external review can begin without further structural churn expected.

### Added
- **Stage contracts (8/8):** `00_RESONANCE_SELF` through `07_RESONANCE_WORLD` plus stage-contract template under `docs/contracts/`.
- **Worked-example pack (4/4):** individual operator, human team, AI agent, hybrid human–AI; each paired with a machine-readable cycle trace under `docs/examples/traces/`.
- **Cycle trace schema:** `docs/schema/cycle_trace.schema.json` — minimal JSON schema constraining 8 stages, statuses, evidence references, and world verdict.
- **Evaluation rubric:** `docs/EVALUATION_RUBRIC.md` — 8-dimension orientation-quality rubric with non-substitutive scoring and explicit anti-pattern detectors.
- **Benchmark bridge:** `docs/BENCHMARK_BRIDGE.md` — mapping between AOP signals and traditional metrics with a non-substitution principle and required benchmark-package fields.
- **Divergence scenarios:** three reference scenarios under `docs/scenarios/` showing where benchmark scores and orientation rubric disagree.
- **Implementation plan:** `docs/IMPLEMENTATION_PLAN.md` with phased execution playbook and 30-day checklist.

### Stabilized
- Core/extension boundary documented in `docs/CORE_AND_EXTENSIONS.md`.
- Glossary, architecture, anti-patterns, stress test, and comparison docs aligned to the same terminology.

### Known limitations of v1.0-draft
- Stage contracts are at **Draft** status; promotion to **Reviewed/Approved** requires external review cadence.
- Trace schema is intentionally minimal; richer fields (timing, actor identity, signature) are out of scope for v1.0-draft.
- Rubric scores are reviewer-assigned, not automated. Automation is **explicitly not** in scope: any future automation must preserve the non-substitution principle.

### Compatibility notes
- v1.0-draft is the baseline against which future changes are compared.
- Breaking changes (renaming stages, altering loop semantics, changing the `cycle_trace.schema.json` in a non-additive way) require a major-version bump in the next tagged draft.
- Additive changes (new examples, new scenarios, new contract reviews) do not bump the version.
