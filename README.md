# CYP1A2 Genotypes, Caffeine Metabolism and Sports Performance

A reproducible data analysis accompanying the BSc capstone thesis
*"Investigation of the Relationship Between CYP1A2 Genotypes, Caffeine
Metabolism and Enhanced Sports Performance: A Genetic-Based Approach to
Optimal Caffeine Consumption Practices for a Healthy Sports Lifestyle in
University Students and Young-Adult Turkish Population."*

**Author** Uğur Ersöz · Bahçeşehir University, Faculty of Engineering and
Natural Sciences, Department of Molecular Biology and Genetics
**Advisor** Asst. Prof. Zeynep Tacer Caba
**Submitted** June 2023 · MBG4999 Capstone Project

**Keywords** CYP1A2 · rs762551 · caffeine metabolism · nutrigenetics ·
sport genetics · 1000 Genomes Project

---

## Overview

The cytochrome P450 1A2 (*CYP1A2*) enzyme is the primary catalyst of
hepatic caffeine demethylation. A single-nucleotide polymorphism in
intron 1 of the gene (rs762551, C>A) stratifies individuals into rapid
(AA), intermediate (AC) and slow (CC) caffeine metabolisers, with
documented effects on the ergogenic response to caffeine
supplementation.

This repository contains the data analysis side of the capstone
project: a single Jupyter notebook that re-analyses publicly available
genotype distributions from one reference panel (1000 Genomes Project,
Phase 3, EUR superpopulation, n = 503) and five primary studies — two
in Turkish cohorts (Çelik et al., 2021; Yucesoy et al., 2017) and three
international cohorts (Santos et al., 2015; Aji et al., 2023; Pittsley
and Kolomyjec, 2022) — to compare allele frequencies across
populations and athletic sub-groups. A complementary online survey
assessed awareness of nutrigenetics and caffeine use among Turkish
university students and young adults.

## Research questions

1. How does the distribution of *CYP1A2* rs762551 genotypes in
   European-ancestry populations compare across the 1000 Genomes
   reference panel and smaller published cohorts?
2. Do Turkish samples (sedentary individuals and professional athletes)
   show genotype distributions consistent with the broader European
   pattern?
3. Is awareness of nutrigenetics and personalised caffeine use
   measurable in a Turkish young-adult cohort?

## Key findings

- **1000 Genomes EUR (n = 503):** 47.5 % AA · 41.0 % AC · 11.5 % CC.
- **LSSU student cohort (n = 164, Pittsley and Kolomyjec, 2022):**
  42.7 % rapid, 44.5 % intermediate, 12.8 % slow metabolisers —
  concordant with the 1000 Genomes EUR distribution.
- **Yucesoy et al. (2017), Turkish professional athletes:** long-distance
  runners are enriched for the slow-metabolising CC genotype compared
  to short-distance runners.
- Sample sizes of *CYP1A2* studies in the Turkish population remain
  small (n ≤ 30 in the studies reviewed), limiting inference.

## Repository layout

```
bsc-capstone-project/
├── notebooks/
│   └── 01_cyp1a2_analysis.ipynb     analysis and figure generation
├── data/
│   ├── README.md                    data provenance, sources, licences
│   └── raw/
│       ├── genotypes_1000genomes_phase3_eur.xlsx
│       ├── caffeine_content_fsanz.xlsx
│       ├── santos_2015.xlsx
│       ├── aji_2023.xlsx
│       ├── yucesoy_2017.xlsx
│       ├── celik_2021.xlsx
│       └── pittsley_kolomyjec_2022.xlsx
├── references/
│   ├── references.bib               BibTeX for all thesis citations
│   └── pdfs/                        article PDFs (reviewer convenience)
│       ├── santos_2015.pdf
│       ├── aji_2023.pdf
│       ├── yucesoy_2017.pdf
│       ├── celik_2021.pdf
│       └── pittsley_kolomyjec_2022.pdf
├── requirements.txt                 pinned Python dependencies
├── CITATION.cff                     machine-readable citation
├── LICENSE                          MIT
└── README.md
```

Each cohort's raw genotype counts come from the corresponding article
in `references/pdfs/`; the per-individual 1000 Genomes EUR file was
pulled from Ensembl (see `data/README.md` for source URL and
retrieval date).

## Reproducing the analysis

```bash
git clone https://github.com/ugrersoz/bsc-capstone-project.git
cd bsc-capstone-project
python -m venv .venv
.venv\Scripts\activate                       # Windows PowerShell
# source .venv/bin/activate                  # macOS / Linux
pip install -r requirements.txt
jupyter notebook notebooks/01_cyp1a2_analysis.ipynb
```

Tested with Python 3.11. Excel I/O relies on `openpyxl`; figures use
`matplotlib` and `seaborn`. See `requirements.txt` for pinned versions.

The notebook reads data with paths relative to its own location
(`../data/raw/...`), so it must be run from `notebooks/`. Jupyter does
this automatically.

## Limitations

The Turkish-population studies aggregated here have small sample sizes
(n ≤ 30), which constrains statistical inference. The reference
distribution from the 1000 Genomes Project covers the EUR
super-population rather than a Turkish-specific panel; conclusions
drawn about Turkish populations from EUR allele frequencies are
therefore indirect. The awareness survey used non-probability sampling
and is reported for descriptive purposes only; the underlying
microdata is not redistributed (see `data/README.md`).

## Citation

If you use this repository, please cite the underlying thesis:

> Ersöz, U. (2023). *Investigation of the Relationship Between CYP1A2
> Genotypes, Caffeine Metabolism and Enhanced Sports Performance.* BSc
> Capstone Project, Bahçeşehir University, Department of Molecular
> Biology and Genetics. Advisor: Z. Tacer Caba.

A machine-readable citation is provided in `CITATION.cff` — GitHub
exposes it through the "Cite this repository" button.

## Licence

- Source code and notebook: MIT Licence (see `LICENSE`).
- Figures and derived data summaries: CC BY 4.0.
- The third-party article PDFs in `references/pdfs/` are retained here
  for the convenience of reviewers of the original thesis only; please
  access them through their DOIs in `references/references.bib` for
  any other use, and refer to the publishers' own licence terms.

## Acknowledgements

Thesis supervised by Asst. Prof. Zeynep Tacer Caba. The author thanks
Asst. Prof. Cemalettin Bekpen (Head of Department) for early guidance,
and is grateful to family for their support throughout the project.

## Contact

Uğur Ersöz · uersoz55@gmail.com
