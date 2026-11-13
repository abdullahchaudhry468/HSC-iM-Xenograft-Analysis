# HSC-iM xenograft analysis

This project explores HSC and HSC-II cells from the xenograft data in *Human haematopoietic stem cells remember inflammatory stress* (Zeng, Nagree et al., 2026).

Focus: Whether the two published cell populations could be distinguished using RNA expression and chromatin accessibility data. This is a **partial reproduction** of the study's computational analysis.

## What I did

- **RNA:** Used the deposited 10x gene-expression counts for 5,976 cells labeled HSC or HSC-II. I normalized the counts, selected variable genes, and ran PCA, clustering and UMAP using Scanpy.
- **RNA markers:** Compared gene expression between the published HSC and HSC-II groups using a Wilcoxon test to identify genes that differed between the populations.
- **ATAC:** Used the authors' processed ATAC LSI features for the same 5,976 cells and recalculated clusters and a UMAP.
- **Comparison:** Matched cells across the two analyses by barcode and compared the resulting clusters with the published HSC/HSC-II labels.

## Main results

The RNA analysis gave me **seven clusters**, while the ATAC analysis gave me **four**. Both showed a noticeable difference between the HSC and HSC-II populations identified in the original study. These clusters don't necessarily mean there are different cell types, but they do suggest there are differences within the populations.

I also looked at which genes were expressed differently between HSC and HSC-II. This was more of an initial comparison, since I looked at the cells individually rather than accounting for differences between donors.

## Scope and limitations

The original **HSC/HSC-II annotations were used to select the cells**. They were not supplied to the RNA or ATAC clustering algorithms, but were used afterward for comparison. The annotations were also used to group cells for the RNA marker analysis. The ATAC LSI features, published cell labels, and the published WNN UMAP came from the study's authors.

## Sources

- Zeng, Nagree et al. (2026), *Human haematopoietic stem cells remember inflammatory stress*, [Nature](https://doi.org/10.1038/s41586-026-10522-7).
- [Published code and data (Zenodo)](https://doi.org/10.5281/zenodo.18850871).

