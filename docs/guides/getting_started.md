# Getting Started with the QFT Failure Manifold

This guide helps you navigate and understand the QFT Failure Manifold documentation.

---

## What is this lab?

The QFT Failure Manifold is a systematic collection of 100 computational "toys" that expose where and how quantum field theory stops being well-defined. Each toy is designed to:

- **Isolate a specific assumption** or limit of QFT
- **Make failure observable** through concrete numerical outputs
- **Classify the type of breakdown** (regulator-dependence, scheme-dependence, etc.)
- **Map boundaries** where QFT transitions from fundamental to effective

This is not a claim that QFT is wrong, but a diagnostic exploration of its limits.

---

## How the lab is organized

### By Phase (Recommended for learning)

The 100 toys are organized into **11 thematic phases**:

1. **Free Field Theory & UV/IR Regulation** (001-010) — Start here
2. **Vacuum Structure & State Ambiguity** (011-020)
3. **Locality, Gauge Structure, & Factorization** (021-030)
4. **Operational Limits & Measurement Theory** (031-040)
5. **Backreaction, Subsystem Dynamics, & Thermality** (041-050)
6. **Entanglement Wedges & Information Localization** (051-060)
7. **Truncation, Unitarity, & Lattice Effects** (061-070)
8. **Chaos, Modular Structure, & Advanced Diagnostics** (071-080)
9. **Failure-Mode Meta-Structure** (081-085)
10. **Vacuum Energy & Cosmological Implications** (086-090)
11. **Advanced Structure & Boundary Diagnostics** (091-100)

Each phase builds on previous phases conceptually.

### By Index (For targeted research)

- **[By Toy Number](../indices/by_toy_number.md)** — Sequential list 001-100
- **[By Topic](../indices/by_topic.md)** — Find toys about specific QFT topics
- **[By Failure Mode](../indices/by_failure_mode.md)** — Find toys by what breaks
- **[Quick Reference](../indices/quick_reference.md)** — Compact table of all toys

---

## Understanding a toy

Each toy description follows the same structure:

### 1. Physical Setup
What is being modeled, what field theory, what regulators are used.

### 2. Stress Test Purpose  
What conceptual trap or limitation is being exposed. This is the "why" of the toy.

### 3. JSON Interpretation Guide
How to read the output fields. What trends to look for, what diagnostics matter.

### 4. Mathematical Context
Key equations, scaling laws, and theoretical background.

### 5. Over-Interpretation Warnings
What NOT to conclude from the results. Common pitfalls to avoid.

---

## Reading the JSON outputs

All toys export machine-readable JSON files with a consistent schema:

```json
{
  "toy_id": "toy_XXX_name",
  "theory": "field theory type",
  "field_content": "scalar/fermion/gauge",
  "regulators": {
    "UV_cutoff": "...",
    "IR_volume": "...",
    "lattice_spacing": "..."
  },
  "sample_points": [...]
}
```

**Key principle**: Many quantities in the JSON are regulator-dependent or scheme-dependent. The toy descriptions explain which quantities are physical and which are diagnostic.

See [JSON Interpretation Guide](json_interpretation.md) for complete schema details.

---

## Common patterns across toys

### Regulator Dependence
Many toys show quantities that change with UV cutoff, IR volume, or lattice spacing. This is not a bug—it's the point.

### Scheme Dependence  
Renormalization schemes affect intermediate quantities. Only certain combinations are physical.

### Vacuum Ambiguity
Different mode decompositions or time slicings lead to inequivalent vacua.

### Gauge Artifacts
Gauge-fixing choices affect observables in ways that must be understood carefully.

### Observer Dependence
"Particles" and thermality depend on the observer's trajectory.

---

## Recommended learning paths

### For QFT students
Start with **Phase I** (toys 001-010) and work sequentially. These establish foundational concepts about regulators, vacuum structure, and free fields.

### For researchers
Use the [By Topic](../indices/by_topic.md) index to find toys relevant to your specific question. Common topics:
- Renormalization → Phases I, III, V
- Gauge theory → Phases III, IV, VI
- Entanglement → Phases VI, VII
- Vacuum structure → Phases I, II
- EFT limits → Phase X

### For theorists exploring QFT limits
Read [Common Pitfalls](common_pitfalls.md) first to avoid misinterpretations, then explore [By Failure Mode](../indices/by_failure_mode.md).

---

## What this lab is NOT

- ❌ Not a claim that QFT is empirically false
- ❌ Not a replacement theory
- ❌ Not a lattice QCD production code
- ❌ Not a numerical simulation framework
- ❌ Not proposing new physics

Instead, it's a **diagnostic map** of where QFT's formalism becomes ambiguous, regulator-dependent, or operationally ill-defined.

---

## Getting help

### Understanding a specific toy
1. Read the toy's description in the appropriate phase file
2. Check [JSON Interpretation Guide](json_interpretation.md) for field meanings
3. Review [Common Pitfalls](common_pitfalls.md) for that toy's category

### Finding related toys
Use the [By Topic](../indices/by_topic.md) or [By Failure Mode](../indices/by_failure_mode.md) indices.

### Understanding the bigger picture
Read the main [README](../../README.md) for project philosophy and the "End state" section.

---

## Key concepts to understand

### Regulator vs Physical Observable
- **Regulator-dependent**: Depends on cutoff, lattice spacing, or volume (diagnostic)
- **Physical observable**: Regulator-independent combination (what experiments measure)

The toys often export regulator-dependent quantities to demonstrate sensitivity.

### Scheme vs Physics
- **Scheme-dependent**: Depends on renormalization prescription (intermediate)
- **Scheme-independent**: Physical observable (actual prediction)

Many toys show scheme dependence to illustrate that "coupling constants" aren't observables.

### Vacuum Ambiguity
Different choices of modes or time slicing lead to genuinely different vacua. There is no unique "ground state" without additional structure.

### Gauge Artifact
Effects that disappear or change under gauge transformations. Must be distinguished from physical effects.

---

## Next steps

1. **Start learning**: Begin with [Phase 1](../toys/phase_01_free_field_theory_and_regulation.md)
2. **Explore topics**: Browse [By Topic](../indices/by_topic.md)
3. **Understand outputs**: Read [JSON Interpretation](json_interpretation.md)
4. **Avoid pitfalls**: Study [Common Pitfalls](common_pitfalls.md)
5. **Navigate freely**: Use [Quick Reference](../indices/quick_reference.md)

---

Welcome to the QFT Failure Manifold. Let's explore where quantum field theory stops being a theory.
