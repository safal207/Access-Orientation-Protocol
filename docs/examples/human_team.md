# Worked Example — Human Team

## Context and objective
A 6-person product team is shipping unreliable releases: features land on time but post-release defects and customer escalations keep rising.

**Objective:** restore release-quality trajectory measured by reduction in post-release defects and unblocked customer outcomes, validated by external customer signal — not internal velocity charts.

## Stage-by-stage walkthrough

### 00 — Resonance (Self)
- Team-level calibration session: surfaced shared anxiety about deadlines and unspoken disagreement on quality bar.
- Declared uncertainties: is the bottleneck specification quality, review depth, or rollout discipline?
- Output: team calibration note + uncertainty register signed by all members.

### 01 — Access Point
- Candidate anchors compared:
  1. "Add more QA capacity"
  2. "Tighten specification entry quality"
  3. "Slow down release cadence"
- Selected anchor: tighten specification entry (highest causal leverage; capacity changes deferred).
- Output: anchor decision record with rejected-options rationale.

### 02 — Assembly
- Included: last 3 incident reports, last 5 specs that shipped with defects, customer escalation transcripts.
- Excluded: generic process literature and unrelated roadmap pressure.
- Output: assembly manifest with provenance per artifact.

### 03 — Orientation
- Built relation map: ambiguous specs -> divergent implementations -> shallow review -> regression after release.
- Ranked directions:
  1. spec entry checklist (acceptance, non-goals, rollout plan),
  2. structured review with explicit risk callouts,
  3. release dry-run before customer rollout.
- Output: shared orientation map.

### 04 — Transition
- Defined operative-state triggers: spec passes entry checklist + named owner per risk.
- Rollback condition: if two specs in a row fail entry checklist, pause feature work and re-orient.
- Output: transition checklist adopted by tech lead and PM.

### 05 — Movement
- Executed 4 features through new entry pipeline.
- Logged deviations: one feature bypassed checklist due to perceived urgency.
- Correction: rollback to stage 04 for that feature; reinforced rule "no bypass without written risk acceptance".
- Output: movement log with deviation events.

### 06 — Trajectory
- Two-month trend:
  - regression rate dropped,
  - review time per spec increased modestly,
  - cycle time stable.
- Output: trajectory report with trend lines and counter-evidence.

### 07 — Resonance (World)
- External validation:
  - customer escalation count fell,
  - two customers cited "more predictable releases",
  - one customer reported a new latency complaint unrelated to defect work.
- Verdict: **validated** for defect trajectory; **partial** for overall reliability (latency surfaced as next concern).
- Next-cycle input: open new cycle scoped to latency, not bundle it into current cycle.

## Failure branch and recovery path
- Failure encountered at stage 05 (urgency bypass).
- Recovery: explicit return to stage 04, reinforce trigger contract, document waiver protocol so future deviations are visible rather than silent.

## Evidence artifacts map
- `team_calibration_note.md`
- `anchor_decision_record.md`
- `assembly_manifest.md`
- `orientation_map.md`
- `transition_checklist.md`
- `movement_log.md`
- `trajectory_report.md`
- `customer_signal_packet.md`

## Final verdict
- Task completion: features shipped on time across the period.
- Orientation success: validated for defect dimension; explicitly insufficient for full reliability picture — next cycle required.
