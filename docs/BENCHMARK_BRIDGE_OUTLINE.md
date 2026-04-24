# Benchmark Bridge Outline (AOP ↔ traditional metrics)

## Purpose
Define how orientation-quality signals complement (not replace) classical metrics such as accuracy, latency, cost, and safety.

## Why benchmarks are useful
- They make orientation quality observable and comparable across runs.
- They expose hidden failure modes where task scores look good but world transfer is weak.
- They provide a shared evidence format for review, governance, and iteration.
- They reduce “internal confidence bias” by requiring external validation signals.

## Who benefits
- **Protocol designers:** validate whether stage contracts produce stable behavior.
- **Agent builders / ML teams:** detect drift between benchmark success and real-world usefulness.
- **Product teams:** choose improvements that increase reliability, not only short-term speed.
- **Researchers/evaluators:** compare systems on trajectory stability and correction behavior.
- **Operators and decision makers:** get clear go/no-go evidence before scaling actions.

## Mapping skeleton
- Entry integrity (`00-01`) ↔ task framing quality
- Assembly relevance (`02`) ↔ context precision / noise ratio
- Transition continuity (`04`) ↔ execution stability
- Trajectory stability (`06`) ↔ robustness over time
- World validation (`07`) ↔ real-world transfer validity

## Required benchmark package fields
- Scenario definition and constraints
- Baseline task metrics
- AOP stage-by-stage trace
- Divergence analysis (score success vs orientation failure and vice versa)
- Transfer risk statement

## Initial target scenarios
1. High benchmark score, weak world transfer
2. Moderate score, strong world correction loop
3. Fast response, poor trajectory stability
