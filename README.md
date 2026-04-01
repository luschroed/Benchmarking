# Benchmarking ambient RNA removal across droplet and well-plate platforms reveals artificial count generation as a critical failure mode of scAR and CellClear

This repository contains all code and supporting information to reproduce the analyses presented in:

> **"Benchmarking ambient RNA removal across droplet and well-plate platforms reveals artificial count generation as a critical failure mode of scAR and CellClear"**  
> Lukas Schroeder, Susanne Gerber, Nicolas Ruffini  
> *Institute of Human Genetics, University Medical Center Mainz* | *(preprint/submitted)*

---

## Overview

Ambient RNA contamination is a pervasive artefact of droplet-based single-cell and single-nucleus RNA sequencing (sxRNA-seq). Multiple computational tools exist to correct for it, but consensus on which performs best and under what conditions is lacking, particularly across experimental platforms and at scale.

We benchmark six ambient RNA removal tools across a diverse panel of nine datasets, including technical benchmarking controls (human-mouse cell line mixtures), complex tissue datasets, and a well-plate-based platform. A key contribution is the explicit quantification of **artificial count inflation**, i.e. corrected values exceeding raw counts as a distinct and previously undercharacterised failure mode.

### Tools benchmarked

| Tool | Algorithm | Requires raw matrix | Platform scope |
|---|---|---|---|
| [CellBender](https://github.com/broadinstitute/CellBender) | Variational autoencoder | Yes | Droplet |
| [SoupX](https://github.com/constantAmateur/SoupX) | Maximum likelihood / proportional subtraction | Yes | Droplet |
| [DecontX](https://github.com/campbio/celda) | Bayesian mixture model | No | Droplet + well-plate |
| [scCDC](https://github.com/ZhangLabGT/scCDC) | Gene-selective contamination correction | No | Droplet (+ claimed general) |
| [scAR](https://github.com/Novartis/scAR) | Variational autoencoder | Yes | Droplet |
| [CellClear](https://github.com/lcmicrobiome/CellClear) | Non-negative matrix factorisation | Yes | Droplet |

> FastCAR was considered but excluded: it targets differential gene expression optimisation rather than global ambient removal, making it incompatible with the ground-truth metrics used here.


| Dataset | Platform | Accession | Cells |
|---|---|---|---|
| hgmm 1k–20k (6 datasets) | 10x Chromium | [10x Genomics website](https://www.10xgenomics.com/datasets) | 1,000–20,000 |
| PBMC | 10x Chromium | [10x Genomics website](https://www.10xgenomics.com/datasets) | — |
| Prefrontal cortex (PFC) snRNA-seq | 10x Chromium 3' v3 | [GSE168408](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE168408) | 158,490 |
| White blood cells (WBC) | BD Rhapsody WTA | [GSE234676](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE234676) | 120,602 |


### Key findings

- scAR and CellClear generate artificial count inflation as a systematic failure mode, not mere denoising artefact
- CellClear replaces >93% of counts with NMF-derived values; scAR produces spurious cell types absent from uncorrected data
- CellBender and SoupX show reliable removal with minimal count distortion
- DecontX and scCDC are the only tools applicable to non-droplet platforms without the raw count matrix
- CellClear fails to scale to atlas-size data (tested up to 172,000 nuclei)

---

## Repository structure
```
.
├── Processing/        # Raw data processing and per-tool ambient RNA correction
├── Analysis/          # Downstream benchmarking analyses and figure generation
├── Environments/      # Conda/pip environment files for reproducibility
└── README.md
```

Due to dependency conflicts between tools, separate environments are provided per tool in `Environments/`.

---

## Citation

*Citation details to be updated upon publication.*

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19348468.svg)](https://doi.org/10.5281/zenodo.19348468)


---

## License

GPL-3.0 — see [LICENSE](LICENSE) for details.
