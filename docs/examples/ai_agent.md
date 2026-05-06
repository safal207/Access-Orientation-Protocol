# Worked Example — AI Agent

## Context and objective
A single autonomous LLM-based agent is tasked with weekly competitive intelligence summaries. Recent runs produced fluent reports that internal stakeholders rated as "confident but misleading": good prose, weak grounding.

**Objective:** restore a trajectory where each weekly summary is grounded in retrievable evidence and where the agent can declare uncertainty rather than fabricate completeness. Validation is external: stakeholder spot-checks against source material.

## Stage-by-stage walkthrough

### 00 — Resonance (Self)
- Agent runs an explicit pre-task self-state probe:
  - retrieval health (index freshness, last sync timestamp),
  - tool availability,
  - declared known-unknowns about the target domain.
- Produces a calibration record: confidence band per topic + an explicit "do not answer without retrieval" flag for low-confidence topics.
- Output: `agent_calibration.json`.

### 01 — Access Point
- Candidate anchors:
  1. "Maximize coverage breadth"
  2. "Restrict to topics with retrievable evidence"
  3. "Default to last week's structure"
- Selected anchor: restrict to topics with retrievable evidence (anti-fabrication leverage highest).
- Rejected-options rationale recorded.
- Output: `anchor_decision.json`.

### 02 — Assembly
- Retrieval bounded to:
  - allowed sources list,
  - freshness window (≤14 days),
  - per-topic minimum evidence count (≥2 independent sources).
- Excluded: speculative blogs, unverifiable social posts.
- Each retrieved chunk tagged with provenance and retrieval timestamp.
- Output: `assembly_manifest.json`.

### 03 — Orientation
- Agent builds topic relation map: claims linked to evidence IDs; claims with no supporting evidence flagged as "drop or mark uncertain".
- Ranked output structure:
  1. high-confidence claims with citations,
  2. partial claims with explicit caveats,
  3. unanswered questions surfaced as open items.
- Output: `orientation_map.json`.

### 04 — Transition
- Operative-state triggers before generation:
  - all retained claims have evidence IDs,
  - uncertainty register is non-empty when coverage is incomplete.
- Rollback condition: if more than 30% of claims are unsupported, halt generation and return to stage 02.
- Output: `transition_gate.json`.

### 05 — Movement
- Generation pass:
  - each paragraph emits a citation set,
  - paragraphs without citation pass-through are blocked,
  - low-confidence sections are emitted under a labeled "open questions" block rather than smoothed into prose.
- Logged deviations: 1 attempted hallucinated metric; intercepted by the citation gate.
- Output: `movement_log.json` + generated report.

### 06 — Trajectory
- Across 4 weekly runs:
  - share of cited claims increased,
  - "open questions" block stable but non-empty (healthy uncertainty),
  - hallucination interception count trending down.
- Output: `trajectory_report.json`.

### 07 — Resonance (World)
- External validation:
  - stakeholder spot-check on 10 random claims: 9 verifiable, 1 wrongly attributed.
  - one stakeholder reported the report was "less impressive but more useful for decisions".
- Verdict: **validated** for grounding trajectory; **partial** because attribution accuracy still has a tail.
- Next-cycle input: tighten attribution check at stage 03 (claim-source pairing audit).

## Failure branch and recovery path
- Failure encountered at stage 05 (hallucinated metric attempt).
- Recovery: citation gate triggered rollback to stage 02 for that topic; replaced fabricated metric with explicit "no reliable source found in window" entry.

## Evidence artifacts map
- `agent_calibration.json`
- `anchor_decision.json`
- `assembly_manifest.json`
- `orientation_map.json`
- `transition_gate.json`
- `movement_log.json`
- `trajectory_report.json`
- `stakeholder_spotcheck.json`

## Final verdict
- Task completion: weekly reports delivered on schedule.
- Orientation success: validated for grounding; explicit residual gap on attribution precision — feeds next cycle, not papered over.
