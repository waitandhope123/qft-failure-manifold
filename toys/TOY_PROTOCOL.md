# QFT Toy Model Protocol

## Objective

Build one Quantum Field Theory toy model per request that:

- produces numerical results derived from physics (not placeholders),
- is implemented in Python,
- exports results to a JSON file,
- uses a shared export schema so toys are directly comparable,
- is designed to probe limits, assumptions, and weak points of QFT.

The goal is cataloging QFT's boundaries, not defending or embellishing it.

## General Rules

### 1. One toy per response
- Each response produces exactly one Python toy model.

### 2. Physics must be real
- Use known QFT or controlled approximations (free field, perturbative, lattice, etc.).
- Every numerical output must follow from equations.
- If a quantity is regulator-dependent or scheme-dependent, flag it explicitly.
- If a quantity is undefined without additional structure, return null explicitly.

### 3. No symbolic-only toys
- All toys must output numerical values at sample points.

### 4. Units and Regulators
- Default to natural units: ℏ = c = 1, unless explicitly stated otherwise.
- All UV and IR regulators must be explicit (cutoff, lattice spacing, volume, etc.).
- Scheme-dependent quantities must be labeled with the scheme.

## Required Toy Structure (Python)

Each toy must include:

### A. Explicit assumptions
- field content and symmetries
- spacetime dimension and topology
- interaction terms (or lack thereof)
- UV regulator (cutoff, lattice spacing, etc.)
- IR regulator (volume, mass gap, etc.)
- renormalization scheme (if applicable)
- vacuum choice or Fock space construction
- domain of validity

### B. Core physics implementation
- equations defining the model
- mode decompositions or field configurations
- regulators and their values
- physically interpretable quantities

### C. Diagnostic observables
Examples:
- vacuum correlators
- particle number expectations
- entanglement entropies
- renormalized masses or couplings
- spectral densities
- regulator-dependence diagnostics
- scheme-dependence diagnostics

## Mandatory JSON Export Schema

Every toy must export exactly these top-level keys:

{
  "toy_id": "string",
  "theory": "string",
  "field_content": "string",
  "spacetime_dimension": "string",
  "units": { "hbar": 1, "c": 1 },
  "regulators": {},
  "parameters": {},
  "notes": {},
  "sample_points": [],
  "observables": {}
}

Each entry in sample_points must follow this structure:

{
  "coordinates": {},
  "local_observables": {},
  "regulator_diagnostics": {},
  "failure_flags": {}
}

- If a quantity is undefined, use null.
- If a quantity is regulator-dependent, flag it.
- If a quantity is scheme-dependent, label the scheme.
- Do NOT omit keys.

## Export Rules (Strict)

- JSON only
- One file per toy
- Output filename MUST match the Python filename

Example:
toy_001_free_scalar_1d.py  
toy_001_free_scalar_1d.json

- The Python script must automatically derive the JSON filename from __file__
- Deterministic output (no randomness unless requested)

## Allowed Toy Categories

- Free field theories (scalar, fermion, gauge)
- Perturbative QFT (one-loop, tree-level)
- Lattice field theory
- Renormalization group flows
- Vacuum structure and inequivalent representations
- Observer-dependent quantities (Unruh effect, etc.)
- Gauge structure and redundancy
- Entanglement and information
- EFT breakdown diagnostics

## What Counts as a "Boundary"

A toy is valuable if it exposes:
- UV/IR divergence and regulator dependence
- Renormalization scheme dependence
- Vacuum state ambiguity
- Gauge artifact vs physical effect separation
- Observer-dependent thermality
- Subsystem factorization failure
- Measurement-induced ambiguities
- Non-commutativity of limit operations
- Breakdown of perturbation theory
- EFT validity boundaries

## What the Assistant Must Not Do

- invent numerical values
- change the export schema
- output multiple toys at once
- output prose without code
- rely on external data unless explicitly asked
- ignore regulators or pretend they don't matter
- claim scheme-independent results for scheme-dependent quantities

## Expected Output Per Request

1. Short explanation of what the toy probes
2. One complete Python script
3. Script writes a JSON file whose name matches the Python file
4. Explicit statement of all regulators and schemes used

## How to Request the Next Toy

Examples:
- "Toy 002: Unruh-DeWitt detector in flat spacetime"
- "Toy 003: Finite-volume vacuum correlators"
- "Toy 004: One-loop mass correction in φ⁴ theory"
- "Toy 005: Entanglement entropy with lattice cutoff"

## End Goal

After many toys, you should be able to:
- compare regulator and scheme dependences across models,
- see where QFT assumptions matter,
- identify ambiguity or underdetermination,
- separate physical effects from regulator/scheme artifacts,
- map the boundary manifold of QFT as an effective theory.
