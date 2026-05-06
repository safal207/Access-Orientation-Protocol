# Access Orientation Protocol — Implementation Plan

## Purpose
This plan translates the existing conceptual architecture of AOP into an executable documentation and reference-model program without collapsing the protocol into a rigid task pipeline.

## Implementation status (100% checkpoint)
Completed artifacts in this repository now cover the full initial stage-contract scope:
- Stage contract template is published.
- 8/8 stage contracts are drafted (`00` to `07`).
- Practical kickoff checklist and issue template are available for execution governance.

Remaining for next maturity level (post-100% of initial contract scope):
- Add worked examples across four system types.
- Add minimal trace schema and benchmark bridge artifacts.
- Move contracts from Draft to Reviewed/Approved via governance cadence.

Progress on next maturity level:
- Worked-examples pack **complete for Phase 2**: 4/4 examples drafted (`individual_operator`, `human_team`, `ai_agent`, `hybrid_human_ai`) with paired machine-readable traces under `docs/examples/traces/`.
- Minimal trace schema published at `docs/schema/cycle_trace.schema.json`; all four trace files conform to it.
- Benchmark bridge outline scaffolded at `docs/BENCHMARK_BRIDGE_OUTLINE.md` (next step: convert outline into evaluation rubric and stress scenarios per Phase 4).

## Scope and assumptions
- **In scope:** documentation hardening, reference artifacts, lightweight examples, and validation methodology.
- **Out of scope (for now):** production runtime, SDKs, and opinionated orchestration frameworks.
- **Constraint:** preserve separation between **protocol core** and **extensions**.

## Guiding implementation principles
1. Keep the eight-part resonance loop intact in all artifacts.
2. Treat **Resonance (Self)** as mandatory entry gate.
3. Treat **Resonance (World)** as mandatory completion gate.
4. Avoid reducing orientation to checklist planning.
5. Require evidence of world feedback for completion claims.

## Execution phases

### Phase 0 — Alignment and baseline (Week 1)
**Goal:** establish implementation baseline and quality criteria.

**Deliverables**
- Repository-wide terminology map and consistency checklist.
- Documentation style guide for protocol invariants.
- Traceability table: each section in docs mapped to one or more core stages.

**Exit criteria**
- No unresolved term conflicts across core docs.
- Every core stage has explicit invariants and failure conditions.

---

### Phase 1 — Core specification hardening (Weeks 2–4)
**Goal:** convert current draft language into stable protocol specification.

**Deliverables**
- Normative core spec with MUST/SHOULD/MAY language.
- Stage contracts for all 8 stages:
  - intent,
  - preconditions,
  - invariants,
  - anti-patterns,
  - observable outputs.
- Updated diagrams synchronized with normative text.

**Exit criteria**
- Internal consistency review passed.
- Diagram-text parity check passed.

---

### Phase 2 — Reference interpretation pack (Weeks 5–7)
**Goal:** show how AOP applies across different system types.

**Deliverables**
- Four worked examples:
  1. individual operator,
  2. human team,
  3. AI agent,
  4. hybrid human–AI workflow.
- For each example: stage-by-stage walk-through + failure recovery path.
- Comparison matrix against pipeline/task-first methods.

**Exit criteria**
- Each example demonstrates full loop closure including world validation.
- Reviewers can distinguish “orientation success” from “task completion”.

---

### Phase 3 — Minimal reference model (Weeks 8–10)
**Goal:** provide lightweight implementable structure without creating a framework.

**Deliverables**
- Minimal data schema (e.g., YAML/JSON) for cycle traces.
- Reference state machine constraints for allowed stage transitions.
- Example trace corpus (good path + anti-pattern paths).

**Exit criteria**
- Trace schema can represent all 8 stages and handoffs.
- Invalid transition examples are machine-detectable.

---

### Phase 4 — Evaluation and benchmark bridge (Weeks 11–13)
**Goal:** operationalize benchmark interpretation while preserving protocol independence.

**Deliverables**
- Evaluation rubric for orientation quality:
  - entry integrity,
  - assembly relevance,
  - transition continuity,
  - trajectory stability,
  - world-feedback incorporation.
- Benchmark bridge document linking AOP signals to existing metrics (accuracy, latency, cost, safety).
- Stress scenarios for drift, premature closure, and false completion.

**Exit criteria**
- At least three benchmark-like scenarios showing divergence between score and orientation quality.
- Clear non-substitutive relationship between AOP rubric and traditional metrics.

---

### Phase 5 — Stabilization and publication (Weeks 14–15)
**Goal:** prepare v1 public package.

**Deliverables**
- Versioned protocol draft (v1.0-draft).
- Changelog and compatibility notes.
- Contributor guide for future extensions.

**Exit criteria**
- Public review checklist complete.
- Core vs extension boundary documented and versioned.

## Cross-cutting workstreams

### A. Quality assurance
- Terminology linting across docs.
- Stage coverage checks (no stage omitted in examples).
- Contradiction review (core assertions do not conflict across files).

### B. Governance
- Decision log for protocol changes.
- Extension proposal template requiring non-collapse proof (extension cannot redefine core loop semantics).

### C. Risk management
Top risks and mitigations:
1. **Protocol collapse into workflow tooling** → maintain strict “conceptual protocol” guardrails.
2. **Overfitting to benchmark interpretation** → keep benchmark materials in extension scope.
3. **Ambiguous world validation** → require external evidence artifacts in every worked example.

## Milestones snapshot
- **M1 (Week 1):** baseline aligned.
- **M2 (Week 4):** core spec stable.
- **M3 (Week 7):** multi-context examples complete.
- **M4 (Week 10):** reference model artifacts complete.
- **M5 (Week 13):** evaluation bridge complete.
- **M6 (Week 15):** v1.0-draft publication-ready.

## Success metrics
- 100% stage coverage across normative and example docs.
- Zero unresolved terminology conflicts in release candidate.
- All published examples include explicit world-feedback evidence.
- Reviewers can reproduce orientation judgments from provided artifacts.

## Immediate next actions (next 7 days)
1. Approve this plan and lock phase sequencing.
2. Create issue tracker labels by phase and workstream.
3. Draft normative template for stage contracts.
4. Run first terminology consistency pass across `/docs`.

## 30-day execution playbook

### Sprint 1 (Days 1–14)
**Objective:** harden terminology and core contracts.

**Planned tasks**
- Build a canonical glossary source-of-truth and map aliases/synonyms.
- Define one-page contract templates for each core stage.
- Run a doc-level contradiction review across core files.

**Definition of done**
- All core terms are normalized and cross-referenced.
- At least 4/8 stage contracts are drafted and peer-reviewed.
- Contradictions are logged and assigned owners.

### Sprint 2 (Days 15–30)
**Objective:** complete core-stage contracts and publish review candidate.

**Planned tasks**
- Finish contracts for all 8 stages.
- Align architecture diagrams to contract semantics.
- Prepare v0.1 review package for external readers.

**Definition of done**
- 8/8 contracts are complete and linked from the architecture docs.
- Diagram-text parity checklist passes.
- Review package includes open questions and decision log updates.

## Stakeholder review cadence
- **Weekly:** implementation sync (owners, blockers, risk review).
- **Biweekly:** protocol governance review (core boundary protection).
- **Monthly:** external feedback session focused on clarity and reproducibility.

## What to do now (practical checklist)
Use this checklist to start execution immediately.

1. **Appoint roles (today).**
   - Protocol editor (owns core language consistency).
   - Example lead (owns worked examples and trace artifacts).
   - QA/review lead (owns contradiction and parity checks).
2. **Create tracking board (today).**
   - Columns: Backlog → In Progress → Review → Done.
   - Labels: `phase-0` ... `phase-5`, `qa`, `governance`, `risk`.
3. **Open first 8 issues (within 24h).**
   - One issue per AOP stage contract with the same template.
4. **Run terminology pass (within 48h).**
   - Normalize key terms across `README.md` and `/docs`.
5. **Draft and approve contract template (within 72h).**
   - Fields: intent, preconditions, invariants, anti-patterns, outputs.
6. **Publish Week-1 status note (day 7).**
   - Report: completed tasks, open risks, and next-week commitments.

### Ready-to-copy issue template
**Title:** `Stage Contract: <Stage Name>`

**Acceptance criteria**
- Contract includes intent, preconditions, invariants, anti-patterns, outputs.
- Terms match glossary and architecture definitions.
- At least one reviewer signs off.
