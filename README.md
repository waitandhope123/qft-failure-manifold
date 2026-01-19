# QFT Boundary Lab

**Mapping QFT's boundary manifold: 100 computational experiments stress-testing Quantum Field Theory through UV/IR divergences, vacuum structure, gauge redundancy, renormalization ambiguity, entanglement limits, and effective theory breakdown**

This repository contains a structured collection of minimal computational "toys" designed to **locate, reproduce, and classify failure modes of quantum field theory (QFT)**. Rather than proposing new physics or alternatives to QFT, the lab systematically probes **where and how QFT loses predictive or operational meaning**.

The result is an explicit map of QFT treated honestly as an **effective theory**.

---

## What this project is

- A **diagnostic test suite**, not a model or simulator
- A **boundary-mapping exercise**, not a refutation of QFT
- A collection of **minimal pressure tests** that isolate specific assumptions
- A reproducible way to classify **failure triggers and failure modes**
- A systematic analysis of what the **pattern of failures** reveals about QFT's nature

Each toy is intentionally simple and adversarial: it is designed to make a specific assumption of QFT fail cleanly and observably.

---

## What this project is not

- ❌ Not a claim that QFT is empirically false  
- ❌ Not a replacement theory  
- ❌ Not a quantum gravity proposal  
- ❌ Not a lattice QCD or production simulation code  

Nothing here contradicts quantum field theory. Instead, the lab shows **where the formalism stops being sufficient to define unique, regulator-independent, or operationally well-defined physics**.

---

## Structure of the lab

The lab consists of **100 toys**, grouped into phases that reflect increasingly subtle or global limits of the theory:

1. **Free Field Theory & UV/IR Regulation** — Vacuum correlators, regulators, microcausality
2. **Vacuum Structure & State Ambiguity** — Inequivalent vacua, Haag's theorem, Reeh-Schlieder
3. **Locality, Gauge Structure, & Factorization** — Gauge redundancy, subsystem decomposition, IR divergences
4. **Operational Limits & Measurement Theory** — Detector resolution, superselection, finite-time effects
5. **Backreaction, Subsystem Dynamics, & Thermality** — Non-unitary evolution, KMS condition, thermal ambiguity
6. **Entanglement Wedges & Information Localization** — Boundary conditions, formulation choices, system/environment split
7. **Truncation, Unitarity, & Lattice Effects** — Hilbert space truncation, lattice artifacts, Ward identities
8. **Chaos, Modular Structure, & Advanced Diagnostics** — OTOC, modular Hamiltonians, spectral reconstruction
9. **Failure-Mode Meta-Structure** — Cross-theory comparisons, failure classification
10. **Vacuum Energy & Cosmological Implications** — Casimir effects, de Sitter construction, EFT positivity
11. **Advanced Structure & Boundary Diagnostics** — RG fixed points, global reconstruction, thermalization

Each toy is classified along multiple axes:

- **Failure Trigger**  
  (UV divergence, IR divergence, gauge artifact, vacuum inequivalence, observer dependence, regulator dependence, scheme dependence, boundary effect, truncation, measurement ambiguity, formulation choice)

- **Failure Mode**  
  (regulator dependence, scheme dependence, vacuum ambiguity, gauge non-uniqueness, state dependence, observer dependence, operational undefinedness, predictability loss, constraint violation, factorization failure, non-commutativity of limits)

- **Failure Sharpness**  
  (sharp, contextual, thick)

- **Repairable Within Standard QFT**  
  (yes / no / reinterpretation only)

---

## Executed results

All executed toys include **machine-readable JSON outputs** encoding observed results such as:

- UV/IR divergences and regulator dependence
- Vacuum state inequivalence
- Gauge artifact vs physical effect separation
- Renormalization scheme dependence
- Observer-dependent thermality
- Subsystem factorization failure
- Measurement-induced disturbances
- Entanglement entropy divergences
- Constraint violations under effective evolution
- Non-commuting limit operations
- Spectral reconstruction ambiguities
- EFT breakdown signals

---

## v1.0.0: Initial Release

**This release includes:**

### Complete Documentation System
All 100 toys have comprehensive documentation including:
- **Physical setup** — What the toy models and why
- **Stress test purpose** — What conceptual trap or limitation is exposed
- **JSON interpretation guide** — How to read the output fields
- **Mathematical context** — Key equations and scaling laws
- **Over-interpretation warnings** — What NOT to conclude

### Eleven Thematic Phases

**Phase I: Free Field Theory & UV/IR Regulation (Toys 001-010)**  
Vacuum correlators, regulators, Bogoliubov transformations, and the structure of free theories

**Phase II: Vacuum Structure & State Ambiguity (Toys 011-020)**  
Vacuum instability, inequivalent representations, Haag's theorem, and Reeh-Schlieder consequences

**Phase III: Locality, Gauge Structure, & Factorization (Toys 021-030)**  
Gauge redundancy, IR divergences, subsystem decomposition, and the failure of strict locality

**Phase IV: Operational Limits & Measurement Theory (Toys 031-040)**  
Detector resolution, superselection sectors, Haag duality, and finite-volume artifacts

**Phase V: Backreaction, Subsystem Dynamics, & Thermality (Toys 041-050)**  
Non-unitary subsystem evolution, KMS condition, thermal time ambiguity, and semiclassical backreaction

**Phase VI: Entanglement Wedges & Information Localization (Toys 051-060)**  
Entanglement structure, boundary conditions, gauge fixing, and formulation choices

**Phase VII: Truncation, Unitarity, & Lattice Effects (Toys 061-070)**  
Hilbert space truncation, lattice artifacts, Ward identities, and IR superselection

**Phase VIII: Chaos, Modular Structure, & Advanced Diagnostics (Toys 071-080)**  
OTOC chaos diagnostics, modular Hamiltonians, spectral positivity, and analytic continuation

**Phase IX: Failure-Mode Meta-Structure (Toys 081-085)**  
Cross-toy classification, GR-QFT comparison, and failure pattern analysis

**Phase X: Vacuum Energy & Cosmological Implications (Toys 086-090)**  
Casimir effects, metastable vacua, de Sitter construction, and EFT positivity bounds

**Phase XI: Advanced Structure & Boundary Diagnostics (Toys 091-100)**  
Spectral reconstruction, RG scheme dependence, global reconstruction ambiguity, and thermalization

### Structural Features
- **Toy implementations**: All 100 toys with Python source files
- **File organization**: Python scripts, JSON outputs, and execution logs organized in `toys/` folder
  - `py.zip` — All Python source files
  - `json.zip` — All JSON output files  
  - `logs.zip` — All execution logs
- **Phase structure**: Thematic organization across 11 phases
- **Version**: v1.0.0

---

## Why this is useful

### For Understanding QFT
- Clarifies common QFT "paradoxes" as regulator or gauge artifacts
- Makes UV/IR sensitivity explicit rather than philosophical
- Separates scheme-dependent intermediate quantities from physical observables
- Exposes where free-field, fixed-background, and perturbative approximations fail
- Provides a baseline against which extensions of QFT can be compared

### For Theoretical Research
- Pattern analysis constrains what kind of theory QFT is (fundamental vs. emergent)
- Provides testable signatures for beyond-QFT hypotheses
- Guides where to look for new physics:
  - Pre-field quantum information theory
  - Quantum reference frames / relational quantum mechanics
  - Emergent gauge structure frameworks
  - Resolution of vacuum energy problem
  - Understanding of asymptotic state assumptions
  - Non-perturbative formulation limits

This lab is most useful for readers who already know QFT and want to understand **its limits, not just its successes**.

---

## How to use this repository

### As a Diagnostic Tool
- **Reference index** of QFT failure modes
- **Sanity check** when claiming "QFT predicts X"
- **Diagnostic harness** for numerical or theoretical work
- **Baseline** for comparing QFT to non-perturbative or modified theories

### As a Research Framework
- Test whether your theory resolves documented failure modes
- Compare your theory's boundary structure to QFT's failure manifold
- Assess whether your theory handles observer-dependent quantities
- Check if your theory addresses vacuum ambiguity
- Verify compatibility with gauge structure requirements
- Evaluate whether your theory treats renormalization as physical vs conventional
- Confirm your theory has smooth EFT breakdown, not sharp cutoff
- Verify systematic failure structure matches effective theory
- Identify experimental signatures to test emergence hypothesis

---

## Repository Contents

```text
QFT-Boundary-Lab/
├── docs/                        # 📚 Complete toy documentation
│   ├── guides/                  # User guides
│   │   ├── common_pitfalls.md
│   │   ├── getting_started.md
│   │   └── json_interpretation.md
│   ├── indices/                 # Navigation indices
│   │   ├── by_failure_mode.md
│   │   ├── by_topic.md
│   │   ├── by_toy_number.md
│   │   └── quick_reference.md
│   ├── toys/                    # 11 phase files with full descriptions
│   │   ├── phase_01_free_field_theory_and_regulation.md
│   │   ├── phase_02_vacuum_structure_and_state_ambiguity.md
│   │   ├── phase_03_locality_gauge_structure_and_factorization.md
│   │   ├── phase_04_operational_limits_and_measurement_theory.md
│   │   ├── phase_05_backreaction_subsystem_dynamics_and_thermality.md
│   │   ├── phase_06_entanglement_wedges_and_information_localization.md
│   │   ├── phase_07_truncation_unitarity_and_lattice_effects.md
│   │   ├── phase_08_chaos_modular_structure_and_diagnostics.md
│   │   ├── phase_09_failure_mode_meta_structure.md
│   │   ├── phase_10_vacuum_energy_and_cosmology.md
│   │   └── phase_11_advanced_structure_and_boundary_diagnostics.md
│   └── README.md                # Documentation landing page
├── toys/                        # Toy implementations and outputs
│   ├── COMMANDS.md              # Execution commands / usage
│   ├── MAKE.md                  # Documentation generation specification
│   ├── README.md                # Toys folder overview
│   ├── TOY_PROTOCOL.md          # Toy-specific execution protocol
│   ├── json.zip                 # All 100 JSON output files
│   ├── logs.zip                 # All execution logs
│   └── py.zip                   # All 100 Python source files
├── LICENSE                      # MIT License
├── PROCESS.md                   # Construction and execution methodology
└── README.md                    # This file
```

---

## End state

By Toy 100:

- Every major failure trigger is sampled (UV/IR divergence, gauge artifact, vacuum inequivalence, regulator/scheme dependence, observer dependence, boundary effects, measurement ambiguity, formulation choice)
- Every major failure mode is demonstrated (regulator dependence, scheme dependence, vacuum ambiguity, gauge non-uniqueness, state dependence, observer dependence, operational undefinedness, constraint violation, factorization failure)
- Failures range from sharp to contextual to thick
- QFT is mapped as an effective theory with a well-defined boundary manifold
- Vacuum state, particle number, and locality shown to be emergent or observer-dependent
- Even renormalization, gauge fixing, and asymptotic states shown to be conventional choices
- Measurement resolution and finite-time effects demonstrated as fundamental limitations

**This project does not argue against Quantum Field Theory.**  
**It shows exactly where and how it stops being a theory.**

The structure of that boundary manifold suggests what kind of theory it is:  
**An emergent effective description rather than a fundamental or nearly-fundamental one.**

---

## Version History

- **v1.0.0** — Initial release: 100 toys across 11 phases; complete documentation system; phase files, indices, and guides

---

## Citation

```bibtex
@software{qft_boundary_lab,
  title   = {QFT Boundary Lab: A Diagnostic Test Suite for Quantum Field Theory},
  author  = {DeRenzis, Sam},
  year    = {2026},
  version = {1.0.0},
  url     = {https://github.com/waitandhope123/qft-failure-manifold},
  note    = {Systematic mapping and analysis of quantum field theory failure modes through 100 computational experiments across 11 phases}
}
```

## License

MIT
