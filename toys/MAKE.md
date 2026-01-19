# MAKE.md — Toy Documentation Specification

**Instructions for generating comprehensive toy descriptions from source code and JSON outputs.**

This specification was used with ChatGPT to create all 100 toy descriptions in the `/docs/toys/` folder for v1.0.0.

---

## Purpose

Generate pedagogical documentation for QFT toy models that:
- Explains what the toy does and why it exists
- Provides JSON interpretation guidance
- Frames outputs as stress tests, not predictions
- Prevents over-interpretation of results

---

## Input Requirements

The documentation generator requires **both** of the following:

1. **Python source code** for the toy (`toy_XXX_name.py`)
2. **JSON output file(s)** produced by executing that toy (`toy_XXX_name.json`)

**Critical**: Do NOT produce output until both inputs are provided.

---

## Output Structure

Each toy description must follow this exact structure:

```markdown
# Toy XXX — Descriptive Title

[Paragraph 1: Physical Setup]

[Paragraph 2: Stress Test Purpose]

[Paragraph 3: JSON Interpretation Guide]
```

### Three Paragraphs (No More, No Less)

**No section headings, no bullet points** — just three paragraphs of prose.

---

## Content Requirements

### Paragraph 1: Physical Setup

**Purpose**: Explain what the toy models

**Must include:**
- Clear statement of the physical system being modeled
- What spacetime/metric is used
- What quantity of interest is being computed
- Context for why this setup is meaningful

**May include**: 1 equation if it helps orientation (e.g., the metric or key observable)

**Example opening**:
> "This toy computes two standard vacuum correlators for a free real scalar field $\phi(t,x)$ in flat 1+1D Minkowski spacetime, using a hard momentum cutoff $\Lambda$ and a discrete step $dk$ to approximate the mode integrals."

---

### Paragraph 2: Stress Test Purpose

**Purpose**: Explain why the toy exists — what limitation or failure mode it exposes

**Must include:**
- Clear statement of the conceptual issue being illustrated
- What assumption of QFT is being tested or where it breaks down
- Frame as diagnostic/stress test, NOT as physical prediction

**Language to use**:
- "The toy exists to stress-test..."
- "It demonstrates a limitation..."
- "It exposes a failure mode..."
- "It illustrates..."

**Language to AVOID**:
- "This proves..."
- "QFT predicts..."
- "The physical interpretation is..."

**May include**: 1 equation if it clarifies the principle being tested

**Example**:
> "The toy exists to expose a stress point that appears even before any interactions: 'local' field correlators are not well-defined without a UV regulator, and naive numerical evaluations can make causality tests look misleading unless you understand what the regulator is doing."

---

### Paragraph 3: JSON Interpretation Guide

**Purpose**: Explain how to read and interpret the JSON output

**Must include:**
- Field-by-field guidance on what the JSON contains
- What trends, signs, or magnitudes are meaningful
- Explicit warnings about what should NOT be over-interpreted
- Connection between JSON values and the equations/concepts

**Key phrases**:
- "To interpret the JSON, read..."
- "The field `curvature_invariants.kretschmann` should..."
- "Do not over-interpret absolute magnitudes as..."
- "Instead, focus on..."

**Example**:
> "To interpret the JSON, focus on each entry in `sample_points`: `interval_t2_minus_x2` tells you whether the separation is timelike or spacelike, and `wightman_function_G` and `commutator_Delta` are the corresponding regulated values at that separation."

---

## Equation Formatting Rules

**ABSOLUTE REQUIREMENTS** — These are non-negotiable:

### LaTeX Formatting
- **Inline math**: Use `$ ... $`
- **Display math**: Use `$$ ... $$`
- **NEVER use**: `\[ \]`, `\begin{align}`, `\begin{cases}`, or any multiline environments
- **Single-line only**: All equations must be on one line

### Equation Usage
- Maximum 1 equation per paragraph (prefer 0-1 total)
- Equations are **interpretive anchors**, not derivations
- Do NOT number equations
- Do NOT introduce new symbols without naming them in text first

### Examples

✅ **Correct**:
```markdown
The regulated vacuum Wightman function $G(t,x)=\int_{-\Lambda}^{\Lambda}\frac{dk}{4\pi\,\omega_k}\cos(\omega_k t-kx)$ depends explicitly on the cutoff $\Lambda$.
```

❌ **Incorrect**:
```markdown
The vacuum correlator is given by:
\[
G(t,x) = \int_{-\Lambda}^{\Lambda}\frac{dk}{4\pi\,\omega_k}\cos(\omega_k t-kx)
\]
which diverges as:
\begin{align}
G(0,0) &\sim \Lambda
\end{align}
```

---

## Style Guidelines

### Voice and Tone
- Clear, accessible language for intelligent readers unfamiliar with the codebase
- Pedagogical but not condescending
- Precise but not overly technical

### Language Patterns

**Use these verbs**:
- illustrates, demonstrates, exposes, tests, stress-tests
- shows, reveals, isolates, probes
- diagnoses, identifies, maps

**Avoid these verbs**:
- proves, confirms, validates, establishes
- predicts, measures, observes (for toy outputs)
- claims, argues, concludes

### Framing

**Every toy is**:
- A diagnostic stress test
- A limitation probe
- An ambiguity exposer

**No toy is**:
- A physical prediction
- An empirical measurement
- A claim about nature

---

## Quality Criteria

A well-written toy description:

1. **Clarity**: Reader understands what's being modeled without seeing code
2. **Purpose**: Reader understands why this toy exists and what it tests
3. **Interpretability**: Reader can map JSON fields to physical/mathematical concepts
4. **Caution**: Reader understands what NOT to conclude from results
5. **Self-containment**: Description stands alone without requiring code inspection
6. **Brevity**: Exactly three paragraphs, 15-25 lines typical

---

## Anti-Patterns to Avoid

❌ **Don't**:
- Write section headings or bullet points
- Include derivations or proofs
- Explain code implementation details
- Make claims about physical reality
- Use passive voice excessively
- Over-use equations (equations are expensive; use sparingly)
- Number equations
- Leave symbols undefined
- Include commentary outside the three paragraphs

✅ **Do**:
- Focus on concepts and interpretation
- Connect code outputs to physical principles
- Warn about over-interpretation
- Use active voice
- Make every sentence earn its place

---

## Execution Protocol

When using this specification:

1. **Receive Python source code** → Do NOT produce output yet
2. **Receive JSON output file** → Now produce the complete description
3. **Output**: Single markdown block with title + three paragraphs
4. **No preamble**: Do not explain what you're doing
5. **No postamble**: Do not ask for feedback or clarification

---

## Example Template

```markdown
# Toy XXX — [Clear, Descriptive Title]

[Paragraph 1: This toy evaluates/computes/models... The physical setup is... The quantity of interest is... May include 1 key equation.]

[Paragraph 2: The toy exists to stress-test/expose/illustrate... It demonstrates a limitation/failure mode/ambiguity... Frame as diagnostic test. May include 1 equation if it clarifies the principle.]

[Paragraph 3: To interpret the JSON, read... The field `X` should behave as... Do not over-interpret... Focus on trends/signs/scaling rather than absolute values... Connect JSON back to equations/concepts.]
```

---

## Success Metrics

A toy description succeeds when:

- ✅ A graduate student can understand the toy without running it
- ✅ The reader knows what question is being asked
- ✅ The reader knows what failure mode is being exposed
- ✅ The reader can interpret the JSON output fields
- ✅ The reader knows what NOT to conclude
- ✅ The description is exactly three paragraphs
- ✅ Math formatting renders correctly in GitHub markdown

---

## Version History

- **v1.0.0**: Specification used to generate all 100 toy descriptions for QFT Failure Manifold

---

## Usage

This specification was provided to ChatGPT along with:
1. Python source file for toy
2. JSON output from executing that toy

ChatGPT then generated the complete toy description following these rules.

All 100 descriptions in `/docs/toys/phase_*.md` were created using this process.

---

**This specification is the key to the v1.0.0 documentation quality.**
