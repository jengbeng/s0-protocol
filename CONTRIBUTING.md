# Contributing to the S0 Repository

This document describes the minimal, invariant contribution process for the S₀ core, the stability levels S₁–S₇, and the meta-architecture X.  
All contributions must preserve the formal structure and constraints defined by the S₀–Sₙ+X specification.

---

## 1. Principles

1. Do not modify or reinterpret:
   - the S₀ axioms (A1–A8),
   - the definition of the transition function **F**,
   - the classification of threats **T₁–T₄**,
   - the definitions of stability levels **S₁–S₇**,
   - the meta-architecture X (τ, ρ, δ).

2. All changes must be:
   - structural (not interpretative),
   - minimal (no unrelated edits in the same PR),
   - verifiable (traceable to explicit inputs and files).

3. No contribution may:
   - introduce privileged subjects,
   - create non-deterministic transitions,
   - add new core axioms or new threat types,
   - change the meaning of S₀, Sₙ, or X.

---

## 2. Scope of Allowed Changes

Allowed:

- structural clarifications that do not change semantics,  
- improved organization of files and cross-references,  
- additional invariant examples in `/examples` and `/applications`,  
- documentation of properties, theorems, and proofs consistent with the core,  
- improvements to CI/workflows under `.github/workflows`.

Not allowed:

- philosophical, political, or implementation-specific commentary,  
- changes that introduce new semantics or reinterpret existing ones,  
- alternative definitions of **F**, **T₁–T₄**, or **S₁–S₇**,  
- changes that depend on specific technologies or platforms.

If in doubt, open an Issue first and describe the proposed change.

---

## 3. Workflow Overview

All contributions follow this pattern:

1. **Open an Issue** describing the proposed change.  
2. **Map the change to an explicit input φ** (the request or anomaly the change addresses).  
3. **Create a Pull Request (PR)** referencing that Issue.  
4. Ensure the PR passes all automated checks.  
5. The PR is reviewed for structural correctness and invariance.  
6. If accepted, the PR is merged according to the governance rules.

---

## 4. Issues

Every change begins with an Issue.

An Issue must include:

- a concise description of the proposed change,  
- the reason or motivation (linked to φ, if applicable),  
- the exact files and sections that will be affected,  
- a statement confirming that the change does not violate:
  - S₀ axioms,  
  - threat classification,  
  - stability-level definitions,  
  - meta-architecture constraints.

Issues without this information may be closed without review.

Recommended Issue template:

- **Title:** short, structural description (e.g. “Clarify S₁ definition in stability_levels_S1_S7.md”)  
- **Context:** why this is needed (φ)  
- **Files:** list of target files  
- **Type:** clarification / example / workflow / property / theorem  
- **Impact:** expected effect on understanding or structure

---

## 5. Pull Requests

A Pull Request must:

- reference the Issue that initiated the change,  
- contain only the minimal set of modifications needed to resolve that Issue,  
- avoid mixing multiple unrelated changes,  
- keep diffs small and readable.

PR guidelines:

- keep each commit logically isolated,  
- do not reformat entire files unless formatting is the subject of the Issue,  
- do not rename files or move them between directories without explicit rationale.

PRs that alter the meaning of S₀–Sₙ+X or introduce non-invariant content will be rejected.

---

## 6. Repository Structure Constraints

All changes must respect the repository structure:

```text
/foundation
    definitions.md
    core_axioms_S0.md
    state_transition_function.md

/threats
    threat_classes_T1_T4.md
    anomalies_and_history.md

/stability
    stability_levels_S1_S7.md
    stability_matrix.md
    recovery_mechanisms.md

/architecture
    architecture_principles.md
    level_interaction.md
    architectural_transition_examples.md

/dynamics
    meta_architecture_X.md
    tau_detector.md
    rho_selector.md
    delta_deactivation.md
    dynamic_generation.md

/theorems
    self_organization_theorem.md
    corollaries.md

/properties
    system_properties.md

/applications
    small_groups.md
    distributed_systems.md
    technology_free_systems.md
    merging_systems.md
    families.md

/examples
    minimal_s0.md
    example_architectural_transition.md

/extensions
    category_theory_formalization.md
    analogies.md
    scope_and_limits.md

/governance
    governance_principles.md
    modification_rules.md

/spec
    S0_full_specification.md
    SnX_full_specification.md

/history
    changelog.md

/.github/workflows
    check.yml
    merge.yml

New files should be added only if:
	•	they belong to one of these directories, and
	•	their role is structurally clear and documented in the relevant section.

⸻

7. Automated Checks

Every PR is validated by GitHub workflows defined in .github/workflows:
	•	structure and path validation,
	•	basic formatting checks,
	•	repository consistency checks (where applicable).

A PR cannot be merged if these checks fail.

⸻

8. Review Process

Reviewers focus on:
	•	structural correctness relative to S₀–Sₙ+X,
	•	consistency with the threat model and stability levels,
	•	absence of implicit reinterpretation or new semantics,
	•	clarity and minimality of the change.

If a change is ambiguous, reviewers may request:
	•	additional justification,
	•	a clearer mapping to φ and the threat model,
	•	splitting the PR into smaller, more focused parts.

⸻

9. Governance and Final Decisions

Governance rules are documented in /governance:
	•	maintainers manage infrastructure and CI,
	•	the semantic core of S₀–Sₙ+X is not changed by unilateral decisions,
	•	changes to core definitions (foundation, threats, stability, dynamics, spec) require explicit, documented reasoning and broader review.

In case of disagreement, the default behavior is to preserve the existing invariant structure until a clearly justified and formally consistent modification is agreed upon.

⸻

10. License of Contributions

By submitting a contribution, you agree that:
	•	your changes become part of the S₀–Sₙ+X repository,
	•	they must remain compatible with the invariant protocol,
	•	they may be further refactored for clarity, as long as semantics remain unchanged.

Thank you for helping keep the S₀ protocol invariant, minimal, and verifiable.

