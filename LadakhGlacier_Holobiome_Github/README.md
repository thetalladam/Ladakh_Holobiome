# Ladakh glacier forefield holobiome — analysis code (REVISION)

Scripts and input data that run from the phyloseq objects and plot metadata.  
Raw reads: NCBI SRA **PRJNA1479924** (ITS), **PRJNA1434027** (16S).

Network / NetCoMi workflows are not included here (heavy to rebuild; contact authors for network scripts and intermediate CSVs).

## Setup

1. Open **`Glacier Transects.Rproj`**
2. Install packages (below)
3. Knit:

| Script | What |
|--------|------|
| `Molecular/ITS/Microbe_explore.Rmd` | α-/β-diversity, PERMANOVA, beta-dispersion |
| `Cover_Chronosequence_REVISION.Rmd` | Cover RDAs, correlations, SEM |
| `Molecular/Composition_moraine_pooled_by_source_REVISION.Rmd` | Composition bar plots |

## Data

| File | Use |
|------|-----|
| `Glacier_Soil_Topo_merged.xlsx` | Soil, cover, topography |
| `Molecular/ITS/La_Gla_final_*_core.Rds` | Core phyloseq (SEM / cover) |
| `Molecular/ITS/La_Gla_final_*.Rds` | Full phyloseq (composition) |
| `Molecular/Ladakh_Glacier_*_tax_filt.Rds` | Diversity / PERMANOVA |
| `DADA2_track_each.tsv` | Read tracking (Methods) |

## Packages

```r
install.packages(c(
  "tidyverse", "rmarkdown", "knitr", "kableExtra", "readxl", "writexl",
  "openxlsx", "vegan", "lme4", "lmerTest", "car", "emmeans", "ARTool",
  "svglite", "patchwork", "ggrepel", "lavaan", "piecewiseSEM"
))
if (!requireNamespace("BiocManager", quietly = TRUE)) install.packages("BiocManager")
BiocManager::install(c("phyloseq", "Biostrings", "microbiome"))
install.packages("microViz")
```
