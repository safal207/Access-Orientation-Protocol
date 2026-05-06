# AOP Evaluation Rubric — Orientation Quality

## Purpose
Provide a stable, reviewable rubric for assessing **orientation quality** of an AOP cycle. The rubric is **non-substitutive**: it complements task-level metrics (accuracy, latency, cost, safety) and never replaces them.

## What this rubric measures (and does not)
- **Measures:** integrity of entry, relevance of assembly, continuity of transition, stability of trajectory, presence and incorporation of external feedback, behavior under failure (rollback discipline).
- **Does not measure:** raw task success. A run can be "task-correct" and orientation-weak, or "task-imperfect" and orientation-strong. Both states are diagnostic.

## Scoring scale (per dimension)
- **0 — absent:** dimension not represented in the cycle.
- **1 — asserted:** dimension claimed but not evidenced.
- **2 — partially evidenced:** evidence exists but with gaps or unresolved drift.
- **3 — fully evidenced:** evidence is reproducible, dated, and sourced; failures (if any) are explicitly recorded with rollback.

A dimension with score 1 ("asserted only") is treated as **failing** for governance purposes — internal claim without evidence is exactly the failure mode AOP is designed to surface.

## Dimensions

### D1 — Entry integrity (stages 00–01)
- Self-state calibration is recorded with at least one declared uncertainty.
- Access point is selected against rejected alternatives with stated rationale.
- **Anti-pattern detector:** "skipped self resonance" — cycle starts directly from a task statement.

### D2 — Assembly relevance (stage 02)
- Inputs have explicit provenance and inclusion/exclusion rationale.
- Noise inputs are visibly excluded, not silently absent.
- **Anti-pattern detector:** assembly-as-accumulation (volume rises, signal does not).

### D3 — Orientation depth (stage 03)
- Relations between inputs are mapped (not just listed).
- Directions are ranked with criteria.
- **Anti-pattern detector:** orientation reduced to checklist or to a single proposed action.

### D4 — Transition continuity (stage 04)
- Operative-state triggers are explicit and falsifiable.
- A rollback condition exists and is reachable.
- **Anti-pattern detector:** "abrupt transition" — state change asserted without a trigger record.

### D5 — Movement integrity (stage 05)
- Deviations are logged at the time they happen.
- Corrections route through a real rollback to an earlier stage when warranted.
- **Anti-pattern detector:** silent recovery (deviation without trace).

### D6 — Trajectory stability (stage 06)
- Pattern claim rests on enough temporal depth to be more than sequence.
- Counter-evidence is recorded, not omitted.
- **Anti-pattern detector:** "illusory trajectory" — extrapolation from 1–2 data points.

### D7 — World validation (stage 07)
- Validation source is **external** to the executing system.
- Verdict can be `validated`, `partial`, or `invalidated`; "partial" is a first-class outcome, not a softened "validated".
- **Anti-pattern detector:** "closed loop without world resonance" — completion declared on internal feedback alone.

### D8 — Recovery discipline (cross-cutting)
- At least one anti-pattern was either (a) encountered and explicitly rolled back, or (b) actively probed and verified absent.
- Rollback artifacts exist and reference the prior stage they returned to.
- **Anti-pattern detector:** "no failure ever surfaced" — a cycle with zero deviation across all stages is treated as suspicious, not as success.

## Aggregate read
- **Strong orientation:** D1–D7 all ≥ 2, D8 = 3, world verdict ∈ {validated, partial}.
- **Weak orientation:** any of D1, D4, D7 < 2, regardless of task outcome.
- **Suspicious orientation:** all dimensions = 3, no anti-pattern probed (D8 weak signal). Recommend independent review.

Aggregate score is **not** a single number. A weighted sum collapses the diagnostic shape that the rubric is built to preserve.

## Use in review
1. Reviewer reads the cycle trace (`docs/schema/cycle_trace.schema.json`) and the worked-example narrative.
2. Reviewer scores each dimension with one-line evidence reference.
3. Reviewer issues a verdict using the aggregate read above.
4. If verdict is "weak" or "suspicious," the cycle does not advance to publication; it returns to the failing stage.

## Relationship to traditional metrics
- Task metrics (accuracy, latency, cost, safety) are reported alongside, never instead of, this rubric.
- Divergence between task metrics and orientation rubric is itself a primary signal — see `docs/BENCHMARK_BRIDGE.md` and `docs/scenarios/`.
