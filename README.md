# CellMatchRLive

**Cell type matching for kidney RNA-seq data - runs entirely in your browser**

**Live app:** https://genepi-freiburg.github.io/CellMatchRLive/

## About

CellMatchR compares gene expression profiles from bulk RNA-sequencing of kidney cell lines, primary cells, or whole tissue to single-cell RNA-seq references using Spearman correlation and Euclidean distance.

**Key features:**
- Runs entirely in browser using WebAssembly (no data uploaded to any server)
- Spearman correlation and Euclidean distance metrics
- Interactive heatmaps with plotly
- 4 reference datasets (mouse and human)
- Upload your own samples, references, or marker genes

## Reference Datasets

| Reference | Species | Cell Types | Description |
|-----------|---------|------------|-------------|
| Ransick et al. (2019) | Mouse | 40 | High-resolution atlas (recommended) |
| Park et al. (2018) | Mouse | 13 | First mouse kidney scRNA-seq atlas |
| Lake et al. / KPMP (2023) | Human | 40 | Kidney Precision Medicine Project |
| Zhang et al. (2021) | Human | 24 | Human kidney scRNA-seq |

## Usage

1. Upload your bulk RNA-seq data (CSV with gene names and CPM/counts)
2. Select a reference dataset
3. Choose gene set (all genes, kidney markers, or tubular markers)
4. Click "Match!" to run analysis

Results show correlation/distance to each reference cell type, with interactive heatmaps for gene expression visualization.

## Technical Details

Built with [Shinylive](https://posit-dev.github.io/shinylive/) - R Shiny apps compiled to WebAssembly via [webR](https://docs.r-wasm.org/webr/latest/).

First load takes 30-60 seconds to download the R runtime (~30MB). Subsequent visits are faster due to browser caching.

## References

- Ransick, A. et al. Single-Cell Profiling Reveals Sex, Lineage, and Regional Diversity in the Mouse Kidney. *Dev. Cell* 51, 399-413.e7 (2019). https://doi.org/10.1016/j.devcel.2019.10.005
- Park, J. et al. Single-cell transcriptomics of the mouse kidney reveals potential cellular targets of kidney disease. *Science* 360, 758-763 (2018). https://doi.org/10.1126/science.aar2131
- Lake et al. An atlas of healthy and injured cell states and niches in the human kidney. *Nature* 619, 585-594 (2023). https://doi.org/10.1038/s41586-023-05769-3
