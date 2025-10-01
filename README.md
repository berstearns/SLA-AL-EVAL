# SLA-AL-EVAL: Evaluating Generative LLMs for Second Language Learner Simulation

This repository contains the LaTeX source for a research paper investigating how generative Large Language Models (LLMs) can simulate second language learners' responses across different task types.

## Research Overview

The paper explores whether LLMs specialized for different pre-training objectives (Next Word Prediction vs. Masked Language Modeling) show differential performance when simulating learner responses on:

1. **Production tasks** (open-ended writing) - aligned with NWP training
2. **Fill-in-the-gap exercises** (constrained completion) - aligned with MLM training

### Key Research Questions

- **RQ1**: Can generative LLMs simulate L2 learners at different CEFR levels (A1-C2) across both task types?
- **RQ2**: Do task-specialized models show superior simulation fidelity on their aligned tasks?
- **RQ3**: How do simulation quality and error patterns differ across model architectures and sizes?

## Repository Structure

```
SLA-AL-EVAL/
├── main.tex                    # Main document
├── lrec2026.sty               # LREC 2026 style file
├── lrec2026-natbib.bst        # Bibliography style
├── lrec2026-example.bib       # Bibliography entries
├── metadata/
│   ├── title.tex              # Paper title
│   ├── authors.tex            # Author information
│   └── abstract.tex           # Abstract
├── sections/
│   ├── 01-introduction/
│   │   └── introduction.tex   # Introduction section
│   ├── 02-related-work/
│   │   └── related-work.tex   # Related work section
│   ├── 03-methodology/
│   │   └── methodology.tex    # Methodology section
│   ├── 04-results/
│   │   └── results.tex        # Results section
│   ├── 05-discussion/
│   │   └── discussion.tex     # Discussion section
│   └── 06-conclusion/
│       └── conclusion.tex     # Conclusion section
├── tables/                     # LaTeX tables (to be added)
├── bibs/                       # Additional bibliography files
├── markdowns/                  # Markdown versions of content
└── docs/                       # Additional documentation
```

## Compilation

To compile the paper:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Or use latexmk for automatic compilation:

```bash
latexmk -pdf main.tex
```

## Key Contributions

1. Systematic evaluation framework for LLM-based learner simulation across two fundamental task types
2. Prompt engineering strategies adapted for second language learner role-playing
3. Comparative analysis of NWP vs. MLM models on production and gap-filling tasks
4. Error pattern analysis revealing where LLM simulations diverge from authentic learner behavior
5. Empirical findings on three learner corpora (EFCAMDAT, Cambridge, TOEFL11)

## Template Source

This paper structure was adapted from:
- **Template**: AL-CEFR-LREC-2026 (CEFR Classification through Artificial Learners)
- **Content inspiration**: "Using LLMs to Simulate Students' Responses to Exam Questions" (Benedetto et al., EMNLP 2024 Findings)

## Models Evaluated

### NWP-Specialized (Autoregressive)
- GPT-3.5-turbo
- GPT-4
- LLaMA-3-8B
- Mistral-7B

### MLM-Specialized (Bidirectional)
- BERT-base
- RoBERTa-large
- ELECTRA-large

## Datasets

- **EFCAMDAT**: 723K learner writings (A1-C2)
- **Cambridge Learner Corpus**: Fill-in-the-gap exercises with authentic responses
- **TOEFL11**: 12K essays from 11 L1 backgrounds

## Key Findings (Summary)

1. ✅ LLMs can simulate proficiency-specific patterns in both task types
2. ✅ Task-model alignment shows measurable but modest effects (MLM better for gap-filling)
3. ⚠️ Larger models suffer from "hyper-accuracy" at lower proficiency levels
4. ⚠️ Best simulation at intermediate levels (B1-B2); struggles at endpoints (A1, C2)
5. ⚠️ Prompts require model-specific engineering; poor cross-model generalization

## Author

**Bernardo Stearns**
Insight Centre for Data Analytics
Data Science Institute, University of Galway, Ireland
bernardo.stearns@insight-centre.org

## License

This work is for academic research purposes. Please cite appropriately if using or building upon this work.

## Citation

```bibtex
@inproceedings{stearns2025sla,
  title={Evaluating Generative LLMs for Second Language Learner Simulation: Production vs. Fill-in-the-Gap Tasks},
  author={Stearns, Bernardo},
  booktitle={Proceedings of the 2026 Language Resources and Evaluation Conference (LREC)},
  year={2026}
}
```

## Acknowledgments

This work has been supported by Science Foundation Ireland under Grant Number SFI/12/RC/2289_P2 Insight_2, Insight SFI Centre for Data Analytics.

---

**Status**: Draft in progress
**Target Conference**: LREC 2026
**Last Updated**: October 2025
