# Stage Contract 02 — Assembly

## Metadata
- Stage ID: 02
- Stage Name: Assembly
- Layer: Entry and composition
- Version: v0.1
- Status: Draft
- Owners: Example lead
- Reviewers: QA/review lead

## Intent
Collect only the information and components required for the selected anchor.

## Inputs
- Required: selected anchor and rationale
- Optional: prior artifacts, external data

## Preconditions (MUST)
- Inclusion criteria are defined before collecting materials.
- Exclusion criteria are defined to prevent context bloat.

## Invariants (MUST hold during stage)
- Every artifact must be traceable to anchor relevance.
- Added context must improve decision quality, not volume.

## Anti-patterns (MUST NOT)
- Indiscriminate context accumulation.
- Treating quantity of data as quality.

## Outputs
- Mandatory: curated assembly set + relevance map
- Optional: dependency graph

## Exit criteria
- Each included item has a relevance tag.
- Excluded items are logged when contentious.

## Evidence artifacts
- assembly manifest
- inclusion/exclusion checklist

## Failure signals
- Unbounded list of references.
- Missing rationale for major artifacts.

## Recovery protocol
Prune assembly to criteria; revalidate against anchor and objective constraints.

## Hand-off contract
- Next stage: 03 Orientation
- Hand-off payload: curated set + relevance map
- Hand-off quality checks: orienter can derive directional model without extra collection
