# Processing

This directory contains notebooks for applying each ambient RNA removal tool to all datasets.
Notebooks output processed `.h5ad` files consumed by the `Analysis/` notebooks.

Run the `uncorrected` notebook first for each dataset type to generate the baseline object.

## hgmm datasets (6 datasets, 1k–20k cells)

| Notebook | Tool / purpose |
|---|---|
| `hgmm_uncorrected.ipynb` | Baseline — no correction applied |
| `hgmm_cellbender.ipynb` | CellBender correction |
| `hgmm_soupx.ipynb` | SoupX correction |
| `hgmm_decontx.ipynb` | DecontX correction |
| `hgmm_sccdc.ipynb` | scCDC correction |
| `hgmm_scar.ipynb` | scAR correction |
| `hgmm_cellclear.ipynb` | CellClear correction |

## Complex tissue datasets (PBMC, PFC snRNA-seq, WBC BD Rhapsody)

| Notebook | Tool / purpose |
|---|---|
| `complex_uncorrected.ipynb` | Baseline — no correction applied |
| `complex_cellbender.ipynb` | CellBender correction |
| `complex_soupx.ipynb` | SoupX correction |
| `complex_decontx.ipynb` | DecontX correction |
| `complex_sccdc.ipynb` | scCDC correction |
| `complex_scar.ipynb` | scAR correction |
| `complex_cellclear.ipynb` | CellClear correction |

## Environment requirements

Each tool requires its own conda environment — see `Environments/` for details.
All Scanpy-based steps use `base.yml`. R-based tools (DecontX, SoupX, scCDC) use the
respective R session files.
