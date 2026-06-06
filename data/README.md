# Data Provenance

This directory documents the raw input data consumed by
`../notebooks/01_cyp1a2_analysis.ipynb`. Each file is described below
with its original source, the date it was retrieved, the licence under
which it is redistributed (or not), and any preprocessing that was
applied before it entered this repository.

For full bibliographic entries of the source publications, see
`../references/references.bib`.

```
data/raw/
├── genotypes_1000genomes_phase3_eur.xlsx     1000 Genomes EUR genotypes (Ensembl, n=503)
├── caffeine_content_fsanz.xlsx               FSANZ caffeine reference table
├── santos_2015.xlsx                          Santos et al. 2015 cohort (n=15)
├── aji_2023.xlsx                             Aji et al. 2023 cohort (n=30)
├── yucesoy_2017.xlsx                         Yucesoy et al. 2017 cohort (n=20)
├── celik_2021.xlsx                           Çelik et al. 2021 cohort (n=30)
└── pittsley_kolomyjec_2022.xlsx              Pittsley & Kolomyjec 2022 cohort (n=164)
```

---

## 1. `raw/genotypes_1000genomes_phase3_eur.xlsx`

**What.** Per-individual genotype calls at the *CYP1A2* intron-1 SNP
**rs762551** (C>A) for the EUR (European-ancestry) super-population of the
1000 Genomes Project, Phase 3. n = 503 individuals across five sub-populations
(CEU, TSI, FIN, GBR, IBS).

**Source.** Ensembl Genome Browser, "Sample genotypes" panel for variant
rs762551:
<https://www.ensembl.org/Homo_sapiens/Variation/Sample?v=rs762551>

**Retrieved.** 2023-06 (during the original thesis work). Re-pulls from
Ensembl may differ if the dataset is rebuilt against a newer reference
assembly or recalled VCF; the analysis in this repository assumes the
snapshot captured in this file.

**Licence.** 1000 Genomes Project data are released into the public domain
for unrestricted research use; see the project data-use statement at
<https://www.internationalgenome.org/data-portal/data-collection/phase-3>.
No restrictions apply to redistribution of the subset stored here.

**Preprocessing.**
- Genotype column normalised to the set `{AA, AC, CC}` (Ensembl returns
  `A|A`, `A|C`, `C|C` — pipe characters were stripped and alleles
  alphabetised so heterozygous calls are always recorded as `AC`).
- Sub-population labels retained as a separate column for the regional
  breakdown in Figures 17–20 of the thesis.

**Citation.** See `@ensembl1000g_rs762551` in `references.bib`.

---

## 2. `raw/caffeine_content_fsanz.xlsx`

**What.** Reference table of caffeine content (mg per standard serving) for
common foods and beverages — coffee preparations, teas, energy drinks,
soft drinks, chocolate products, guarana, yerba mate, and selected
over-the-counter products. Used in the introductory exposition of caffeine
sources (Chapter 3.1 and Figure 1 of the thesis).

**Source.** Food Standards Australia New Zealand (FSANZ), *Caffeine content
of common foods, drinks and other products*, public technical report.

**Retrieved.** 2023-06.

**Licence.** FSANZ publications are © Commonwealth of Australia and released
under a Creative Commons Attribution 3.0 Australia licence
(<https://creativecommons.org/licenses/by/3.0/au/>). Attribution preserved in
this README satisfies the licence terms for redistribution of the underlying
values.

**Preprocessing.** None. The file is the unmodified workbook.

---

## 3–7. Published cohort spreadsheets

The five cohort workbooks (`santos_2015.xlsx`, `aji_2023.xlsx`,
`yucesoy_2017.xlsx`, `celik_2021.xlsx`, `pittsley_kolomyjec_2022.xlsx`)
contain the per-individual or per-group genotype counts transcribed from the
corresponding article (PDFs available under `../references/pdfs/`). They are
not original data: they are working copies prepared for re-analysis in the
notebook, and the underlying values are drawn from the published tables of
each study. Counts and percentages, not the article text or figures, are
what is retained.

| File | Cohort | n | Source | DOI / URL |
|---|---|---|---|---|
| `raw/santos_2015.xlsx` | Healthy volunteers (plasma caffeine) | 15 | Santos et al., 2015 (Austin J Pharm Ther) | open access, see `references.bib` |
| `raw/aji_2023.xlsx` | Sedentary young adults (timing study) | 30 | Aji et al., 2023 (Reports Biochem Mol Biol) | <https://rbmb.net/browse.php?a_id=1020> |
| `raw/yucesoy_2017.xlsx` | Turkish professional athletes | 20 | Yucesoy et al., 2017 (Eur J Biol) | see `references.bib` |
| `raw/celik_2021.xlsx` | Turkish healthy individuals | 30 | Çelik et al., 2021 | see `references.bib` |
| `raw/pittsley_kolomyjec_2022.xlsx` | LSSU student cohort | 164 | Pittsley & Kolomyjec, 2022 (bioRxiv) | <https://doi.org/10.1101/2022.06.14.496190> |

The original publications must be accessed through their DOIs for any
use beyond reproducing the figures in this repository.

---

## Survey data (Turkish young-adult awareness study)

The notebook contains a cell that reads `raw/survey_responses.xlsx`.
That file is **not included** in this repository because participants
of the online awareness survey were not consented for open data
release. The cell will therefore raise a `FileNotFoundError` on a
clean checkout — this is intentional and serves as a placeholder for
the analysis step.

Aggregate counts and percentages reported in Chapter 4 of the thesis
are the only outputs that may be cited. Requests for access to the
de-identified microdata for replication purposes can be addressed to
the author (`uersoz55@gmail.com`) and will be evaluated against the
original ethics scope.

---

## Reproducibility checklist

- [x] Every file has a named upstream source.
- [x] Retrieval date is recorded.
- [x] Redistribution licence is identified.
- [x] Preprocessing steps are documented (and minimal).
- [x] Data that cannot be redistributed is excluded with a stated reason.
