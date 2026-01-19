# JSON Interpretation Guide

## Overview

All QFT Failure Manifold toys export JSON files with a consistent schema. This guide explains how to interpret the fields and what they mean.

---

## Top-Level Structure

```json
{
  "toy_id": "toy_XXX_name",
  "theory": "QFT type (free scalar, φ⁴, gauge theory, etc.)",
  "field_content": "scalar/fermion/gauge/mixed",
  "spacetime_dimension": "1+1, 3+1, etc.",
  "units": { "hbar": 1, "c": 1 },
  "regulators": {
    "UV_cutoff_Lambda": "high-momentum cutoff",
    "IR_volume_L": "finite box size",
    "lattice_spacing_a": "lattice discretization",
    "...": "other regulators"
  },
  "parameters": {
    "mass_m": "field mass",
    "coupling_lambda": "interaction strength",
    "...": "model parameters"
  },
  "notes": {
    "..."  : "explanatory text"
  },
  "sample_points": [...],
  "observables": {...}
}
```

---

## Key Principles

### 1. Regulator Dependence
Many quantities depend on regulators (Λ, L, a). This is INTENTIONAL—the toys demonstrate UV/IR sensitivity.

**Example**: Vacuum energy density grows with UV cutoff.

### 2. Scheme Dependence
Renormalized quantities depend on subtraction scheme. The JSON labels which scheme is used.

**Example**: Running coupling λ(μ) differs between MS-bar and momentum subtraction.

### 3. Null Values
`null` means "undefined in this context" not "zero" or "error."

**Example**: Point like field variance is `null` because it diverges without smearing.

---

## Sample Points Structure

Each entry in `sample_points` represents one configuration or spacetime point:

```json
{
  "coordinates": {
    "t": "time",
    "x": "space",
    "k": "momentum",
    "mu": "renormalization scale",
    "...": "depends on toy"
  },
  "local_observables": {
    "field_correlator_G": "vacuum two-point function",
    "energy_density": "local energy",
    "particle_number": "mode occupation",
    "...": "toy-specific"
  },
  "regulator_diagnostics": {
    "cutoff_dependence": "how result changes with Λ",
    "volume_dependence": "how result changes with L",
    "...": "sensitivity measures"
  },
  "failure_flags": {
    "divergent": true/false,
    "regulator_dependent": true/false,
    "scheme_dependent": true/false,
    "gauge_artifact": true/false,
    "...": "breakdown indicators"
  }
}
```

---

## Common Field Types

### Correlators
- **Wightman function** G(x,y): Vacuum expectation ⟨φ(x)φ(y)⟩
- **Commutator** Δ(x,y): [φ(x), φ(y)]
- Usually regulator-dependent at short distances

### Energy Quantities
- **Vacuum energy density**: Zero-point energy per volume (UV-divergent)
- **Stress tensor** T_μν: Local energy-momentum (needs regularization)
- **Energy cost**: Operational energy required for state preparation

### Particle Numbers
- **Mode occupation** n_k: Particles in mode k (basis-dependent)
- **Detector response**: Observer-dependent excitation rate
- Not gauge-invariant or observer-independent in general

### Entanglement
- **Entanglement entropy** S: Von Neumann entropy of reduced state (UV-divergent)
- **Mutual information** I: Correlation between regions
- Requires UV cutoff to be finite

### Renormalization
- **Running coupling** λ(μ): Scale-dependent parameter
- **Beta function** β(λ): RG flow derivative
- **Anomalous dimension** γ: Scaling behavior
- All scheme-dependent

---

## Interpreting Trends

### What to look for:

**UV Sensitivity**
- Quantities growing with Λ → UV divergence
- Example: Vacuum energy ~ Λ^(d+1)

**IR Sensitivity**
- Quantities changing with L or m → IR structure matters
- Example: Finite-volume correlators depend on box size

**Scheme Dependence**
- Different schemes give different numbers → intermediate quantity
- Example: λ_MS-bar ≠ λ_momentum at same scale

**Vacuum Inequivalence**
- Different mode choices → different particle content
- Example: Bogoliubov-related vacua have nonzero particle numbers

### What NOT to conclude:

❌ Don't interpret regulator-dependent values as physical predictions
❌ Don't compare scheme-dependent quantities across schemes directly
❌ Don't treat gauge-dependent observables as physical
❌ Don't ignore `null` values—they signal important breakdowns

---

## Specific Toy Categories

### Free Field Toys (001-010)
**Focus**: Regulators, correlators, vacuum structure
**Key fields**: `wightman_function_G`, `commutator_Delta`, `cutoff_Lambda`
**Watch for**: UV/IR divergences, coincident-point singularities

### Vacuum Structure (011-020)
**Focus**: Inequivalent representations, observer dependence
**Key fields**: `vacuum_overlap`, `particle_number`, `unruh_temperature`
**Watch for**: Bogoliubov coefficients, Haag's theorem signals

### Gauge Theory (021-030)
**Focus**: Gauge artifacts, IR divergences, factorization
**Key fields**: `dressed_operator_extent`, `boundary_flux`, `gauge_fixing`
**Watch for**: Non-local gauge structure, Gauss constraint

### Renormalization (Throughout)
**Focus**: Scheme dependence, running couplings, EFT limits
**Key fields**: `coupling_scheme_A`, `coupling_scheme_B`, `beta_function`
**Watch for**: Scheme differences, Landau poles, fixed points

---

## Red Flags

These indicate important conceptual issues:

🚩 **Large cutoff dependence**: Theory needs renormalization
🚩 **Scheme-dependent physical claim**: Misidentified observable
🚩 **Divergent entanglement entropy**: UV sensitivity
🚩 **Nonzero spacelike commutator**: Microcausality violation
🚩 **Gauge-dependent "observable"**: Not actually gauge-invariant
🚩 **Vacuum overlap → 0**: Haag's theorem / inequivalent representations

---

## Best Practices

1. **Always check regulators first**: Know what Λ, L, a are
2. **Distinguish diagnostics from observables**: Not everything is measurable
3. **Compare trends, not absolute values**: Scaling matters most
4. **Respect null values**: They mark conceptual boundaries
5. **Read toy description**: Context explains what each field means

---

## Example Walkthrough

**Toy 001: Free Scalar Correlator**

```json
{
  "cutoff_Lambda": 10.0,
  "wightman_function_G": 0.15,
  "coincident_limit_defined": false
}
```

**Interpretation**:
- G = 0.15 is the regulated correlator at Λ = 10
- `coincident_limit_defined: false` means G(0,0) diverges
- This 0.15 is NOT a physical observable—it depends on Λ
- To see UV sensitivity, compare across different Λ values

---

## Further Reading

- See [Common Pitfalls](common_pitfalls.md) for interpretation mistakes
- See [Getting Started](getting_started.md) for context
- See toy descriptions in `/docs/toys/` for field-by-field explanations

---

Remember: The JSON encodes both physical and diagnostic information. Learn to distinguish them.
