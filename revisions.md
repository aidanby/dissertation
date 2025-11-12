# Dissertation Revision Tasks

## Current Thesis Statement

**Original:**
> Software engineering is an evolving process, including testing, debugging, and migration. Open-source, code assisting language models are commonly pre-trained on causal code generation (i.e., left-to-right). This limits their value in software maintenance and evolution tasks, which require a wholistic understanding of software properties. Adding an understanding of software properties through program analysis can assist in important steps of the software evolution process and mitigate the limitations of a language model.

**Final (Updated):**
> Program analysis complements large language models (LLMs) for software maintenance by providing structured software signals that include bidirectional code context, formal verification of code properties, and dataflow properties. These signals can be integrated with LLMs beyond autoregressive generation. Explicitly integrating analysis-derived signals with LLMs consistently outperforms either pure learning-based or pure analysis-based approaches across key software engineering tasks in real-world repositories.

## Proposed Revised Thesis Statements

### Option 1: Evidence-Based with Novel Contributions (Recommended)
>
> Large Language Models (LLMs) trained on causal code generation excel at producing natural code but lack the semantic understanding required for software maintenance tasks. This dissertation demonstrates that integrating LLMs with program analysis techniques produces measurably superior results across fault localization, automated program repair, and program transpilation compared to either LLM or program analysis in isolation. Specifically, this work introduces four novel integration techniques: bidirectional adapter fine-tuning that enables test-free fault localization on real-world bugs and security vulnerabilities, entropy-based "naturalness" quantification that improves all three stages of automated program repair, verification-guided transpilation that achieves functional correctness guarantees while maintaining code naturalness, and LLM static analysis concatenated fine-tuning for vulnerablity detection. These contributions establish that hybrid neural-symbolic approaches consistently outperform pure neural or symbolic methods for tasks related to software evolution.

### Option 2: Concise Problem-Solution Focus
>
> While LLMs demonstrate strong code generation capabilities, their application to software evolution tasks is limited by their training on left-to-right generation and lack of semantic understanding. This dissertation addresses this limitation by developing hybrid approaches that augment LLMs with program analysis through bidirectional fine-tuning for fault localization, entropy-guided uncertainty quantification for program repair, and verification-integrated transpilation. Empirical evaluation on real-world defects demonstrates that these integrations systematically outperform both traditional program analysis and standalone LLM approaches, establishing the value of combining neural and symbolic methods for software maintenance.

## Revision Task List

### 1. Thesis Statement (Priority: HIGH)

- [ ] Review the four proposed thesis statement options above
- [ ] Iterate with Daniel and Vincent for approval
- [ ] Update thesis statement in Abstract (line ~210)
- [ ] Update thesis statement in Section 1.1 (line ~290)
- [ ] Ensure consistency between both locations

### 2. Introduction Chapter Revisions (Priority: HIGH)

#### 2.1 Contributions Section (Section 1.2)

- [x] Rewrite contributions to include ALL chapters:
  - Chapter 3: Fault Localization (LLMAO) ✓
  - Chapter 4: Automated Program Repair (Entropy-based) ✓
  - Chapter 5: Program Transpilation (VERT) ✓
  - Chapter 6: Security Vulnerability Detection (Multi-task) ✓
  - Note: Chapter 7 (Node.js) is not included as a separate contribution (it's an extension/application)
- [x] Add novelty claims for each contribution (what was new at time of publication)
- [x] Include paper references for each contribution (\cite{Llmao}, \cite{yang2024revisiting}, \cite{vert}, \cite{yang2024security})
- [x] Add GitHub repository links for each tool:
  - LLMAO: <https://github.com/squaresLab/LLMAO>
  - Entropy-based APR: <https://github.com/squaresLab/entropy-apr-replication>
  - VERT: <https://github.com/YoshikiTakashima/vert>
  - MSIVD: <https://github.com/squaresLab/multitask-vuln-paper>
- [x] Specify quantitative results for each contribution

#### 2.2 Current Contributions to Update

**COMPLETED** - All contributions have been rewritten with comprehensive details:

1. ✓ **Fault Localization (LLMAO)**
   - Added: Dataset sizes (395 Defects4J, 493 BugsInPy, 5,260 Devign)
   - Added: Performance metrics vs. baselines (outperforms DeepFL, GRACE, TransferFL)
   - Added: Novelty claim about test-free approach and bidirectional adapters
   - Added: Paper reference \cite{Llmao}

2. ✓ **Automated Program Repair (Entropy-based)**
   - Added: Specific improvements (24 patches saved, 49% better Top-1 ranking)
   - Added: Three stages improved (FL, patch testing efficiency, ranking)
   - Added: Comparison to both traditional APR and pure LLM approaches
   - Added: Paper reference \cite{yang2024revisiting}

3. ✓ **Program Transpilation (VERT)**
   - Added: Specific technique (verification harnesses + formal verification via Wasm)
   - Added: Results (100% functional correctness with idiomatic code)
   - Added: Comparison to C2Rust
   - Added: Paper reference \cite{vert}

4. ✓ **Multi-task Security Vulnerability Detection (MSIVD)**
   - Added: Novelty claims (self-instruct dialogue, multi-task learning, GNN integration)
   - Added: Results on post-training-cutoff dataset
   - Added: Paper reference \cite{yang2024security}

Note: Chapter 7 (Node.js/NodeMedic) is treated as an extension/application of the vulnerability detection work rather than a separate core contribution, as it builds directly on the techniques from Chapters 3 and 6.

### 3. Background and Related Work Chapter (Priority: MEDIUM)

#### 3.1 Restructure Chapter 2

- [x] Keep only common background:
  - What are LLMs? ✓
  - Transformer architecture basics ✓
  - LLMs for code generation ✓
  - General program analysis concepts ✓
  - Static analysis ✓
  - Dynamic analysis ✓
  - Formal verification ✓
  - Integration of LLMs and program analysis ✓
- [x] Removed chapter-specific background (to be moved to respective chapters):
  - Fault localization background (removed from Ch 2, needs to be added to Chapter 3)
  - Patch correctness background (removed from Ch 2, needs to be added to Chapter 4)
  - Equivalence verification (removed from Ch 2, needs to be added to Chapter 5)
  - Rust transpilers (removed from Ch 2, needs to be added to Chapter 5)
  - Software vulnerability detection (removed from Ch 2, needs to be added to Chapters 6 & 7)
  - Node.js threat model and taint analysis (removed from Ch 2, needs to be added to Chapter 7)

### 4. Beginning of Each Technical Chapter (Priority: HIGH)

For each of Chapters 3-7, add opening section that:

- [x] **Chapter 3 (Fault Localization):**
  - Relate to thesis statement: "addresses the limitation of left-to-right LLMs for discriminative tasks"
  - Explain which part of thesis this supports: "bidirectional understanding of software properties"

- [x] **Chapter 4 (Automated Program Repair):**
  - Relate to thesis statement: "demonstrates that LLM uncertainty can guide traditional APR"
  - Explain which part of thesis this supports: "combining LLM capabilities with program analysis"

- [x] **Chapter 5 (Program Transpilation):**
  - Relate to thesis statement: "shows that LLM generation requires verification for correctness"
  - Explain which part of thesis this supports: "formal verification as program analysis for LLM outputs"

- [x] **Chapter 6 (Security Vulnerability Detection):**
  - Relate to thesis statement: "extends fault localization to multi-file, multi-task scenarios"
  - Explain which part of thesis this supports: "holistic understanding through multi-task learning"

- [x] **Chapter 7 (Node.js Vulnerability Detection):**
  - Relate to thesis statement: "demonstrates hybrid approach with dynamic program analysis"
  - Explain which part of thesis this supports: "taint analysis as program property for LLM guidance"

### 5. Conclusion of Each Technical Chapter (Priority: HIGH)

For each of Chapters 3-7, add/revise conclusion section that:

- [x] **Chapter 3 Conclusion:**
  - Reiterate novelty: First test-free fault localization using bidirectional fine-tuning
  - State contributions: Outperforms SOTA on 3 benchmarks (Defects4J, BugsInPy, Devign)
  - Connect to thesis: Proves bidirectional understanding improves discriminative tasks
  - Evidence provided: Outperforms GRACE, DeepFL, DEAR, TransferFL on 395+493+5,260 bugs

- [x] **Chapter 4 Conclusion:**
  - Reiterate novelty: First use of LLM entropy for all three APR stages
  - State contributions: 18% precision improvement in patch classification
  - Connect to thesis: Demonstrates LLM uncertainty as valuable program analysis signal
  - Evidence provided: 24 test runs saved per bug, 49% Top-1 improvement vs. Shibboleth

- [x] **Chapter 5 Conclusion:**
  - Reiterate novelty: First verified transpilation using LLMs with formal verification
  - State contributions: 100% functional correctness with improved naturalness
  - Connect to thesis: Shows verification is necessary for LLM-based code transformation
  - Evidence provided: 40% more C++, 37% more C, 47% more Go programs verified (1,394 total)

- [x] **Chapter 6 Conclusion:**
  - Reiterate novelty: Multi-task learning for vulnerability detection and explanation
  - State contributions: SOTA on post-training-cutoff vulnerability dataset
  - Connect to thesis: Extends fault localization to multi-file, security-focused scenarios
  - Evidence provided: SOTA on BigVul/PreciseBugs and post-training-cutoff dataset

- [x] **Chapter 7 Conclusion:**
  - Reiterate novelty: Integration of taint provenance with neural approaches
  - State contributions: F1 score of 0.943 on Node.js vulnerabilities
  - Connect to thesis: Demonstrates value of dynamic program analysis with LLMs
  - Evidence provided: F1=0.943 on 2,051 npm packages, outperforms pure analysis/LLM methods

### 6. Title Revision (Priority: LOW - After Thesis Statement)

- [ ] Wait until thesis statement is finalized
- [ ] Propose new title options that reflect:
  - Integration of LLMs with program analysis
  - Software evolution focus
  - Hybrid approach emphasis
- [ ] Possible title ideas:
  - "Hybrid Neural-Symbolic Approaches for Software Evolution"
  - "Integrating Large Language Models with Program Analysis for Software Maintenance"
  - "Beyond Code Generation: Augmenting LLMs with Program Analysis for Software Evolution"

### 7. Build System Updates (Priority: LOW)

- [ ] Update Makefile to use `dissertation.tex` instead of `proposal.tex`
- [ ] Verify build process: `make pdf` should work correctly
- [ ] Update DOC variable in Makefile: `DOC = dissertation.tex`

## Build Instructions

### Current Build Process

```bash
pdflatex dissertation.tex
bibtex dissertation
pdflatex dissertation.tex
pdflatex dissertation.tex
```

### Using Makefile (after updating DOC variable)

```bash
make pdf
```

## Notes on Quantitative Evidence

Based on the dissertation content, here are the key quantitative results to emphasize:

1. **Fault Localization (Chapter 3):**
   - Evaluated on 395 bugs (Defects4J), 493 bugs (BugsInPy), 5,260 vulnerabilities (Devign)
   - Outperforms DeepFL, GRACE, TransferFL on all benchmarks
   - Test-free approach (novel at time of publication)

2. **Automated Program Repair (Chapter 4):**
   - 18% higher precision in patch classification
   - Improvements across all three APR stages
   - Evaluated on Defects4J benchmark

3. **Program Transpilation (Chapter 5):**
   - 100% functional correctness with verification
   - More idiomatic code than C2Rust
   - Evaluated on real-world Go repositories

4. **Security Vulnerability Detection (Chapter 6):**
   - SOTA results on post-training-cutoff dataset
   - Multi-task learning for vulnerability + explanation
   - Addresses data contamination concerns

5. **Node.js Vulnerability Detection (Chapter 7):**
   - F1 score of 0.943 (NodeMedic-GNN)
   - Outperforms traditional program analysis
   - Evaluated on real Node.js packages

## Timeline Suggestion

1. **Week 1:** Revise thesis statement (iterate with advisors)
2. **Week 2:** Update Introduction (contributions + novelty claims)
3. **Week 3:** Restructure Background chapter
4. **Week 4:** Add chapter openings (relate to thesis)
5. **Week 5:** Add chapter conclusions (evidence + contributions)
6. **Week 6:** Final review and title revision
