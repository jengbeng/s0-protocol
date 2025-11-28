# Core Axioms of the S0 Protocol (A1–A8)

This document defines the invariant axioms that constrain the S₀ protocol.  
These axioms cannot be altered, supplemented, or reinterpreted in any derivative work.  
They define the minimal structural conditions required for correct, deterministic, and collectively valid state transitions.

The axioms do not depend on technology, implementation, or domain.  
They apply equally in all environments where S₀ is used.

---

## A1 — Existence of Subjects

There exists a non-empty set of subjects:

**𝒮 ≠ ∅**

Subjects are entities capable of observing the input φ and producing reactions r.

---

## A2 — Equality of Subjects

All subjects in 𝒮 participate on equal structural terms.

No subject possesses privileged power over:

- the input φ,  
- the reaction set R,  
- the state x,  
- the history H,  
- the transition function F.

No subject may unilaterally control the transition process.

---

## A3 — Shared Input

All subjects have access to a shared, observable input:

**φ is available to every subject s ∈ 𝒮**

No subject may receive a private φ that determines the next state.

---

## A4 — Reaction Capability

Every subject can produce a reaction r in response to φ.

The collection of reactions:

**R = {r₁, r₂, …}**

must be structurally observable and usable by F.

A subject that cannot react is equivalent to a suppressed subject (T₁).

---

## A5 — Single Global Transition Function

There exists exactly one transition function:

**F : (x, φ, R) → x'**

F is:

- deterministic,  
- independent of any single subject,  
- reproducible,  
- globally valid for all subjects.

Multiple competing transition functions violate S₀ (T₄).

---

## A6 — Determinism

Given the same triple (x, φ, R), the transition function must always produce the same next state:

**F(x, φ, R) = x'** is unique and reproducible.

Nondeterminism or ambiguity violates the invariant structure.

---

## A7 — Reproducible Global History

The system must maintain a reproducible, verifiable global history:

**H = (x₀, x₁, x₂, …)**

History must arise solely from repeated application of F.

History cannot be rewritten arbitrarily.  
Recovery operations (S₁–S₇) may only restore correctness, not introduce new meaning.

---

## A8 — Consistency of Collective Transition

For any transition, the tuple (𝒮, φ, R, F, x, x') must satisfy all previous axioms.

A transition that violates any axiom is an incorrect transition (T₃).

Every correct transition must:

- treat all subjects equally,  
- use a shared φ,  
- accept the reaction set R as produced,  
- apply the invariant F,  
- produce a single next state,  
- extend history consistently.

---

## Purpose of Axioms

These axioms guarantee:

- equality of subjects,  
- determinism of transitions,  
- correctness of global history,  
- protection against monopolization (T₄),  
- protection against subject suppression (T₁),  
- protection against divergence (T₂),  
- protection against inconsistent transitions (T₃).

Together, they define the invariant core of the S₀ protocol.