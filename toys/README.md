# Toys Directory

This directory contains the executed diagnostic artifacts for the **QFT Failure Manifold**.

## Contents

### Documentation

- **COMMANDS.md**  
  Exact commands used to execute each toy and generate its JSON output.

- **MAKE.md**  
  Specification for documentation format and generation workflow.

- **TOY_PROTOCOL.md**  
  Formal protocol defining how each toy is constructed, what constraints it must satisfy, and how results are exported.

### Implementation & Results (Archives)

- **json.zip**  
  Archive containing all 100 JSON output files (toy_001_*.json through toy_100_*.json).
  Each JSON encodes parameters, observables, and detected failure signals for a single toy.

- **logs.zip**  
  Archive containing execution logs for all toys.

- **py.zip**  
  Archive containing all 100 Python source files (toy_001_*.py through toy_100_*.py).
  Each implements one computational experiment.

## What's Included in v1.0.0

**Current release:**
- Separate archives: `py.zip` (source), `json.zip` (outputs), `logs.zip` (execution logs)
- **100 toys total** across 11 thematic phases
- Complete descriptions in `/docs/` folder
- Comprehensive documentation with guides and indices

## Toy Numbering

- Toys are numbered **001-100** (100 total)
- Toy 050 (cross-toy comparator) is a meta-analysis toy
- Toy 081 (cross-toy failure-mode classifier) is a meta-analysis toy
- Toy 099 (QFT boundary dashboard) is a system-level diagnostic
- Toy 100 (dark matter origin) is an exploratory/speculative toy
- All other toys have complete implementations and JSON outputs

## Why ZIP Archives?

The archives keep the repository lightweight while preserving machine-readable execution data. This project is diagnostic and archival, not a live simulation framework.

## Finding Toy Documentation

**Complete toy descriptions** are in the `/docs/` folder:
- Navigate by phase: `/docs/toys/phase_01_free_field_theory_and_regulation.md` (etc.)
- Sequential index: `/docs/indices/by_toy_number.md`
- Quick reference: `/docs/indices/quick_reference.md`
- Getting started: `/docs/guides/getting_started.md`

See `/docs/README.md` for full navigation.

---

**For execution commands and usage, see `COMMANDS.md` in this directory.**
