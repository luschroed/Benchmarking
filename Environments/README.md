# Environments

This directory contains all conda environment files required to reproduce the analyses in this study.

## Quick start

For a combined environment that runs all notebooks in `Processing/` with a functioning R setup:
```bash
conda env create -f benchmarking.yml
conda activate benchmarking
```

Note that this combined environment does not pin tool-specific dependency versions and may produce minor numerical differences from the published results.

## Exact reproduction

To exactly reproduce the results of this study, use the tool-specific environments below.

### Python environments

| File | Use |
|---|---|
| `CellBender.yml` | CellBender correction notebooks |
| `scAR.yml` | scAR correction notebooks |
| `CellClear.yml` | CellClear correction notebooks |
| `base.yml` | All other Scanpy-based processing steps |

Each file contains an explicit environment name. Install and activate with:
```bash
conda env create -f <environment_file>.yml
conda activate <env_name>
```

For example:
```bash
conda env create -f CellClear.yml
conda activate cellclear
```

### R environments

R-based tools were run with sessionInfo-captured package versions. To reproduce the R environment, manually install the listed package versions from the corresponding file.

| File | Use |
|---|---|
| `R_session_DecontX.txt` | DecontX |
| `R_session_SoupX.txt` | SoupX |
| `R_session_scCDC.txt` | scCDC |

The session files are plain-text `sessionInfo()` outputs listing all loaded packages and their exact versions at the time of analysis.
