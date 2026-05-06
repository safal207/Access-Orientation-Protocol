# Divergence Scenarios

These reference scenarios illustrate where traditional benchmark metrics and the AOP evaluation rubric **disagree**. They are the working material of the benchmark bridge (`docs/BENCHMARK_BRIDGE.md`).

Each scenario is structured to teach reviewers a single divergence pattern:
- `scenario_high_score_weak_transfer.md` — a system that scores well on a benchmark but fails world validation.
- `scenario_strong_correction_loop.md` — a system that scores modestly but exhibits strong recovery and trajectory behavior.
- `scenario_fast_unstable.md` — a system that wins on latency but loses on trajectory stability.

The scenarios are deliberately **non-substitutive**: they do not tell the reviewer which signal "wins". They name the disagreement and require an explicit decision about which signal is authoritative for the decision at hand.
