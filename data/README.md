# Data Provenance

This directory documents the raw input data consumed by
`../Capstone Project_Data.ipynb`. Each file is described below with its
original source, the date it was retrieved, the licence under which it is
redistributed (or not), and any preprocessing that was applied before it
entered this repository.

For full bibliographic entries of the source publications, see
`../references/references.bib`.

---

## Current location of the data files

For historical reasons, the raw data files described here are still kept at
the **project root**, not under `data/raw/`. A future revision of the
repository will move them. The two files are:

- `../Genotypes for 1000GENOMES phase_3 EUR.xlsx`
- `../Caffeine content of common foods, drinks and therapeutic products (Australia).xlsx`

Re-derived or cleaned outputs produced by the notebook (genotype-frequency
tables, summary statistics) are kept in-memory or written next to the
notebook; they are not stored in `data/` to keep the provenance chain
unambiguous.

---

## 1. `Genotypes for 1000GENOMES phase_3 EUR.xlsx` (repository root)

**What.** Per-individual genotype calls at the *CYP1A2* intron-1 SNP
**rs762551** (C>A) for the EUR (European-ancestry) super-population of the
1000 Genomes Project, Phase 3. n = 503 individuals across five sub-populations
(CEU, TSI, FIN, GBR, IBS).

**Source.** Ensembl Genome Browser, "Sample genotypes" panel for variant
rs762551:
<https://www.ensembl.org/Homo_sapiens/Variation/Sample?v=rs762551>

**Retrieved.** 2023-06 (during the original thesis work). Re-pulls from
Ensembl may differ if the dataset is rebuilt against a newer reference assembly
or recalled VCF; the analysis in this repository assumes the snapshot captured
in this file.

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

## 2. `Caffeine content of common foods, drinks and therapeutic products (Australia).xlsx` (repository root)

**What.** Reference table of caffeine content (mg per standard serving) for
common foods and beverages — coffee preparations, teas, energy drinks,
soft drinks, chocolate products, guarana, yerba mate, and selected
over-the-counter products. Used in the introductory exposition of caffeine
sources (Chapter 3.1 and Figure 1 of the thesis).

**Source.** Food Standards Australia New Zealand (FSANZ), *Caffeine content
of common foods, drinks and other products*, public technical report. The
spreadsheet variant of the same compilation that has circulated in
nutrition-genomics teaching material.

**Retrieved.** 2023-06.

**Licence.** FSANZ publications are © Commonwealth of Australia and released
under a Creative Commons Attribution 3.0 Australia licence
(<https://creativecommons.org/licenses/by/3.0/au/>). Attribution preserved in
this README satisfies the licence terms for redistribution of the underlying
values.

**Preprocessing.** None. The file is the unmodified workbook.

---

## Cohort summaries extracted from published articles

The five published cohorts re-analysed in the notebook are **not redistributed
as files** in this repository, because the underlying article PDFs are
copyright of their respective publishers. Only the small genotype-count
summary tables required to reproduce the figures are embedded directly in
the notebook as Python dictionaries. The original publications must be
accessed through their DOIs:

| # | Cohort                                  | n   | Source                                  | DOI / URL |
|---|-----------------------------------------|-----|------------------------------------------|-----------|
| 1 | Healthy volunteers (plasma caffeine)    | 15  | Santos et al., 2015 (Austin J Pharm Ther) | — (open access, see `references.bib`) |
| 2 | Sedentary young adults (timing study)   | 30  | Aji et al., 2023 (Reports Biochem Mol Biol) | <https://rbmb.net/browse.php?a_id=1020> |
| 3 | Turkish professional athletes           | 20  | Yucesoy et al., 2017 (Eur J Biol)        | — (verify) |
| 4 | Turkish healthy individuals             | 30  | Çelik et al., 2021                       | — (verify) |
| 5 | LSSU student cohort                     | 164 | Pittsley & Kolomyjec, 2022 (bioRxiv)     | <https://doi.org/10.1101/2022.06.14.496190> |

If you wish to reproduce the figures with the exact counts used in the
thesis, the per-genotype tallies are visible at the top of each
visualisation section of `notebooks/01_cyp1a2_analysis.ipynb`.

---

## Survey data (Turkish young-adult awareness study)

Anonymised responses from the online awareness survey administered to
Turkish university students and young adults are **not included** in this
repository because participants were not consented for open data release.
Aggregate counts and percentages reported in Chapter 4 of the thesis are
the only outputs that may be cited.

Requests for access to the de-identified microdata for replication purposes
can be addressed to the author (`uersoz55@gmail.com`) and will be evaluated
against the original ethics scope.

---

## Reproducibility checklist

- [x] Every file has a named upstream source.
- [x] Retrieval date is recorded.
- [x] Redistribution licence is identified.
- [x] Preprocessing steps are documented (and minimal).
- [x] Data that cannot be redistributed is excluded with a stated reason.
