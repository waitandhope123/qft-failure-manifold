# Common Pitfalls in QFT Failure Manifold Interpretation

This guide catalogs common misinterpretations of QFT toy outputs and provides corrections.

---

## Overview

The toys are designed to expose conceptual subtleties in QFT. This makes them easy to misinterpret. This guide helps you avoid the most common mistakes.

---

## Category 1: UV/IR Regulators

### Pitfall 1.1: Treating regulator-dependent values as physical

❌ **WRONG**: "The vacuum energy is 150."  
✅ **RIGHT**: "At cutoff Λ=10, the regulated vacuum energy is 150. This grows as Λ² and is not a physical observable without renormalization."

### Pitfall 1.2: Comparing bare quantities across different cutoffs

❌ **WRONG**: "Increasing the cutoff decreased the correlator, so the physics changed."  
✅ **RIGHT**: "The bare correlator is cutoff-dependent. Physical observables require renormalization, which absorbs cutoff dependence."

### Pitfall 1.3: Expecting finite results without regulators

❌ **WRONG**: "The coincident correlator should give a finite number."  
✅ **RIGHT**: "Coincident correlators diverge in the continuum. The `null` value correctly indicates this is undefined without a regulator."

---

## Category 2: Renormalization Schemes

### Pitfall 2.1: Treating coupling constants as observables

❌ **WRONG**: "The coupling is λ=0.5, therefore the theory is weakly coupled."  
✅ **RIGHT**: "In scheme A at scale μ, the coupling is λ=0.5. In scheme B it's λ=0.7. Only scattering amplitudes are observable."

### Pitfall 2.2: Comparing schemes directly

❌ **WRONG**: "Scheme B gives a larger coupling, so it's more accurate."  
✅ **RIGHT**: "Schemes differ by finite terms. Both give the same physical predictions when used consistently."

### Pitfall 2.3: Ignoring scheme labels

❌ **WRONG**: "The beta function is dλ/dlnμ = 0.1."  
✅ **RIGHT**: "In the MS-bar scheme, dλ/dlnμ = 0.1. In momentum subtraction it would differ by scheme-dependent terms."

---

## Category 3: Vacuum Structure

### Pitfall 3.1: Assuming unique vacuum

❌ **WRONG**: "There's only one vacuum state for a free field."  
✅ **RIGHT**: "Different mode decompositions (related by Bogoliubov transformations) give inequivalent vacua with different particle content."

### Pitfall 3.2: Treating particle number as absolute

❌ **WRONG**: "The vacuum has 5 particles."  
✅ **RIGHT**: "Relative to basis B, vacuum A has ⟨N_B⟩=5 particles. This is basis-dependent, not an intrinsic property."

### Pitfall 3.3: Expecting vacuum persistence

❌ **WRONG**: "The vacuum can't decay—there's nothing in it."  
✅ **RIGHT**: "In external fields (Schwinger effect) or accelerated frames (Unruh effect), the vacuum becomes unstable and produces pairs."

---

## Category 4: Gauge Theory

### Pitfall 4.1: Treating gauge-fixed observables as physical

❌ **WRONG**: "The photon propagator is ⟨A_μ A_ν⟩."  
✅ **RIGHT**: "The gauge-fixed propagator depends on gauge choice. Only gauge-invariant Wilson loops are physical observables."

### Pitfall 4.2: Expecting strict locality with gauge fields

❌ **WRONG**: "The charged operator creates a particle right here."  
✅ **RIGHT**: "Gauge invariance requires dressing with a Wilson line, making the operator nonlocal. Strictly local charged operators don't exist."

### Pitfall 4.3: Ignoring Gauss constraint

❌ **WRONG**: "I can specify the field in this region independently."  
✅ **RIGHT**: "Gauss's law ties interior charge to boundary flux. Subregions aren't independent in gauge theories."

---

## Category 5: Observer Dependence

### Pitfall 5.1: Expecting observer-independent particles

❌ **WRONG**: "The vacuum has zero particles for everyone."  
✅ **RIGHT**: "Inertial observers see vacuum. Accelerated observers see thermal radiation (Unruh effect). Particles are observer-dependent."

### Pitfall 5.2: Treating Unruh temperature as external

❌ **WRONG**: "The accelerated detector measures an ambient temperature."  
✅ **RIGHT**: "The Unruh temperature T=a/(2π) characterizes the detector's response to the Minkowski vacuum, not an external bath."

### Pitfall 5.3: Expecting finite-time thermality

❌ **WRONG**: "The detector should see thermal radiation immediately."  
✅ **RIGHT**: "Thermality is an asymptotic property. At finite times, detailed balance is only approximate."

---

## Category 6: Entanglement

### Pitfall 6.1: Expecting finite entanglement entropy

❌ **WRONG**: "The entanglement entropy should be a fixed number."  
✅ **RIGHT**: "Entanglement entropy diverges with UV cutoff: S ~ log(L/a) in 1+1D. It's not a cutoff-independent observable."

### Pitfall 6.2: Treating entanglement as localized

❌ **WRONG**: "Entanglement is stored in the boundary between regions."  
✅ **RIGHT**: "Field entanglement is UV-dominated and nonlocal. The 'area law' reflects short-distance correlations across the boundary."

### Pitfall 6.3: Confusing entanglement with correlation

❌ **WRONG**: "High entanglement means strong classical correlation."  
✅ **RIGHT**: "Entanglement can exist without classical correlations. They're distinct quantum information measures."

---

## Category 7: Measurement and Operations

### Pitfall 7.1: Expecting sharp measurements

❌ **WRONG**: "Measure the field at point x."  
✅ **RIGHT**: "Field measurements require finite smearing width σ. As σ→0, measurement disturbance diverges."

### Pitfall 7.2: Ignoring measurement backaction

❌ **WRONG**: "Measure A, then measure B—they're spacelike separated so they don't affect each other."  
✅ **RIGHT**: "Finite-resolution measurements disturb even spacelike-separated probes. Smearing introduces backreaction."

### Pitfall 7.3: Assuming instantaneous measurements

❌ **WRONG**: "Measure energy density at time t."  
✅ **RIGHT**: "Energy measurements require finite time averaging. Quantum energy inequalities bound how negative averaged energy can be."

---

## Category 8: Limit Operations

### Pitfall 8.1: Expecting commuting limits

❌ **WRONG**: "First take L→∞, then a→0 gives the same result as a→0 then L→∞."  
✅ **RIGHT**: "Continuum and thermodynamic limits often don't commute. Order matters for singular quantities."

### Pitfall 8.2: Trusting truncated series

❌ **WRONG**: "Include more terms to get better accuracy."  
✅ **RIGHT**: "Asymptotic series diverge eventually. Optimal truncation balances error from missing terms vs divergent tail."

### Pitfall 8.3: Extending beyond domain of validity

❌ **WRONG**: "This formula works at weak coupling, so I'll use it at strong coupling."  
✅ **RIGHT**: "Perturbative results break down beyond their convergence radius. Different methods needed for strong coupling."

---

## Category 9: Global vs Local

### Pitfall 9.1: Expecting local data to fix global state

❌ **WRONG**: "I know all local observables in this region, so I know the global state."  
✅ **RIGHT**: "Infinite states can share identical local data (Reeh-Schlieder). Local correlators don't fix the global state."

### Pitfall 9.2: Treating extensive quantities as local

❌ **WRONG**: "Total energy is a local observable."  
✅ **RIGHT**: "Energy is a global charge requiring boundary conditions. Local energy density needs smearing and subtraction."

### Pitfall 9.3: Ignoring boundary effects

❌ **WRONG**: "Finite-volume and infinite-volume give the same physics."  
✅ **RIGHT**: "Boundary conditions affect vacuum state, correlators, and mode structure. Volume is an IR regulator."

---

## Category 10: Semiclassical and EFT

### Pitfall 10.1: Trusting EFT beyond its regime

❌ **WRONG**: "The EFT prediction is 15, so that's what happens."  
✅ **RIGHT**: "At energy scale E, the EFT predicts 15 with corrections ~ (E/Λ)². Above Λ, new physics enters."

### Pitfall 10.2: Treating classical backgrounds as exact

❌ **WRONG**: "The external field is exactly as specified."  
✅ **RIGHT**: "Classical backgrounds are approximations. Backreaction and quantum fluctuations modify them."

### Pitfall 10.3: Expecting sharp EFT breakdown

❌ **WRONG**: "Below the cutoff, EFT works. Above it, it fails."  
✅ **RIGHT**: "EFT breakdown is gradual. Corrections grow with E/Λ, not a sharp transition."

---

## Golden Rules

### Rule 1: Distinguish diagnostics from observables
Not everything in the JSON is measurable. Regulator-dependent quantities are diagnostic tools.

### Rule 2: Always state your regulator
"Divergent" is incomplete. Say "grows as Λ² as cutoff Λ increases."

### Rule 3: Always state your scheme
"λ=0.5" is incomplete. Say "λ_MS-bar(μ=M_Z)=0.5."

### Rule 4: Respect null values
`null` means "undefined in this setup," not "zero" or "error." It marks conceptual boundaries.

### Rule 5: Read the toy description
Context is crucial. The toy description explains what each field means and what to conclude.

### Rule 6: Don't over-generalize
Each toy isolates one failure mode. Don't conclude "all of QFT fails" from one toy.

### Rule 7: Check your assumptions
If a result surprises you, verify you're not importing assumptions from classical physics or finite quantum systems.

---

## Self-Check Questions

Before interpreting a result, ask:

1. **Is this regulator-dependent?** If yes, how does it scale with the regulator?
2. **Is this scheme-dependent?** If yes, which scheme am I using?
3. **Is this gauge-dependent?** If yes, is it actually physical?
4. **Is this observer-dependent?** If yes, which observer's perspective?
5. **Is this basis-dependent?** If yes, which mode decomposition?
6. **What's the domain of validity?** Am I extrapolating beyond it?
7. **What limit is being taken?** Do different orders of limits commute?

---

## When to be suspicious

Be skeptical if someone claims:

🚩 "The coupling constant is exactly X" (without scheme/scale)
🚩 "The vacuum has exactly zero energy" (without subtraction)
🚩 "Particle number is observer-independent"
🚩 "This quantity is finite" (without showing regulator independence)
🚩 "Local data determines the global state"
🚩 "Gauge-fixed quantities are physical observables"
🚩 "Measurements don't disturb spacelike-separated regions"

---

## Learning from mistakes

The toys deliberately set traps for these pitfalls. If you catch yourself making one:

1. Re-read the toy description
2. Check the [JSON Interpretation Guide](json_interpretation.md)
3. Look for the relevant failure flags in the JSON
4. Understand why this is a limitation, not a bug

---

Remember: These toys expose conceptual subtleties, not errors in QFT. The goal is to understand QFT's boundaries, not to reject it.
