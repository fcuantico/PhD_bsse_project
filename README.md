# Phd_bsse_project

**Iowa State University — Computational Chemistry**
**PI:** Dr. Ryan Richard & Prof. Theresa — `rmrresearch/bsse_db`
**Branch context:** `fcuantico`

---

## Overview

This repository contains the LaTeX source for a research report (and eventual
thesis chapter / publication) on Basis Set Superposition Error (BSSE) in
\ce{H2O} clusters, from the dimer through the trimer, using the
Valiron-Mayer Function Counterpoise (VMFC) method at the
SCF, MP2, and CCSD(T) levels with the aug-cc-pVDZ basis set.

The broader project goal (PI Task List, Issue #46) is to identify thresholds
that allow expensive BSSE correction terms to be dropped without significant
loss of accuracy.

---

## Repository Structure

```
Phd_bsse_project/
├── main.tex                  ← master document (calls all sections)
├── references.bib            ← bibliography (biber/biblatex)
├── .gitignore                ← LaTeX artifacts and PDFs excluded
├── sections/
│   ├── intro.tex             ← Ch.1  Project motivation and scope
│   ├── theory.tex            ← Ch.2  BSSE theory, VMFC, FORM I/II
│   ├── dimer.tex             ← Ch.3  H2O dimer results
│   ├── trimer_setup.tex      ← Ch.4  Trimer data pipeline
│   ├── trimer_bsse.tex       ← Ch.5  Trimer BSSE decomposition
│   ├── trimer_interaction.tex← Ch.6  BSSE vs interaction energy
│   └── next_steps.tex        ← Ch.7  Outlook and remaining tasks
└── figures/
    ├── theory/               ← diagrams for theory chapter
    ├── dimer/                ← dimer plots
    └── trimer/               ← trimer plots (modes 1-5, interaction)
```

---

## Building

Requires a full TeX Live installation with `biber`:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

Or with `latexmk`:

```bash
latexmk -pdf -bibtex main.tex
```

---

## Packages Required

| Package     | Purpose                                      |
|-------------|----------------------------------------------|
| `amsmath`   | Mathematics                                  |
| `amssymb`   | Math symbols                                 |
| `mhchem`    | Chemical formulas (`\ce{H2O}`, `\ce{CCSD(T)}`) |
| `siunitx`   | Units (`\SI{2.75}{\angstrom}`)               |
| `booktabs`  | Publication-quality tables                   |
| `biblatex`  | Bibliography (biber backend)                 |
| `hyperref`  | PDF links                                    |

---

## Status

| Chapter | Section file         | Status      |
|---------|----------------------|-------------|
| 1       | `intro.tex`          | 🔲 TODO     |
| 2       | `theory.tex`         | 🔲 TODO     |
| 3       | `dimer.tex`          | 🔲 TODO     |
| 4       | `trimer_setup.tex`   | 🔲 TODO     |
| 5       | `trimer_bsse.tex`    | 🔲 TODO     |
| 6       | `trimer_interaction.tex` | 🔲 TODO |
| 7       | `next_steps.tex`     | 🔲 TODO     |

---

## Data Source

Raw NWChem output files and analysis scripts live in the separate
[`rmrresearch/bsse_db`](https://github.com/rmrresearch/bsse_db) repository
on branch `fcuantico`. This repo contains only the write-up.
