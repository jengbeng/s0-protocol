# Core Definitions (S0 Protocol)

This document provides the minimal set of formal definitions used across the S₀ protocol, the stability levels S₁–S₇, and the meta-architecture X.  
All definitions are structural and technology-agnostic.  
No interpretations or implementations are included.

---

## 1. Subjects

**Subject (s ∈ 𝒮)**  
An entity capable of:

- receiving the input φ,  
- producing a reaction r,  
- participating equally in the transition process defined by S₀.

Subjects are not ranked, privileged, or ordered.  
All subjects have equal structural status.

**Set of subjects (𝒮)**  
A non-empty set.  
Its cardinality is not fixed and may change across transitions, provided the axioms of S₀ remain satisfied.

---

## 2. Inputs and Reactions

**Input (φ)**  
A piece of information accessible to subjects at the moment of transition.  
Inputs are shared, observable, and not dependent on any single subject.

**Reaction (r)**  
The output produced by a subject in response to φ.  
The full reaction set **R = {r₁, r₂, …}** is used by the transition function.

Reactions are not commands; they are structural signals used in the formation of the next state.

---

## 3. States

**State (x ∈ X)**  
A structural description of the system at a given point in the global history.

**State space (X)**  
The set of all possible states reachable under the axioms of S₀.

States may encode:

- subject configuration,  
- structural conditions,  
- previous transitions,  
- outputs of the meta-architecture (if active).

States are not semantic objects; S₀ does not prescribe their meaning.

---

## 4. Transition Function

**Transition function (F)**  

A deterministic mapping:

**F : (x, φ, R) → x'**

Properties:

- independent of any single subject,  
- reproducible,  
- globally consistent,  
- constrained by S₀ axioms,  
- produces exactly one next state x'.

**Correct transition**  
A transition is correct if it satisfies:

- the axioms A1–A8,  
- determinism of F,  
- equality of subjects,  
- consistency with the global history.

Incorrect transitions correspond to threat class T₃.

---

## 5. Global History

**History (H)**  
A reproducible, verifiable sequence of states:

**H = (x₀, x₁, x₂, …)**

Properties:

- generated exclusively by repeated application of F,  
- not modifiable retroactively (except in recovery under S₁–S₇),  
- shared across subjects and stability layers.

---

## 6. Threats

**Threat (T)**  
A structural deviation classified into one of the four invariant classes:

- **T₁** — loss or suppression of subjects  
- **T₂** — divergence of inputs or reactions  
- **T₃** — incorrect or inconsistent transitions  
- **T₄** — monopolization or domination of architecture

Threats are detected, not defined, by the meta-architecture X (τ).

---

## 7. Stability Levels

**Stability level (Sₙ, n=1..7)**  
A structural mechanism that:

- observes the system,  
- detects divergence,  
- restores consistency,  
- prevents monopolization.

Stability levels do **not** modify S₀ or F.  
They act externally to preserve correctness.

---

## 8. Meta-Architecture Components

**τ (tau)**  
Detector of anomalies.  
Classifies observed deviations into threat classes T₁–T₄.

**ρ (rho)**  
Selector.  
Chooses the minimal set of stability levels required to handle the detected threat set U.

**δ (delta)**  
Deactivation mechanism.  
Removes stability levels whose presence is no longer justified by history.

---

## 9. Architecture State

**Architecture state (m)**  
A subset:

**m ⊆ {S₁, S₂, S₃, S₄, S₅, S₆, S₇}**

The meta-architecture evolves as:

**m' = (m ∪ ρ(U)) \ δ(history)**

This produces a deterministic yet adaptive stability configuration.

---

## 10. Derivative Works

Derivative work is any file, structure, or transformation that:

- preserves the invariant core (S₀, Sₙ, X),  
- remains consistent with all definitions in this document,  
- does not introduce conflicting semantics.

Clarifications and additions are allowed if explicitly marked as non-core.

---

## 11. Purpose of Definitions

These definitions exist to ensure:

- clarity,  
- structural consistency,  
- reproducibility of reasoning,  
- unambiguous interpretation of S₀ and its extensions.

They do not prescribe implementation details or contextual meaning.