# Benchmark Bridge — AOP ↔ Traditional Metrics

## Purpose
Make AOP signals comparable to classical benchmark metrics (accuracy, latency, cost, safety) **without** letting benchmark scores stand in for orientation quality. The bridge is designed so that **divergence** between the two systems of measurement is visible and actionable, not smoothed.

## Non-substitution principle
- Benchmark scores describe **task surface**.
- The AOP rubric describes **orientation behavior**.
- Neither implies the other. A run can score well on a benchmark and still fail world transfer; it can score modestly and still produce a strong correction loop.
- The bridge therefore reports both, and treats their **disagreement** as a first-class observation.

## Mapping

| AOP dimension (rubric) | Stage signal | Traditional metric most often confused with it |
|---|---|---|
| D1 Entry integrity | 00–01 | task framing quality, prompt clarity |
| D2 Assembly relevance | 02 | retrieval precision / context noise ratio |
| D3 Orientation depth | 03 | plan quality / decomposition score |
| D4 Transition continuity | 04 | execution stability, error rate at hand-off |
| D5 Movement integrity | 05 | step-level accuracy, tool-call success |
| D6 Trajectory stability | 06 | longitudinal robustness, drift metrics |
| D7 World validation | 07 | real-world transfer, downstream impact |
| D8 Recovery discipline | cross | rollback rate, post-incident MTTR |

The mapping is **directional, not equivalent**. A high traditional metric does not raise the corresponding AOP score; it only shows where the metric and the rubric **could** agree if the underlying orientation behavior also held.

## Required benchmark package fields
Any benchmark report submitted under AOP review must include:
1. **Scenario definition and constraints** — task, inputs, allowed tools, time bounds.
2. **Baseline task metrics** — accuracy/latency/cost/safety as appropriate.
3. **AOP cycle trace** — conforming to `docs/schema/cycle_trace.schema.json`.
4. **Rubric scoring** — per-dimension scores per `docs/EVALUATION_RUBRIC.md` with evidence references.
5. **Divergence analysis** — explicit statement of where task metrics and rubric disagree, and which signal is treated as authoritative for the decision being made.
6. **Transfer risk statement** — what would have to be true in the world for this cycle to fail despite favorable scores, and what evidence would detect that.

A package missing field 5 or field 6 is **incomplete** for governance purposes, regardless of how strong the task metrics look.

## Divergence scenarios (initial set)
Three reference scenarios live under `docs/scenarios/`:
1. `scenario_high_score_weak_transfer.md` — high benchmark accuracy, weak D7.
2. `scenario_strong_correction_loop.md` — moderate accuracy, strong D5/D8.
3. `scenario_fast_unstable.md` — low latency, weak D6.

Each scenario is paired with the divergence pattern it teaches reviewers to recognize.

## How the bridge is used
- **In review:** reviewer reads benchmark report alongside cycle trace and rubric scoring; explicitly names the divergence (or its absence).
- **In iteration:** the team picks the next change based on **the weaker** of the two signals, not the friendlier one.
- **In publication:** any external claim ("our system improved X") must report both the metric movement and the rubric movement, or it is treated as incomplete.

## What the bridge does NOT do
- It does not produce a single combined score.
- It does not let a strong rubric score excuse a real safety regression on the task metric.
- It does not let a strong task metric excuse a missing world-validation step.
- It does not turn AOP into a benchmark methodology — AOP remains a protocol; benchmarks remain instruments observed through it.
