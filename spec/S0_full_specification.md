# S0 Full Specification (Invariant Core Protocol)

This document defines the full formal specification of **S₀**, the invariant protocol governing state transitions in systems composed of multiple subjects.  
S₀ establishes the minimal structural conditions required for correct, deterministic, reproducible, and collectively valid transitions.

S₀ is technology-agnostic, domain-agnostic, and cannot be reinterpreted or extended in ways that modify its invariant core.

---

# 1. Entities of the Protocol

S₀ defines the following invariant elements:

- **𝒮** — set of subjects  
- **φ** — shared input  
- **R** — set of reactions produced by subjects  
- **x ∈ X** — current system state  
- **x'** — next system state  
- **F** — deterministic transition function  
- **H** — global history of transitions

These elements form the minimal ontology of the protocol.

---

# 2. Subjects

A **subject (s ∈ 𝒮)** is an entity capable of:

1. observing the shared input φ  
2. producing a reaction r  
3. participating equally in the transition process

Properties:

- 𝒮 must be non-empty.  
- No subject has privileged access to φ, R, x, or F.  
- No subject may unilaterally influence F or history H.  
- Subjects may appear or disappear, provided A1–A8 remain satisfied.

---

# 3. Inputs (φ)

**φ** is the shared input available to all subjects.

Requirements:

- φ must be the same for all subjects.  
- φ must be observable.  
- φ must not depend on a single privileged subject.  

Violations of shared input correspond to **T₂**.

---

# 4. Reactions (R)

Each subject produces a reaction:

**rᵢ = reaction(sᵢ, φ)**

The set of all reactions is:

**R = {r₁, r₂, …}**

Requirements:

- all subjects must have the ability to react (A4)  
- reactions must be observable  
- reactions must be available to F  
- suppressed or missing reactions correspond to **T₁**

---

# 5. States and State Space

A **state (x ∈ X)** is a structural description of the system at a given moment.

S₀ does not define the semantic meaning of states; it defines only their role in transitions.

The **state space X** contains all states reachable through valid applications of F.

---

# 6. Transition Function (F)

The transition function is defined as:

**F : (x, φ, R) → x'**

Properties:

- deterministic (A6)  
- reproducible  
- independent of any single subject  
- common to all subjects  
- uniquely maps each valid triple to a single next state

Incorrect or inconsistent transitions correspond to **T₃**.

---

# 7. Global History (H)

History is a sequence of states:

**H = (x₀, x₁, x₂, …)**

Generated exclusively by repeated application of F:

**xₙ = F(xₙ₋₁, φₙ₋₁, Rₙ₋₁)**

Requirements:

- history must be reproducible (A7)  
- history may not be arbitrarily rewritten  
- recovery operations may restore correctness but not introduce semantic change

---

# 8. Axioms of S₀ (A1–A8)

The invariant core of S₀ is defined by eight axioms:

### **A1 — Existence of subjects**  
𝒮 ≠ ∅

### **A2 — Equality of subjects**  
No subject is privileged in access, influence, or authority.

### **A3 — Shared input**  
All subjects observe the same φ.

### **A4 — Reaction capability**  
All subjects can produce reactions r.

### **A5 — Single transition function**  
There exists exactly one deterministic F.

### **A6 — Determinism**  
Given identical (x, φ, R), F must yield exactly one x'.

### **A7 — Reproducible global history**  
History must be verifiable and derive solely from F.

### **A8 — Collective consistency**  
All transitions must satisfy the previous axioms.

Violations:

- A1/A2 → T₁  
- A3/A4 → T₂  
- A5/A6/A7/A8 → T₃ or T₄ depending on structure

---

# 9. Correct vs. Incorrect Transitions

A **correct transition** satisfies:

- A1–A8  
- deterministic output  
- shared input φ  
- complete reaction set R  
- global verification  
- architectural independence

An **incorrect transition**:

- contradicts any axiom  
- uses divergent inputs  
- suppresses reactions  
- introduces nondeterminism  
- rewrites history  
- depends on a privileged subject

Incorrect transitions must be detected and handled by stability levels (S₁–S₇), defined separately in the SnX specification.

---

# 10. Structural Violations and Threat Classes

All structural violations fall into four classes:

- **T₁** — subject loss/suppression  
- **T₂** — divergence of φ or R  
- **T₃** — incorrect or inconsistent transitions  
- **T₄** — monopolization or domination of architecture

These threat classes form the basis for stability mechanisms.

---

# 11. Guarantees Provided by S₀

S₀ ensures:

- equal participation of subjects  
- deterministic evolution  
- verifiable history  
- independence from centralized authority  
- protection against structural failures  
- the ability to detect violations  
- the ability to recover from incorrect transitions (using S₁–S₇)

---

# 12. Non-Scope of S₀

S₀ does not define:

- practical governance mechanisms  
- semantics of states  
- messaging protocols  
- consensus algorithms  
- incentives  
- implementation details  
- political, philosophical, or normative content

S₀ defines **only the invariant core of collective state transitions**.

---

# 13. Purpose of S₀

The purpose of S₀ is to provide:

- a minimal formal foundation,  
- universal across domains,  
- resistant to monopolization,  
- immune to interpretative drift,  
- capable of supporting higher-order structures (Sₙ, X),  
- suitable for open and verifiable collective systems.

S₀ is designed to be the minimal invariant substrate upon which more complex architectures can be built.