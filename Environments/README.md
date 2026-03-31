## Conda environments and R sessions used for this Benchmarking

benchmarking.yml is a combined conda environment that allows you to run all notebooks in `Processing/` in combination with a functioning R environment.

However, if you want to exactly reproduce the results of this study you need to use the respective conda environment for each tool, i.e.
`CellBender.yml`, `CellClear.yml` and `scAR.yml`, `base.yml` for all Scanpy processing steps as well as the respective R environments `R_session_DecontX.txt`, `R_session_SoupX.txt` and `R_session_scCDC.txt`.
