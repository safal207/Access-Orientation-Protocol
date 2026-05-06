# Scenario — Moderate Score, Strong Correction Loop

## Setup
Two agents are evaluated on the same multi-step planning benchmark.
- **Agent A** scores 81% on final-answer correctness. It rarely revises; when wrong, it commits to the wrong answer.
- **Agent B** scores 73% on the same metric. It detects its own uncertainty, rolls back, retrieves more evidence, and resubmits — sometimes within the time budget, sometimes not.

By score alone, Agent A "wins".

## Traditional metrics
| Metric | Agent A | Agent B |
|---|---|---|
| Final-answer accuracy | 81% | 73% |
| Median latency | 4.0s | 6.8s |
| Tool-call count | low | higher |

Conventional read: A is more accurate and cheaper.

## AOP rubric read
| Dimension | Agent A | Agent B |
|---|---|---|
| D1 Entry integrity | 2 | 3 |
| D4 Transition continuity | 1 | 3 |
| D5 Movement integrity | 1 (silent recoveries) | 3 (logged deviations) |
| D6 Trajectory stability | 1 (single-shot wins) | 3 (improves run-over-run) |
| D7 World validation | 1 | 2 |
| D8 Recovery discipline | 0 (no rollback ever) | 3 (rollback used and recorded) |

## Divergence pattern
- A's higher score sits on top of D8 = 0. A is right when it is right and silently wrong when it is wrong; the system has no internal correction channel.
- B's lower score is paired with D5/D6/D8 strength. B's wrong answers are **followed by** detected wrongness and a rollback path. Out of distribution, B is the system that survives.

## What the bridge requires here
- Both agents report rubric scores alongside task accuracy.
- The team writing the deployment decision must explicitly state which signal is authoritative.
- For a **bounded benchmark race**: A is acceptable.
- For a **production deployment under distribution shift**: B is the correct choice, and the +8 points of accuracy are not worth D8 = 0.

## Recovery direction for Agent A
- Introduce explicit transition gates so over-confident answers can be intercepted.
- Add deviation logging at stage 05 — silent recoveries are exactly the failure mode the rubric is built to catch.
- Add a rollback path so D8 can move off zero.

## Lesson for reviewers
"Higher score" can hide "no correction loop". The rubric is the instrument that surfaces this trade-off. The bridge requires that the trade-off is **named**, not averaged away.
