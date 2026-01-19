# QFT Failure Manifold — Documentation

**Complete documentation for all 100 computational experiments exploring Quantum Field Theory's boundaries.**

---

## Quick Navigation

### By Phase (Thematic Organization)

| Phase | Topic | Toys | Description |
|-------|-------|------|-------------|
| **I** | [Free Field Theory & UV/IR Regulation](toys/phase_01_free_field_theory_and_regulation.md) | 001-010 | Vacuum correlators, regulators, microcausality |
| **II** | [Vacuum Structure & State Ambiguity](toys/phase_02_vacuum_structure_and_state_ambiguity.md) | 011-020 | Inequivalent vacua, Haag's theorem, Reeh-Schlieder |
| **III** | [Locality, Gauge Structure, & Factorization](toys/phase_03_locality_gauge_structure_and_factorization.md) | 021-030 | Gauge redundancy, subsystem decomposition, IR divergences |
| **IV** | [Operational Limits & Measurement Theory](toys/phase_04_operational_limits_and_measurement_theory.md) | 031-040 | Detector resolution, superselection, finite-time effects |
| **V** | [Backreaction, Subsystem Dynamics, & Thermality](toys/phase_05_backreaction_subsystem_dynamics_and_thermality.md) | 041-050 | Non-unitary evolution, KMS condition, thermal ambiguity |
| **VI** | [Entanglement Wedges & Information Localization](toys/phase_06_entanglement_wedges_and_information_localization.md) | 051-060 | Boundary conditions, formulation choices, system/environment split |
| **VII** | [Truncation, Unitarity, & Lattice Effects](toys/phase_07_truncation_unitarity_and_lattice_effects.md) | 061-070 | Hilbert space truncation, lattice artifacts, Ward identities |
| **VIII** | [Chaos, Modular Structure, & Diagnostics](toys/phase_08_chaos_modular_structure_and_diagnostics.md) | 071-080 | OTOC, modular Hamiltonians, spectral reconstruction |
| **IX** | [Failure-Mode Meta-Structure](toys/phase_09_failure_mode_meta_structure.md) | 081-085 | Cross-theory comparisons, failure classification |
| **X** | [Vacuum Energy & Cosmological Implications](toys/phase_10_vacuum_energy_and_cosmology.md) | 086-090 | Casimir effects, de Sitter construction, EFT positivity |
| **XI** | [Advanced Structure & Boundary Diagnostics](toys/phase_11_advanced_structure_and_boundary_diagnostics.md) | 091-100 | RG fixed points, global reconstruction, thermalization |

---

## Alternative Navigation

### By Index
- [By Toy Number](indices/by_toy_number.md) — Sequential list 001-100
- [By Topic](indices/by_topic.md) — Free fields, gauge theory, renormalization, etc.
- [By Failure Mode](indices/by_failure_mode.md) — UV/IR divergence, gauge ambiguity, etc.
- [Quick Reference Table](indices/quick_reference.md) — All toys with classifications

### Guides
- [Getting Started](guides/getting_started.md) — How to use this documentation
- [JSON Interpretation](guides/json_interpretation.md) — Reading toy outputs
- [Common Pitfalls](guides/common_pitfalls.md) — What not to conclude

---

## Documentation Structure

Each toy description includes:

1. **Physical Setup** — What is being modeled and why
2. **Stress Test Purpose** — What conceptual trap or limitation is exposed
3. **JSON Interpretation Guide** — How to read the output fields
4. **Mathematical Context** — Key equations and scaling laws
5. **Over-interpretation Warnings** — What NOT to conclude from the results

---

## Philosophy

These toys are **pressure tests**, not predictions. Each is designed to:
- Isolate a specific assumption or limit of QFT
- Make failure observable and reproducible
- Classify the type and sharpness of breakdown
- Map where QFT transitions from fundamental to effective

**The goal:** Understand precisely where and how Quantum Field Theory stops being well-defined.

---

## How to Use This Documentation

### For Learning QFT's Limits
Start with **Phase I** (free field theory) and work sequentially through the phases. Each builds on concepts from previous phases.

### For Research
Use the **index files** to find toys relevant to your specific question:
- Studying gauge structure? → See [By Topic](indices/by_topic.md)
- UV/IR issues? → See [By Failure Mode](indices/by_failure_mode.md)
- Need renormalization examples? → Jump to **Phases V-VII**

### For Implementation
Each toy description includes:
- Expected JSON output structure
- Key diagnostic fields to check
- Common numerical issues
- How to verify correctness

---

## Quick Links

**Main Repository:** [README.md](../README.md)  
**Toy Implementations:** [toys/](../toys/)  
**Execution Guide:** [toys/COMMANDS.md](../toys/COMMANDS.md)

---

*Documentation organized by Claude, toy descriptions created through systematic QFT boundary analysis.*
