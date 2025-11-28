# State Transition Function (F) in the S0 Protocol

This document defines the invariant transition function **F**, which generates the next system state from the current state, the shared input, and the set of subject reactions.

The definition of **F** is part of the invariant core of S₀ and cannot be altered or reinterpreted.

---

## 1. Formal Definition

The transition function is a deterministic mapping:

**F : (x, φ, R) → x'**

Where:

- **x** — current state  
- **φ** — shared input available to all subjects  
- **R** — set of reactions produced by subjects  
- **x'** — next state

F must produce exactly **one** next state for any valid triple (x, φ, R).

---

## 2. Deterministic Requirements

For all valid inputs:

If **(x₁ = x₂) and (φ₁ = φ₂) and (R₁ = R₂)**, then:

**F(x₁, φ₁, R₁) = F(x₂, φ₂, R₂)**

No randomness.  
No external dependencies.  
No subject may alter the output of F unilaterally.

---

## 3. Independence from Subjects

F is independent of any single subject:

- no subject defines F,  
- no subject may override F,  
- F is common to all subjects,  
- all subjects must be able to derive or verify F.

Monopolization or private modification of F corresponds to threat class **T₄**.

---

## 4. Valid Inputs

The function F may only be applied if:

1. All subjects share the same φ (A3)  
2. All subjects can react (A4)  
3. The reaction set R is collectively observable  
4. The current state x is part of the global history  
5. The axioms A1–A8 are satisfied

If these conditions are violated, the transition is invalid and classified under **T₃**.

---

## 5. Output Requirements

The resulting state **x'** must:

- extend the global history H correctly,  
- not contradict any previous state,  
- be verifiable by all subjects,  
- not require privileged knowledge,  
- preserve determinism.

History evolves as:

**H = (x₀, x₁, x₂, …)**  
with each **xₙ = F(xₙ₋₁, φₙ₋₁, Rₙ₋₁)**.

---

## 6. Invalid Transitions

A transition is invalid if:

- inputs differ across subjects (T₂),  
- reactions are suppressed or missing (T₁),  
- the transition violates any axiom (T₃),  
- multiple competing definitions of F appear (T₄),  
- F produces more than one possible next state,  
- F requires hidden or private information.

Invalid transitions must be detected and corrected by stability mechanisms (S₁–S₇).

---

## 7. Observability and Verification

F must be:

- **observable** — subjects can inspect inputs and verify output,  
- **reproducible** — the same triple must yield the same x',  
- **structurally transparent** — not dependent on implementation details.

Verification of F is fundamental for:

- maintaining consistent global history,  
- detecting incorrect transitions (T₃),  
- enabling recovery mechanisms under stability levels.

---

## 8. Purpose of the Transition Function

F exists to ensure that:

- state evolution is deterministic,  
- subjects remain equal,  
- history remains consistent,  
- transitions are verifiable,  
- system behavior cannot be monopolized,  
- violations can be detected and repaired through S₁–S₇.

F is the mechanism that binds subjects, inputs, reactions, and states into one coherent process.