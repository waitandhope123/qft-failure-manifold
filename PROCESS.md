# Process and Tooling

This repository was created using an **AI-assisted, human-directed workflow** involving collaboration between the human author and two AI systems (ChatGPT and Claude).

The conceptual vision, research questions, validation methodology, and all execution were human-directed. AI systems were used as specialized tools for code generation, documentation synthesis, and structural organization.

---

## Role of the human author

The human author's role included:

- **Defining the research objective**: Map QFT's boundary manifold through computational stress tests
- **Directing the research process**: Iteratively guiding what types of failures to explore and how to probe them
- **Making all conceptual decisions**: What constitutes a "failure," how to classify it, what questions to ask next
- **Consulting additional AI tools**: Using Perplexity for research ideas, sanity checks on toy directions, and validation that data interpretations are headed in the right direction
- **Executing all toy models**: Running every Python script to generate the JSON outputs (all 100 toys)
- **Quality control**: Ensuring alignment between code, outputs, documentation, and interpretive claims
- **Final approval**: All content, classifications, and conclusions reviewed and approved by the human author

---

## Role of ChatGPT

ChatGPT was used for **toy model generation and initial descriptions**:

### Toy Development (Toys 001-100)
- **Conceptual design**: Human author posed research questions; ChatGPT suggested which toy models would expose specific failure modes in QFT
- **Python implementation**: ChatGPT wrote all 100 Python toy scripts under human direction
- **Output validation**: After human execution, ChatGPT compared JSON outputs against Python source code to verify correctness, expected field structure, and diagnostic accuracy
- **Iterative refinement**: Human author reviewed validation results, identified gaps, directed creation of additional toys

### Toy Descriptions
- ChatGPT created comprehensive toy descriptions following the three-paragraph structure:
  1. Physical setup and what is being modeled
  2. Stress test purpose and conceptual limitation being exposed
  3. JSON interpretation guidance with over-interpretation warnings
- Human author compiled these into TOYS MASTER LIST.txt as working document

ChatGPT did **not** autonomously define research goals, select failure modes to investigate, or make decisions without human direction.

---

## Role of Claude

Claude was used for **documentation architecture and repository structure**:

### Documentation Structure (v1.0.0)
- Human author provided Claude with:
  - TOYS MASTER LIST.txt containing all 100 toy descriptions
  - GR repository as structural template
  - Instructions for phase organization (11 phases for QFT vs 13 for GR)
- Claude organized descriptions into the `/docs/` structure:
  - 11 thematic phase files containing all 100 toy descriptions
  - Navigation indices (by toy number, by topic, by failure mode, quick reference)
  - User guides (getting started, JSON interpretation, common pitfalls)
- Claude created the professional documentation hierarchy

### Repository Documentation
- Main `README.md` in GitHub root
- Documentation READMEs and navigation structure
- Structural organization of repository mirroring GR lab

### Key Adaptation
- Claude adapted GR lab's structure for QFT context
- Changed all references from "GR Failure Manifold" to "QFT Failure Manifold"
- Organized 100 toys into 11 QFT-appropriate phases vs 90 toys in 13 GR phases
- Created QFT-specific guides emphasizing regulator dependence, scheme dependence, and vacuum ambiguity

Claude did **not** generate toy models, execute code, or make empirical claims without human review.

---

## Workflow Summary

**Phase 1: Toy Creation (ChatGPT + Human)**
1. Human defines research question or QFT failure mode to explore
2. ChatGPT proposes toy model approach
3. ChatGPT implements Python script
4. Human executes script → generates JSON output
5. ChatGPT compares JSON output to Python source to validate correctness
6. If validation passes → move to next toy; if issues found → refine and repeat
7. Repeat for all 100 toys

**Phase 2: Toy Description (ChatGPT + Human)**
1. Human provides ChatGPT with Python source and JSON output
2. ChatGPT generates detailed toy description with three-paragraph structure
3. Human compiles all descriptions into TOYS MASTER LIST.txt
4. Repeat for all 100 toys

**Phase 3: Documentation Architecture (Claude + Human)**
1. Human provides Claude with:
   - TOYS MASTER LIST.txt with all 100 toy descriptions
   - GR repository as structural template
   - Phase organization requirements
2. Claude organizes into `/docs/` structure with 11 phase files
3. Claude creates navigation aids (4 indices) and user guides (3 guides)
4. Claude writes main README and supporting documentation
5. Human reviews and approves documentation

---

## Division of Labor

| Task | Human | ChatGPT | Claude |
|------|-------|---------|--------|
| Define research objectives | ✓ | | |
| Decide what toys to create | ✓ | Suggest | |
| Implement Python toys | | ✓ | |
| Execute Python scripts | ✓ | | |
| Generate JSON outputs | ✓ | | |
| Validate JSON vs Python | | ✓ | |
| Write toy descriptions | | ✓ | |
| Compile TOYS MASTER LIST | ✓ | | |
| Design phase structure | ✓ | | |
| Extract & organize docs | | | ✓ |
| Create navigation indices | | | ✓ |
| Write user guides | | | ✓ |
| Write README | | | ✓ |
| Review final documentation | ✓ | | |
| Make final decisions | ✓ | | |

---

## Validation and Responsibility

All content in this repository was validated through a multi-stage process:

**Technical Validation (ChatGPT):**
- JSON outputs compared against Python source code for correctness
- Field structure and diagnostic contents verified
- Expected behavior and numerical outputs checked

**Content Validation (Human):**
- Conceptual correctness: Do toys test what they claim to test?
- Interpretive accuracy: Do descriptions reflect what diagnostics actually show?
- Internal consistency: Do classifications align across all 90 toys?
- Pedagogical clarity: Is documentation accessible and complete?

**Responsibility for the correctness, framing, and interpretation of the work rests entirely with the human author.**

---

## Motivation for Disclosure

This file exists to:

1. **Document the process transparently**: How AI tools were used in this project
2. **Clarify roles**: What was human judgment vs AI assistance
3. **Enable reproducibility**: Others can follow similar workflows
4. **Acknowledge tools**: AI systems as specialized instruments in research

This disclosure is made in the spirit of scientific transparency, not to promote or diminish the use of AI tools. The project stands on its technical and conceptual merits.

---

## Scope Note

This repository does not make empirical claims, propose new physical laws, or replace existing theories. It is a **diagnostic and classificatory exercise** focused on mapping where and how Quantum Field Theory loses predictive or operational meaning, becomes regulator-dependent, scheme-dependent, or operationally ambiguous.

All toys are **stress tests**, not predictions. All outputs are **diagnostics**, not measurements. All interpretations are **conditional**, not definitive.

---

## Version History of Process

- **v1.0.0** (Initial Release): 
  - ChatGPT created all 100 toys with comprehensive three-paragraph descriptions
  - Human compiled into TOYS MASTER LIST.txt
  - Claude organized into professional 11-phase documentation structure
  - Complete navigation system (4 indices, 3 guides) created
  - Human validated all content end-to-end

---

## Tools Used

- **ChatGPT** (OpenAI): Python code generation, toy descriptions
- **Claude** (Anthropic): Documentation architecture, interpretive synthesis
- **Perplexity**: Research consultation, toy idea generation, directional validation
- **Python 3.x**: All toy implementations
- **JSON**: Structured output format
- **Markdown**: Documentation format
- **Git/GitHub**: Version control and distribution
