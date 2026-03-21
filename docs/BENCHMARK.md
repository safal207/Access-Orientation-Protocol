# Access Orientation Benchmark (AOB) v0.1

> This document is an early derived interpretation of the Access Orientation Protocol. It is not part of the minimal protocol core.

Access Orientation Benchmark (AOB) is an evaluation specification derived from the Access Orientation Protocol. It is designed for neural models and agent systems that should be judged not only by output scores, but also by the quality, integrity, and transferability of the path that produced those scores.

AOB does not replace classical benchmarking. It adds an orientation layer to benchmarking.

## Purpose

A conventional benchmark usually answers a narrow question: how well did the system solve the test?

AOB answers a broader question: how stable, honest, coherent, reproducible, and transferable is the system's ability to solve tasks across a full evaluation cycle?

This specification should be treated as an application layer derived from the core protocol, not as a redefinition of the protocol itself.

## What AOB measures

### Classical metrics retained

AOB can include standard benchmark metrics such as:
- accuracy / pass rate;
- latency;
- cost;
- throughput;
- precision / recall / F1;
- safety violations.

### Orientation-layer metrics added

AOB adds protocol-aligned measures such as:
- **Self Calibration** — how correctly the system enters the task;
- **Assembly Quality** — how well relevant context is assembled;
- **Orientation Integrity** — how well the system maintains the correct solution vector;
- **Transition Stability** — how reproducibly the evaluation state is frozen and crossed into execution;
- **Movement Coherence** — how internally consistent the execution path remains;
- **Trajectory Stability** — how behavior degrades or holds across long runs;
- **World Transfer** — how benchmark strength transfers into real-world usefulness.

## Canonical cycle for a benchmark run

A benchmark run follows the same eight-part cycle:

0. **Resonance (Self)**
1. **Access Point**
2. **Assembly**
3. **Orientation**
4. **Transition**
5. **Movement**
6. **Trajectory**
7. **Resonance (World)**

As in the base protocol, **Resonance (Self)** is the mandatory entry boundary and **Resonance (World)** is the mandatory completion boundary. If the world does not confirm the benchmark, the cycle remains incomplete.

## Benchmark phases

## 0. Resonance (Self)

### Goal
Calibrate the system's starting state before evaluation begins.

### What is fixed
- model version;
- weights or checkpoint version;
- prompt, policy, or system configuration;
- tool access;
- memory state;
- decoding parameters such as temperature;
- cache usage;
- known drift indicators;
- confidence-calibration baseline.

### Output
**Run Identity Card** — a reproducible record of the starting state.

### Risk
If this phase is skipped, the benchmark may compare non-comparable states.

## 1. Access Point

### Goal
Declare which capability class is actually being tested.

### Example access points
- code generation;
- long-context question answering;
- multi-step reasoning;
- agent planning;
- dialogue stability;
- medical triage;
- retrieval fidelity.

### Output
**Declared Task Boundary** — a precise statement of the tested capability.

### Risk
Without a clear access point, a system may appear to succeed by solving an adjacent problem rather than the stated one.

## 2. Assembly

### Goal
Assemble the full evaluation context rather than a bare dataset.

### Includes
- core benchmark set;
- adversarial cases;
- edge cases;
- historical failure set;
- cost ceilings;
- latency limits;
- session length;
- tool availability;
- memory constraints.

### Output
**Benchmark Assembly Pack**

### Metrics
- **Assembly Coverage Score**
- coverage of base cases;
- coverage of edge cases;
- coverage of historical failures.

### Risk
Weak assembly can produce attractive scores on a dead benchmark.

## 3. Orientation

### Goal
Define what success means before scoring begins.

A model can be "best" under different orientations:
- accuracy;
- cost-efficiency;
- robustness;
- calibration honesty;
- long-run stability;
- real-world utility.

### Output
**Evaluation Orientation Profile**

```yaml
orientation:
  primary_goal: long_run_stability
  secondary_goals:
    - cost_efficiency
    - uncertainty_honesty
  anti_goals:
    - benchmark_gaming
    - excessive_confidence
```

### Risk
Without orientation, benchmarking collapses into score-maximization at any cost.

## 4. Transition

### Goal
Freeze the benchmark run in a reproducible executable state.

### Includes
- final configuration freeze;
- seed freeze;
- prompt freeze;
- evaluation-mode freeze;
- dataset hash;
- environment hash.

### Output
**Executable Benchmark Snapshot**

### Metrics
- **Transition Integrity**
- reproducibility;
- configuration immutability;
- absence of hidden substitutions.

### Risk
Without transition integrity, run A and run B cannot be honestly compared.

## 5. Movement

### Goal
Measure actual task execution by the model or agent.

### What is measured
- case outcomes;
- number of steps;
- retries;
- tool calls;
- hallucination bursts;
- chain consistency;
- latency per step;
- cost per step;
- recovery after failure.

### Metrics
- **Task Success**
- **Step Efficiency**
- **Recovery Quality**
- **Consistency Under Load**

### Risk
A strong final score can hide chaotic or fragile internal movement.

## 6. Trajectory

### Goal
Evaluate the pattern of behavior over time rather than a single result.

### What is measured
- drift after N tasks;
- degradation after long context;
- confidence inflation;
- cost creep;
- latency creep;
- memory corruption;
- local-optimum fixation;
- strategy rigidity.

### Metrics
- **Trajectory Stability Index**
- **Drift Rate**
- **Confidence Drift**
- **Long-Session Degradation**
- **Pattern Coherence**

### Risk
A system can look strong on the first twenty cases and fail on the two-hundredth.

## 7. Resonance (World)

### Goal
Test whether benchmark strength transfers into the world.

### What is measured
- production usefulness;
- user-satisfaction correlation;
- expert validation;
- real task completion;
- safety in deployment;
- downstream impact.

### Metrics
- **Benchmark-to-World Transfer**
- **User Utility Alignment**
- **Operational Reliability**
- **External Validation Score**

### Hard rule
If the world does not confirm the benchmark, the cycle is not complete.

## Benchmark modes

### A. Static Benchmark
A classic one-shot dataset run used for fast comparison, regression checks, and basic leaderboards.

**Limitation:** it does not expose long-run trajectory.

### B. Long-Run Benchmark
A long series of tasks or sessions used for agent systems, memory-heavy models, long-context models, and copilots.

It helps reveal:
- drift;
- fatigue;
- strategy fixation;
- cumulative error.

### C. Adversarial Benchmark
A set of hostile, noisy, or ambiguous cases used for robustness, confidence honesty, and failure-mode mapping.

### D. World Transfer Benchmark
A field evaluation using real tasks, real operators, or real deployment constraints.

It reveals whether leaderboard strength survives contact with reality.

## Optional extension layer

If the repository later formalizes an additional orientation-diagnostics layer, AOB can incorporate extra checks such as:
- **Metabolic Diversity Check** — whether the system gets trapped in a single strategy;
- **Belief Aging Check** — whether recent hypotheses are promoted to rules too early;
- **Temporal Causality Check** — whether short-term gains create long-term degradation;
- **Cognitive Immunity Check** — whether the system loses important layers and collapses into ideological or brittle modes.

These checks are intentionally optional at this stage. They should remain subordinate to the core protocol terminology until the base architecture is more mature.

## Score structure

AOB reports can be organized into four blocks:

### 1. Performance
- Accuracy / Pass Rate
- Precision / Recall / F1
- Latency
- Cost

### 2. Integrity
- Self Calibration
- Transition Integrity
- Orientation Consistency
- Confidence Honesty

### 3. Trajectory
- Drift Rate
- Long-Run Stability
- Cost Creep
- Strategy Rigidity

### 4. Transfer
- Real-World Utility
- Expert Validation
- User Outcome Correlation
- Benchmark-to-World Transfer

## Example benchmark report

```yaml
model: AOP-Coder-7B
benchmark_run: 2026-03-21-01

performance:
  pass_at_1: 0.54
  pass_at_5: 0.73
  avg_latency_ms: 210
  avg_cost_usd: 0.0028

integrity:
  self_calibration: 0.78
  orientation_consistency: 0.81
  confidence_honesty: 0.66
  transition_integrity: 0.94

trajectory:
  drift_rate: 0.18
  long_run_stability: 0.62
  cost_creep: 0.21
  strategy_rigidity: 0.57

transfer:
  pr_acceptance_proxy: 0.49
  real_world_utility: 0.71
  expert_validation: 0.68
  benchmark_to_world_transfer: 0.64
```

## Example applications

### Code LLM
AOB asks not only for `pass@k`, but also whether quality survives longer work, whether early success hardens into a bad strategy, and whether benchmark strength transfers into real pull requests and editor sessions.

### Medical classifier
AOB adds uncertainty honesty, resilience on rare cases, long-run consequences of errors, and confirmation by domain experts and outcome data.

### Memory-bearing agent
AOB asks whether the agent can hold orientation over 30-50 steps, avoid false certainty, prevent error accumulation from becoming belief, and recover a sound trajectory after failure.

## Fail conditions

An AOB run should be flagged as structurally weak if any of the following is true:
- self-calibration is absent;
- evaluation orientation is not declared;
- no trajectory analysis is performed;
- world transfer is not tested;
- a high score is achieved through hidden drift;
- the benchmark is not reproducible;
- the system exhibits stable false confidence.

## Summary formula

A strong model is not simply the one with the highest score. A strong model is one that preserves orientation, survives trajectory, and is confirmed by the world.

## Minimal conclusion

AOB turns benchmarking from an exam into a diagnosis of a living system. It evaluates not only result quality, but also path quality, long-run suitability, and the degree to which benchmark performance receives real-world confirmation.
