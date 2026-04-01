# Benchmarking ambient RNA removal across droplet and well-plate platforms reveals artificial count inflation as a critical failure mode of scAR and CellClear

This repository contains all code and supporting information to reproduce the analyses presented in the manuscript:

> **"Benchmarking ambient RNA removal tools for single-cell RNA sequencing across droplet-based and well-plate platforms reveals artificial count inflation by scAR and CellClear"**  
> Schroeder et al., 2026 *(preprint/submitted)*

---

## Overview

Ambient RNA contamination is a well-known confound in droplet-based single-cell and single-nucleus RNA-seq experiments. Several computational tools have been developed to correct for this, but their comparative performance — particularly across different sequencing platforms and in real-world datasets — remains poorly characterised.

We benchmark six ambient RNA removal tools across a diverse set of datasets including technical benchmarking controls (HGMM multiplexed libraries), lipid-based library preparation datasets, and a well-plate-based platform, representing a broader evaluation than previously published comparisons.

**Tools benchmarked:**
- [CellBender](https://github.com/broadinstitute/CellBender)
- [SoupX](https://github.com/constantAmateur/SoupX)
- [DecontX](https://github.com/campbio/celda)
- [scCDC](https://github.com/ZJU-UoE-CCW-LAB/scCDC)
- [scAR](https://github.com/Novartis/scAR)
- [CellClear](https://github.com/lcmicrobiome/CellClear)

**Datasets:**
- 6 human-mouse mixture (HGMM) datasets from 10x Genomics droplet-based platforms
- 2 lipid-based library preparation datasets (from published studies)
- 1 well-plate-based dataset (from a published study)

**Key finding:** scAR and CellClear generate artificial count inflation under certain conditions, representing a previously underappreciated failure mode with direct implications for downstream analyses.

---

## Repository Structure
```
.
├── Processing/       # Raw data processing and ambient RNA tool application
├── Analysis/         # Downstream benchmarking analyses and figures
├── Environments/     # Conda/pip environment files for reproducibility
└── README.md
```

---

## Reproducibility

Environment files for all tool-specific and analysis environments are provided in `Environments/`. We recommend creating separate environments per tool due to dependency conflicts.

---

## Citation

If you use this code or build on this work, please cite:  
*Schroeder et al. (2026) — manuscript details to be updated upon publication.*

---

## License

GPL-3.0 — see [LICENSE](LICENSE) for details.
