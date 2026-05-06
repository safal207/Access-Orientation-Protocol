# Scenario — Fast Response, Poor Trajectory Stability

## Setup
A summarization agent is tuned aggressively for latency. Per-request time drops from 4.2s to 0.9s. Per-request quality, judged on a single-turn benchmark, holds steady at ~0.84 ROUGE.

The same agent is used by an analyst who runs **a series** of summarization requests across a week to build a longitudinal report.

## Traditional metrics
- Median latency: **0.9s** (down from 4.2s)
- Single-turn quality (ROUGE): **0.84** (flat)
- Cost per request: down ~3x

Conventional read: a clean Pareto win.

## AOP rubric read
- D1 Entry integrity: **2** — self-state probe shortened to a single confidence flag.
- D2 Assembly relevance: **1** — to hit latency, retrieval window narrowed and provenance tags dropped.
- D3 Orientation depth: **2** — orientation reduced to "pick the top-k spans" without relation mapping.
- D4 Transition continuity: **2**.
- D5 Movement integrity: **2** — no deviation log emitted (overhead).
- D6 Trajectory stability: **0** — across the analyst's week, summaries silently drift in framing because each request is decoupled from the previous orientation.
- D7 World validation: **1** — analyst notices "the picture changed" mid-week without a regression in any single summary.
- D8 Recovery discipline: **1** — no rollback path because there is no per-request memory of previous orientation.

## Divergence pattern
- Per-request metrics look identical or better.
- D6 collapses because the speed optimization removed the inter-request continuity that trajectory stability depends on.
- The benchmark is per-request; the **use** is longitudinal. The metric and the use are not the same thing, and the rubric is the place where this gap becomes visible.

## What the bridge requires here
- A **transfer risk statement**: "if downstream use is longitudinal, per-request latency wins are paid for in cross-request drift. We will detect this only via D6."
- An explicit decision: speed wins are acceptable for **independent** requests, not for **series**.

## Recovery direction
- Restore enough cross-request memory to evaluate D6.
- Add a longitudinal stability probe alongside the per-request benchmark.
- Treat D6 = 0 as a deployment blocker for longitudinal use, regardless of latency wins.

## Lesson for reviewers
A win on a per-request metric can come at the cost of a dimension the per-request metric cannot see. The rubric is the mechanism by which trajectory stability is **named** rather than discovered late.
