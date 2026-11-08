# Panniculitis analysis workflow

Analysis code for the manuscript

> Ziadlou R, Ameri M, et al. **Spatial mapping reveals convergent cytotoxic inflammation and divergent immune architectures in panniculitis.** *Nature Communications* (2026).

The workflow covers imaging mass cytometry (IMC), targeted transcriptomics (NanoString nCounter) and immunofluorescence (IF) of subcutaneous white adipose tissue from erythema nodosum (EN), erythema induratum (EI) and healthy controls (HC). It is organised as a [workflowr](https://github.com/workflowr/workflowr) project.

## Contents

| File (`analysis/`) | What it does | Figures |
|---|---|---|
| `01_IMC_read_data.Rmd` | Reads steinbock output (single-cell intensities, images, masks) into a `SpatialExperiment`, adds sample metadata, arcsinh transformation | - |
| `02_IMC_marker_quality_check.Rmd` | Marker and image quality control | - |
| `03_IMC_Clustering.Rmd` | Batch correction (fastMNN), clustering (PhenoGraph), cell-type annotation, neighbourhood analysis (imcRtools `testInteractions`) | - |
| `04_IMC_Figures.Rmd` | IMC figures and statistics | Figs. 1C-E, 2, 3A/D/G; Suppl. Figs. 2B, 3 |
| `05_NanoString_Figures.Rmd` | nCounter heatmaps, boxplots and statistics (nSolver-normalised data) | Figs. 4, 5, 6, 7A; Suppl. Fig. 2A |
| `06_IF_IL1B_NLRP3_LPS_LTA.Rmd` | Immunofluorescence quantification (IL-1β, NLRP3, LTA, LPS) | Fig. 7B; Suppl. Fig. 4 |

Run the files in the order above (for example with `workflowr::wflow_build()` or by knitting each file). Paths are relative to the project root via `here::here()`. `01_IMC_read_data.Rmd` expects the steinbock output folder in `../data` (change `steinbock_dir` at the top of the file if it is stored elsewhere).

## Data

The data are **not included** in this repository. Because they derive from patient material, the IMC (.mcd, steinbock output, processed `SpatialExperiment` objects), nCounter and immunofluorescence data are available under restricted access, as described in the Data Availability statement of the paper (requests to the corresponding author). The numerical data underlying the figures are provided in the Source Data file of the paper. The files expected in `data/` are listed in `data/README.md`.

## Software

Upstream processing: steinbock (0.16.1) with DeepCell/Mesmer segmentation for IMC, nSolver Analysis Software (4.0) for nCounter normalisation and differential expression, ImageJ (2.16.0) for IF measurements.

R (4.5.0) with, among others: imcRtools (1.14.0), batchelor (1.24.0), cytomapper, dittoSeq, scuttle, scater, scran, bluster, Rphenograph, CATALYST, ComplexHeatmap, pheatmap, ggplot2, ggpubr, rstatix, dplyr, tidyr, readxl, openxlsx and here.

## License

Code: MIT License (see `LICENSE`).

## Citation

If you use this code, please cite the paper above and this repository: https://doi.org/10.5281/zenodo.XXXXXXX
