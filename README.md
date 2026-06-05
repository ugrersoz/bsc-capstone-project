# CYP1A2 Genotypes, Caffeine Metabolism and Sports Performance

Reproducible data analysis accompanying the BSc Capstone thesis
*"Investigation of the Relationship Between CYP1A2 Genotypes, Caffeine
Metabolism and Enhanced Sports Performance: A Genetic-Based Approach to
Optimal Caffeine Consumption Practices for a Healthy Sports Lifestyle in
University Students and Young-Adult Turkish Population."*

**Author:** Uğur Ersöz · Bahçeşehir University, Faculty of Engineering and
Natural Sciences, Department of Molecular Biology and Genetics
**Advisor:** Asst. Prof. Zeynep Tacer Caba
**Submitted:** June 2023 · MBG4999 Capstone Project
**Keywords:** CYP1A2 · rs762551 · caffeine metabolism · nutrigenetics ·
sport genetics · 1000 Genomes Project

---

## Abstract

The cytochrome P450 1A2 (*CYP1A2*) enzyme is the primary catalyst of
hepatic caffeine demethylation. A single-nucleotide polymorphism in
intron 1 of the gene (rs762551, C>A) stratifies individuals into rapid
(AA), intermediate (AC) and slow (CC) caffeine metabolisers, with
documented effects on the ergogenic response to caffeine
supplementation. This project compiles publicly available genotype
distributions from one global reference panel (1000 Genomes Project,
Phase 3, EUR superpopulation, n = 503) and four primary studies — two
in Turkish cohorts (Çelik et al., 2021; Yucesoy et al., 2017) and three
international cohorts (Santos et al., 2015; Aji et al., 2023; Pittsley
and Kolomyjec, 2022) — and re-analyses them in a single Jupyter
notebook to compare allele frequencies across populations and athletic
sub-groups. A complementary online survey assessed awareness of
nutrigenetics and caffeine use among Turkish university students and
young adults.

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

## Repository contents

The repository currently keeps all data and analysis files at the
project root. A more conventional `notebooks/` and `data/raw/` layout
is planned for a future revision.

| Path | Description |
|---|---|
| `Capstone Project_Data.ipynb` | Jupyter notebook containing the full analysis and figure generation |
| `Genotypes for 1000GENOMES phase_3 EUR.xlsx` | Per-individual genotypes at rs762551 for the 1000 Genomes Phase 3 EUR super-population (n = 503), retrieved from Ensembl |
| `Caffeine content of common foods, drinks and therapeutic products (Australia).xlsx` | Reference caffeine-content table (FSANZ) used for the discussion of dietary caffeine sources |
| `Article #1.pdf` / `.xlsx` | Santos et al., 2015 — global perspective, plasma caffeine after standardised coffee (n = 15) |
| `Article #2.pdf` / `.xlsx` | Aji et al., 2023 — caffeine timing and endurance in sedentary young adults (n = 30) |
| `Article #3.pdf` / `.xlsx` | Yucesoy et al., 2017 — Turkish professional athletes (n = 20, long- vs short-distance) |
| `Article #4.pdf` / `.xlsx` | Çelik et al., 2021 — Turkish healthy individuals (n = 30) |
| `Article #5.pdf` / `.xlsx` | Pittsley and Kolomyjec, 2022 — Lake Superior State University students (n = 164, bioRxiv preprint) |
| `references/references.bib` | BibTeX entries with DOIs for all 35 sources cited in the thesis |
| `data/README.md` | Data provenance: source, retrieval date, licence, preprocessing |
| `requirements.txt` | Pinned Python dependencies |
| `CITATION.cff` | Machine-readable citation metadata |
| `LICENSE` | MIT licence |

## Reproducibility

```bash
git clone https://github.com/ugrersoz/bsc-capstone-project.git
cd bsc-capstone-project
python -m venv .venv
.venv\Scripts\activate                       # Windows PowerShell
# source .venv/bin/activate                  # macOS / Linux
pip install -r requirements.txt
jupyter notebook "Capstone Project_Data.ipynb"
```

Tested with Python 3.11. Excel I/O relies on `openpyxl`; figures use
`matplotlib` and `seaborn`. See `requirements.txt` for pinned versions.

## Limitations

The Turkish-population studies aggregated here have small sample sizes
(n ≤ 30), which constrains statistical inference. The reference
distribution from the 1000 Genomes Project covers the EUR
super-population rather than a Turkish-specific panel; conclusions drawn
about Turkish populations from EUR allele frequencies are therefore
indirect. The awareness survey used non-probability sampling and is
reported for descriptive purposes only.

## Citation

If you use this repository, please cite both the thesis and this code:

> Ersöz, U. (2023). *Investigation of the Relationship Between CYP1A2
> Genotypes, Caffeine Metabolism and Enhanced Sports Performance.* BSc
> Capstone Project, Bahçeşehir University, Department of Molecular
> Biology and Genetics. Advisor: Z. Tacer Caba.

A machine-readable citation is provided in `CITATION.cff` — GitHub
exposes it through the "Cite this repository" button.

## Licence

- Source code and notebooks: MIT Licence (see `LICENSE`).
- Figures and derived data summaries: CC BY 4.0.
- The third-party article PDFs included in this repository are retained
  here for the convenience of reviewers of the original thesis only;
  please access them through their DOIs in `references/references.bib`
  for any other use, and refer to the publishers' own licence terms.

## Acknowledgements

Thesis supervised by Asst. Prof. Zeynep Tacer Caba. The author thanks
Asst. Prof. Cemalettin Bekpen (Head of Department) for early guidance,
and is grateful to family for their support throughout the project.

## Contact

Uğur Ersöz · uersoz55@gmail.com
