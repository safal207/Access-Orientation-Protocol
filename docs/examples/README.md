# AOP Worked Examples — Phase 2 Pack

This folder operationalizes Phase 2 of the implementation plan: showing AOP across multiple system types without collapsing the protocol into a checklist.

## Example set (Phase 2 — complete)
1. `individual_operator.md` ✅
2. `human_team.md` ✅
3. `ai_agent.md` ✅
4. `hybrid_human_ai.md` ✅

Each example is paired with a machine-readable trace under `traces/` that conforms to `docs/schema/cycle_trace.schema.json`.

## Required structure for each example
- Context and objective
- Stage-by-stage walkthrough (`00` to `07`)
- Evidence artifacts produced at each stage
- Failure branch and recovery path
- Final Resonance (World) verdict and lessons for next cycle

## Acceptance checklist (applied to all four examples)
- Full loop closure with **external** validation (not internal review pass)
- Explicit anti-pattern encounter + recovery via stage rollback
- Reproducible trace reference under `traces/`
- Clear distinction between task completion and orientation success
- Partial verdicts preserved — examples do not fake "validated" outcomes

## Trace corpus
- `traces/individual_operator_cycle_001.json`
- `traces/human_team_cycle_001.json`
- `traces/ai_agent_cycle_001.json`
- `traces/hybrid_human_ai_cycle_001.json`

## Cross-example contrasts
- **Individual operator:** self-state calibration is single-channel; world validation comes from peer feedback and shipped output.
- **Human team:** self-state is collective and surfaces unspoken disagreement; world validation is customer signal, not internal velocity.
- **AI agent:** self-state probes retrieval health and known-unknowns; world validation is stakeholder spot-check against sources.
- **Hybrid human–AI:** self-state is **two-channel** with an explicit handoff contract; world validation is patient-side response, external to both human and agent.

## What this pack does NOT claim
- It does not turn AOP into a workflow framework.
- It does not substitute traces for the conceptual loop.
- It does not treat "task delivered on schedule" as orientation success.
