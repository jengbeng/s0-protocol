# SnX Full Specification (Stability Levels S₁–S₇ and Meta-Architecture X)

This document defines the full specification of the stability levels **S₁–S₇** and the meta-architecture **X = {τ, ρ, δ}**.  
These components extend S₀ by providing mechanisms for detection, correction, and prevention of structural violations, without modifying the invariant core of the protocol.

Stability levels and X are external to S₀:  
they observe, verify, restore, and protect — but do not alter S₀’s axioms or the transition function F.

---

# 1. Purpose of Sₙ

The stability levels exist to:

- detect structural violations (threats T₁–T₄),  
- ensure correctness of transitions,  
- maintain consistency of global history H,  
- restore proper system structure after incorrect transitions,  
- prevent monopolization or suppression within the architecture.

Sₙ does **not** add new semantics to S₀.  
Sₙ only ensures that S₀ operates correctly under real-world conditions.

---

# 2. Threat Classes

All violations are grouped into four invariant threat classes:

- **T₁ — Subject loss or suppression**  
- **T₂ — Divergence of inputs or reactions**  
- **T₃ — Incorrect or inconsistent transitions**  
- **T₄ — Architectural domination or monopolization**

The meta-architecture X identifies threats and activates the required stability levels.

---

# 3. Overview of Stability Levels (S₁–S₇)

Each stability level addresses particular subsets of threats.  
Levels may operate alone or in combination, depending on τ and ρ.

The levels are:

- **S₁ — Local Reproducibility**
- **S₂ — Cross-Subject Reproducibility**
- **S₃ — History Verification**
- **S₄ — Divergence Detection**
- **S₅ — Structural Restoration**
- **S₆ — Transition Reconciliation**
- **S₇ — Anti-Monopolization and Architectural Balance**

Each level is defined precisely in Sections 4–10.

---

# 4. S₁ — Local Reproducibility

Ensures that:

- a subject can recompute F(x, φ, R) locally,  
- the transition is reproducible by any independent observer.

Addresses:

- incorrect transitions (T₃)

S₁ is the minimal level required for validating deterministic transitions.

---

# 5. S₂ — Cross-Subject Reproducibility

Ensures agreement across all subjects:

- subjects must independently recompute F  
- their results must match

Addresses:

- divergence in subject computations (T₂, T₃)

If subjects disagree, higher levels must activate.

---

# 6. S₃ — History Verification

Ensures that:

- the global history H is valid,  
- every state in H results from repeated application of F,  
- no hidden rewrites have occurred.

Addresses:

- history inconsistencies (T₃)  
- partial subject suppression affecting history (T₁)

If history diverges, S₃ activates restoration via S₅–S₆.

---

# 7. S₄ — Divergence Detection

Detects:

- inconsistent φ across subjects (T₂)  
- missing or suppressed reactions (T₁)  
- nondeterministic or ambiguous transitions (T₃)

S₄ is the "early warning system" of Sₙ.  
It does not repair — only detects.

---

# 8. S₅ — Structural Restoration

Restores structural correctness after a violation:

- reconstructs the proper reaction set R  
- ensures consistent φ  
- reestablishes valid subject participation  
- prepares the system for a valid transition

Addresses:

- subject suppression (T₁)  
- input divergence (T₂)

S₅ does not rewrite history except for restoring correctness.

---

# 9. S₆ — Transition Reconciliation

Reconciles incorrect transitions by:

- recomputing expected outputs  
- comparing with actual outputs  
- reintroducing the corrected state into history  
- ensuring determinism and reproducibility

Addresses:

- incorrect transitions (T₃)

S₆ may operate on multiple consecutive states if needed.

---

# 10. S₇ — Anti-Monopolization and Architectural Balance

Protects the protocol from domination or control:

- monitors access to φ, R, F, and history  
- prevents any subject or subset of subjects from controlling transitions  
- detects attempts to override or replace F  
- ensures decentralization of influence

Addresses:

- monopolization or domination (T₄)

S₇ guarantees architectural equality even under adverse conditions.

---

# 11. Interaction Matrix of Levels

Stability levels may activate in combinations.  
A high-level matrix:

| Threat | S₁ | S₂ | S₃ | S₄ | S₅ | S₆ | S₇ |
|--------|----|----|----|----|----|----|----|
| T₁     |    |    | X  | X  | X  |    | X  |
| T₂     |    | X  |    | X  | X  |    |    |
| T₃     | X  | X  | X  | X  |    | X  |    |
| T₄     |    |    |    |    |    |    | X  |

X = may activate depending on history and τ.

---

# 12. Meta-Architecture X

X is composed of:

- **τ — threat detector**  
- **ρ — stability selector**  
- **δ — stability deactivation**

These components operate over the global history and observable system behavior.

Sₙ activation does not depend on subject input; it is fully structural.

---

# 13. τ (Tau) — Threat Detection

τ analyzes observable system properties and classifies anomalies into:

**U ⊆ {T₁, T₂, T₃, T₄}**

Properties:

- deterministic  
- based on structural inconsistencies  
- does not rely on subjective interpretation  
- may operate continuously or episodically

---

# 14. ρ (Rho) — Stability Selection

Given a threat set U, ρ selects the minimal required stability levels:

**ρ(U) ⊆ {S₁, S₂, S₃, S₄, S₅, S₆, S₇}**

ρ is minimal in the sense that:

- no unnecessary levels are activated  
- selection is deterministic  
- selection is reproducible across subjects

Example:

- if U = {T₃}, then ρ(U) = {S₁, S₂, S₃, S₆}

---

# 15. δ (Delta) — Stability Deactivation

δ determines when stability levels can be safely removed.

Given the global history H:

**δ(H) ⊆ {S₁, S₂, …, S₇}**

A level Sₙ may deactivate if:

- its associated threat has not recurred,  
- history is stable,  
- structural correctness is restored.

δ guarantees that stability layers do not grow indefinitely.

---

# 16. Architecture State

The active stability set is:

**m ⊆ {S₁..S₇}**

The meta-architecture evolves as:

**m' = (m ∪ ρ(U)) \ δ(H)**

This ensures deterministic yet adaptive system behavior.

---

# 17. Guarantees Provided by SnX

SnX provides:

- detection of structural failures  
- restoration of system correctness  
- verification of deterministic transitions  
- protection against subject suppression  
- prevention of monopolization  
- long-term architectural resilience  
- consistency of global history  
- invariance of S₀ regardless of environmental conditions

---

# 18. Non-Scope

SnX does **not**:

- modify S₀ axioms,  
- modify the transition function F,  
- introduce new definitions of φ or R,  
- alter state semantics,  
- define governance systems,  
- impose implementation or platform constraints.

SnX is purely structural.

---

# 19. Purpose

The purpose of SnX is to ensure that the invariant S₀ protocol:

- remains correct under real-world conditions,  
- is protected from structural violations,  
- can recover from incorrect transitions,  
- cannot be monopolized or corrupted,  
- remains verifiable and reproducible over time.

S₀ defines *what* a correct transition is.  
SnX defines *how to protect it*.