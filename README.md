# Access Orientation Protocol

**Status:** v1.0-draft (publication-ready draft, see [`CHANGELOG.md`](CHANGELOG.md)).

Access Orientation Protocol (AOP) is a documentation-first protocol for orienting action in living systems. It describes how a human, AI agent, team, or adaptive system can move from internal state calibration to externally validated action without reducing the process to a simple linear workflow.

It should be understood as a **meta-orientation layer** that can sit above workflows, agent runtimes, decision engines, and benchmarks without being reducible to any of them.

## Why this protocol exists

Many systems can execute steps, but they still fail because they enter action from the wrong state, anchor to the wrong problem, assemble the wrong inputs, or mistake internal certainty for contact with reality.

Access Orientation Protocol exists to provide a shared architecture for:
- regaining contact with actual internal state before action;
- identifying a true entry point rather than a convenient one;
- distinguishing relevant assembly from indiscriminate accumulation;
- preserving continuity during state change;
- validating action through real-world response rather than internal completion alone.

The protocol is designed as a loop of calibration, orientation, transition, movement, and verification. It does not start with output production and it does not end at execution.

## Canonical cycle

The canonical cycle has eight parts:

0. **Resonance (Self)** — calibrate the system to its actual internal state.
1. **Access Point** — identify the true entry or anchor point.
2. **Assembly** — gather only the elements that are relevant to the current state and aim.
3. **Orientation** — restore internal coordinates, relations, and direction.
4. **Transition** — cross into a new operative state without rupture.
5. **Movement** — act from centered orientation rather than panic, inertia, or compulsion.
6. **Trajectory** — observe the pattern of motion over time.
7. **Resonance (World)** — test the cycle against external reality through its feedback, correction, or contradiction.

This is a **resonance loop**, not a one-way pipeline. **Resonance (Self)** is the mandatory entry condition. **Resonance (World)** is the mandatory completion condition. Without **Resonance (World)**, the cycle is incomplete.

## What it is

Access Orientation Protocol is:
- a conceptual protocol for orientation before, during, and after action;
- an architectural model for adaptive systems operating under uncertainty;
- a shared vocabulary for humans, AI agents, teams, and mixed systems;
- a way to reason about transitions, drift, integrity, and validation.

## What it is not

Access Orientation Protocol is not:
- a generic AI framework;
- an agent runtime;
- a task runner;
- a decision engine;
- a guarantee of truth, correctness, or wisdom;
- a mechanism that eliminates self-deception.

The protocol can improve clarity and reduce avoidable distortion, but it cannot guarantee that a system's self-reading is accurate or that its actions map cleanly to reality.

## Initial architecture overview

AOP can be understood as four interacting layers:

1. **Boundary calibration**
   - Resonance (Self)
   - Resonance (World)
2. **Entry and composition**
   - Access Point
   - Assembly
3. **State organization**
   - Orientation
   - Transition
4. **Action and observation**
   - Movement
   - Trajectory

The layers are conceptual rather than software modules. They define relationships that can be implemented differently across individuals, teams, software systems, or hybrid human-machine environments.

### Architectural principles

- The protocol is loop-based, not pipeline-based.
- Entry without Resonance (Self) is structurally unsound.
- Completion without Resonance (World) is structurally incomplete.
- Orientation is broader than planning; it restores coordinates, not just tasks.
- Trajectory is a pattern observed across time, not merely a list of steps.
- Reality-testing matters more than internal satisfaction.

## Benchmark interpretation

The protocol can also be used to evaluate models and agent systems. This is an **early derived interpretation**, not part of the minimal protocol core. In that context, the same eight-part loop becomes an assessment frame for how a system enters a task, assembles context, maintains orientation, survives long trajectories, and transfers benchmark performance into real-world usefulness.

This benchmark interpretation does not replace accuracy, latency, cost, or safety metrics. It adds an orientation layer that asks whether benchmark performance is stable, honest, reproducible, and externally validated.
The first benchmark-specific specification lives in `docs/BENCHMARK.md`. The core-vs-extension boundary is summarized in `docs/CORE_AND_EXTENSIONS.md`.

## Repository structure

```text
/
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── VERSIONING.md
├── LICENSE
├── RIGHTS.md
├── .gitignore
├── docs/
│   ├── ANTI_PATTERNS.md
│   ├── ARCHITECTURE.md
│   ├── BENCHMARK.md
│   ├── BENCHMARK_BRIDGE.md
│   ├── BENCHMARK_BRIDGE_OUTLINE.md
│   ├── COMPARISON.md
│   ├── CORE_AND_EXTENSIONS.md
│   ├── EVALUATION_RUBRIC.md
│   ├── GLOSSARY.md
│   ├── IMPLEMENTATION_PLAN.md
│   ├── STRESS_TEST.md
│   ├── TECHNICAL_BRIEF.md
│   ├── contracts/        # 8 stage contracts + template
│   ├── examples/         # 4 worked examples + traces
│   ├── scenarios/        # divergence scenarios
│   └── schema/           # cycle_trace JSON schema
└── diagrams/
    ├── access_orientation_layers.mmd
    └── access_orientation_loop.mmd
```

## Roadmap

The full phased plan lives in [`docs/IMPLEMENTATION_PLAN.md`](docs/IMPLEMENTATION_PLAN.md). Summary of the v1.0-draft state:

- **Phase 0 — Alignment and baseline:** complete.
- **Phase 1 — Core specification hardening:** 8/8 stage contracts drafted.
- **Phase 2 — Reference interpretation pack:** 4/4 worked examples + machine-readable traces.
- **Phase 3 — Minimal reference model:** cycle-trace JSON schema published.
- **Phase 4 — Evaluation and benchmark bridge:** rubric, bridge, and three divergence scenarios drafted.
- **Phase 5 — Stabilization and publication:** v1.0-draft cut; external review window open.

Future work after v1.0-draft includes promoting stage contracts from Draft to Reviewed/Approved, expanding the divergence-scenario corpus, and additive (non-breaking) schema enrichments — see `VERSIONING.md` for what changes require a major version bump.

## Current status

This repository is at **v1.0-draft** — a publication-ready draft. The conceptual core, all eight stage contracts, the worked-example pack, the cycle-trace schema, the evaluation rubric, and the benchmark bridge are in place. External review can begin without further structural churn expected before v1.0.

For contribution rules and the extension-proposal protocol see [`CONTRIBUTING.md`](CONTRIBUTING.md). For versioning and breaking-change policy see [`VERSIONING.md`](VERSIONING.md). For the change history see [`CHANGELOG.md`](CHANGELOG.md).


## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).

The software and documentation are provided under MIT.  
The project name, branding, logos, and associated marks are not granted by this license.
