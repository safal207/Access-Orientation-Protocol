# Contributing to the Access Orientation Protocol

Thank you for considering a contribution. AOP is a documentation-first protocol; contributions are evaluated against the **conceptual integrity of the loop**, not against code-style conventions.

## Before you propose a change
Read these first — most contribution friction comes from missing one of them:
- `README.md` — protocol overview and what AOP **is not**.
- `docs/CORE_AND_EXTENSIONS.md` — the core/extension boundary.
- `docs/GLOSSARY.md` — canonical terminology.
- `docs/ANTI_PATTERNS.md` and `docs/STRESS_TEST.md` — known failure modes you should not reintroduce.
- `VERSIONING.md` — what counts as breaking.

## Contribution categories

### 1. Editorial (typos, wording clarifications)
- Open a PR. No issue required.
- Must not change normative meaning. If unsure whether the wording is normative, treat it as normative.

### 2. New worked example or scenario
- Use the structure already established under `docs/examples/` or `docs/scenarios/`.
- Each worked example must include: stage-by-stage walkthrough, evidence artifacts map, **failure branch with rollback**, and a `world_verdict` that is honest (including `partial` or `invalidated`).
- Each scenario must surface a **specific divergence** between traditional metrics and the AOP rubric.

### 3. Stage contract change (any of `docs/contracts/00`–`07`)
- Open an issue first using the stage-contract issue template.
- Required reviewers: protocol editor + at least one independent reviewer.
- Changes that alter intent, preconditions, or invariants are **breaking** unless they are pure clarifications.

### 4. Schema change (`docs/schema/cycle_trace.schema.json`)
- Additive optional fields: PR + one reviewer.
- Any change to required fields, enums, or the 8-stage shape: **breaking**, requires governance review and a MAJOR version bump.
- Include a `CHANGELOG.md` entry with migration notes.

### 5. Extension proposal
The extension proposal is the **highest-friction** contribution path. This is intentional — extensions are where the core gets eroded if accepted carelessly.

A new extension proposal must include a **non-collapse proof**: a written argument that the extension does **not**:
- redefine any of the 8 stages,
- weaken `Resonance (Self)` as entry gate or `Resonance (World)` as completion gate,
- replace the non-substitution principle with a single combined score,
- silently turn the protocol into a workflow framework.

If reviewers cannot agree that the non-collapse proof holds, the extension is rejected or reclassified as a core change (which then triggers the breaking-change path).

## Pull request expectations
- Title format: `<area>: <short description>` (e.g., `examples: add education-context worked example`).
- PR body should reference the relevant issue (if any) and the contribution category above.
- Do not bundle unrelated changes. Examples + rubric edits + schema edits in the same PR will be asked to split.
- Editorial PRs may be merged by a maintainer without external review.
- Anything beyond editorial requires at least one independent review.

## Definition of done
A PR is ready to merge when:
- All affected docs are internally consistent (no terminology drift versus glossary).
- All worked examples and scenarios still type-check against `docs/schema/cycle_trace.schema.json` if they include trace files.
- `CHANGELOG.md` is updated for non-editorial changes.
- The non-substitution principle and the entry/completion gates are intact.

## What we will not accept
- Removing or weakening the entry/completion gates "for usability".
- Replacing `partial` and `invalidated` verdicts with softer language to make examples look better.
- Adding combined or weighted single-number rubric scores.
- Importing prescriptive workflow tooling into the protocol core.

## Governance
- Disputes on whether a change is breaking are resolved by the protocol editor; if unresolved, the change is treated as breaking by default.
- Decisions of structural significance are recorded in a decision log entry.
