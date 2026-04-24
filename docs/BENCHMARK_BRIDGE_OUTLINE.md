# Benchmark Bridge Outline (AOP ↔ traditional metrics)

## Purpose
Define how orientation-quality signals complement (not replace) classical metrics such as accuracy, latency, cost, and safety.

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
