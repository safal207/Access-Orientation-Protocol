# Scenario — High Benchmark Score, Weak World Transfer

## Setup
A QA agent is evaluated on a closed-set technical-question benchmark. It scores 92% on exact-match accuracy. The same agent is then deployed to answer real engineer questions in a production support channel.

## Traditional metrics
- Accuracy on benchmark: **92%**
- Latency: median 3.1s
- Cost per query: within budget
- Safety: no blocked categories triggered

By any conventional read, the system is "ready".

## AOP rubric read (per `docs/EVALUATION_RUBRIC.md`)
- D1 Entry integrity: **1** — the agent does not run a self-state probe; it answers from the prompt directly.
- D2 Assembly relevance: **2** — retrieval is broad but not bounded by freshness or provenance.
- D3 Orientation depth: **2** — claims are produced, but evidence pairing is implicit.
- D4 Transition continuity: **1** — generation begins without an explicit gate.
- D5 Movement integrity: **2** — no deviation logging; recoveries are silent.
- D6 Trajectory stability: not assessed (single-shot).
- D7 World validation: **0** — no external check beyond benchmark labels.
- D8 Recovery discipline: **0** — no rollback ever observed; "no failure" is treated as a red flag, not as success.

## Divergence pattern
- The benchmark score reports task surface only.
- D7 = 0 means the system has no world-validation channel; benchmark labels are not "world".
- D1 = 1 and D4 = 1 mean entry and transition gates are missing; the high score may not survive distribution shift.

## What the bridge requires here
- A **transfer risk statement**: "engineers ask follow-up questions and act on answers; if attribution is wrong, downstream debugging time increases. We have no detector for this."
- An explicit decision about which signal is authoritative: **the rubric is authoritative for the deployment question**, the benchmark is authoritative only for "is the model in the right ballpark before we even consider deploying".

## Recovery direction (per stress-test patterns)
- Add a self-state probe at 00 (retrieval health, known-unknowns).
- Add a transition gate at 04 (refuse to answer when evidence coverage is below threshold).
- Add an external validation channel at 07 (engineer thumbs-up/down + spot-check on a sample).
- Treat the 92% score as **necessary but not sufficient**.

## Lesson for reviewers
A high task score with rubric scores at 0–1 on D1, D4, D7, D8 is the canonical "elegant internally, unreliable externally" pattern. The benchmark cannot detect this; the rubric is built for exactly this case.
