# Minimal Core vs Derived Extensions

This document distinguishes the minimal core of the Access Orientation Protocol from interpretations and extensions that may be built on top of it.

## Minimal core

The minimal core consists of:
- the canonical eight-part cycle;
- the mandatory entry boundary **Resonance (Self)**;
- the mandatory completion boundary **Resonance (World)**;
- the loop-based architecture;
- the core vocabulary required to discuss orientation, transition, movement, trajectory, drift, and integrity.

The minimal core is the part of the repository that defines what the protocol is.

## Derived extensions

Derived extensions apply the protocol to particular contexts without redefining the protocol itself. Current examples include:
- benchmarking and evaluation interpretations;
- domain-specific worked examples;
- lightweight reference models;
- future implementation notes that clarify, rather than replace, the protocol.

Derived extensions should remain downstream of the core architecture.

## Boundary rule

If an extension changes the meaning of the canonical cycle, weakens the mandatory role of **Resonance (Self)** or **Resonance (World)**, or collapses orientation into planning or execution, it is no longer acting as an extension. It is redefining the protocol.

## Current repository stance

At the current stage of the repository:
- `README.md`, `docs/ARCHITECTURE.md`, `docs/TECHNICAL_BRIEF.md`, `docs/GLOSSARY.md`, `docs/STRESS_TEST.md`, `docs/COMPARISON.md`, and `docs/ANTI_PATTERNS.md` primarily describe the minimal core;
- `docs/BENCHMARK.md` is an early derived interpretation;
- future examples or implementations should be added only if they preserve the distinction between core and extension.
