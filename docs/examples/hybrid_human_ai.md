# Worked Example — Hybrid Human–AI Workflow

## Context and objective
A small clinical operations group uses an AI assistant to draft patient-communication letters. The human clinician finalizes and signs each letter. Recent audits flagged that some letters were technically correct but tonally misaligned with patient context, and a few contained subtle clinical caveats removed by the AI for "clarity".

**Objective:** restore a trajectory where AI drafting plus human review produces letters that are both clinically faithful and contextually appropriate, validated by patient-side response signal — not by internal review-pass rate alone.

## Stage-by-stage walkthrough

### 00 — Resonance (Self)
- Joint calibration: clinician declares own fatigue/load; agent emits retrieval and confidence state; both record assumed division of responsibility.
- Output: shared `joint_calibration.md` with separate human and agent self-reports + an explicit handoff contract for the cycle.

### 01 — Access Point
- Candidate anchors:
  1. "Speed up review (reduce clinician time per letter)"
  2. "Improve drafting accuracy (reduce clinical edits)"
  3. "Improve patient-context fit (reduce tonal misalignment)"
- Selected anchor: patient-context fit, with clinical fidelity as a hard invariant (non-negotiable).
- Output: anchor decision with explicit invariants the AI cannot override.

### 02 — Assembly
- Inputs:
  - patient record extract (consent-bounded),
  - prior correspondence with this patient,
  - clinical guideline excerpts relevant to the case.
- Excluded: unrelated demographic generalizations.
- Provenance recorded per source; sensitive fields tagged.
- Output: `assembly_manifest.md`.

### 03 — Orientation
- AI proposes letter structure with evidence anchors per clinical claim.
- Clinician annotates orientation map with patient-context cues the AI cannot infer (recent bereavement, language preference, prior misunderstandings).
- Output: jointly authored `orientation_map.md` with human-only annotations marked.

### 04 — Transition
- Operative-state triggers before drafting:
  - clinical claims have evidence anchors,
  - human-only context cues are present,
  - tone constraints are explicit (not implicit).
- Rollback condition: if either the agent or the clinician flags missing context, return to stage 02.
- Output: `transition_gate.md`.

### 05 — Movement
- AI drafts letter; clinician reviews with structured diff:
  - clinical fidelity diff,
  - tone/context diff,
  - removed-caveat detector (flags any safety-relevant phrase the AI dropped).
- Logged deviation: AI shortened a hedged statement into a confident one.
- Correction: rollback to stage 03 to re-anchor the caveat as non-negotiable; re-draft preserved the hedge.
- Output: `movement_log.md` with diff artifacts.

### 06 — Trajectory
- Across 30 letters over 6 weeks:
  - clinical-edit rate stable and low,
  - tonal-edit rate decreasing,
  - caveat-removal incidents trending toward zero after gate added.
- Output: `trajectory_report.md`.

### 07 — Resonance (World)
- External validation:
  - patient response rate to letters increased,
  - two patient comments cited "felt heard",
  - one patient reported residual confusion despite the new tone — escalation route worked.
- Verdict: **validated** for tonal trajectory; **partial** overall because individual patient confusion still surfaces and must feed the next cycle.
- Next-cycle input: add per-patient comprehension follow-up step.

## Failure branch and recovery path
- Failure encountered at stage 05 (caveat removal by AI).
- Recovery: explicit gate added to detect dropped hedges; rolled back to stage 03 to mark caveat as non-negotiable; downstream drafts preserved the safety phrasing.

## Evidence artifacts map
- `joint_calibration.md`
- `anchor_decision.md`
- `assembly_manifest.md`
- `orientation_map.md`
- `transition_gate.md`
- `movement_log.md`
- `trajectory_report.md`
- `patient_response_packet.md`

## Final verdict
- Task completion: letters delivered on schedule across the period.
- Orientation success: validated for tonal fit; an open patient-comprehension gap is acknowledged and routed to the next cycle rather than declared resolved.

## Hybrid-specific notes
- Self-state reporting is **two-channel** (human + agent), and both channels must be present at stage 00.
- The handoff contract is **explicit** about which decisions the AI may make autonomously and which require human authorship, especially around clinical caveats.
- World validation is **external to both** the AI and the clinician — internal review-pass rate is treated as a process metric, not as orientation evidence.
