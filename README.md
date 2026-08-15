# SingleCell-PRISM: Light-Chain-Only Plasma-Cell Clones in AL Amyloidosis

## ⚠️ Disclaimer

The accompanying manuscript has not yet finished peer review. This repository is provided for research and reproducibility purposes only. The code and results should not be used independently to guide clinical diagnosis, prognosis, or treatment decisions.

<img width="191" height="191" alt="image" src="https://github.com/user-attachments/assets/a802e6d8-9e6f-4687-a449-267c70658ab7" />

This repository contains the analysis code accompanying the submitted manuscript:

**Loss of Productive IgH in Plasma Cell Clones Underlies a Cardiac High-Risk Phenotype in AL Amyloidosis**

**Authors:** Xuezhu Wang, Xinyi Xiong, Chengyang Xu, Yi Xu, Hongxiao Han, Ai Guan, Yajuan Gao, Jian Li, and Kaini Shen.

The study integrates single-cell transcriptomics and paired B-cell receptor sequencing to characterize plasma-cell clones with loss of productive immunoglobulin heavy-chain expression, examine their isotype and light-chain composition, relate immunoglobulin status to transcriptional state and developmental potential, and evaluate the depth and saturation of heavy-chain repertoire detection.

## ✨ Overview

Systemic light-chain (AL) amyloidosis is driven by clonal plasma cells that produce amyloidogenic immunoglobulin light chains. Although plasma cells normally synthesize both heavy and light immunoglobulin chains, some amyloidogenic clones may lack detectable productive IgH while retaining disease-associated light-chain expression.

This repository contains focused analyses of:

1. **Integration of scRNA-seq and scBCR-seq data**
2. **Assignment of productive IgH status and plasma-cell clonotypes**
3. **Immunoglobulin isotype and chain-status composition**
4. **Relationships between IgH/IgK/IgL status and plasma-cell transcriptional state**
5. **CytoTRACE-based assessment of developmental potential**
6. **Heavy-chain repertoire saturation and sequencing-depth evaluation**

Together, these workflows support investigation of light-chain-only plasma-cell biology and its relationship to clinically cardiac high-risk AL amyloidosis.

## 🔬 Analysis Modules

### 1. Heavy-chain clonotype integration

The primary workflow matches scBCR-seq libraries to scRNA-seq cells, evaluates barcode overlap, assigns productive heavy-chain clonotypes, and integrates IgH status with plasma-cell programs and clinical annotations.

### 2. Isotype and chain-status analysis

Dandelion-based repertoire analysis summarizes:

- Productive heavy- and light-chain detection
- Immunoglobulin isotype composition
- Clonotype-specific chain-status distributions
- Joint clonotype, isotype, and chain-status patterns

### 3. Developmental-potential analysis

CytoTRACE-related analyses connect IgH, IgK, and IgL status with plasma-cell differentiation state, transcriptional programs, unfolded-protein-response features, and disease-associated light-chain expression.

### 4. Heavy-chain repertoire saturation

Repeated subsampling of V(D)J contigs evaluates whether sequencing depth adequately captures the observed productive IgH repertoire and clone diversity within each sample.

## 📁 Notebook Descriptions

| Notebook | Description |
|---|---|
| `1.1_plasmacellcloneVDJ-IgH.ipynb` | Matches scBCR-seq to scRNA-seq, assigns productive IgH clonotypes, and relates heavy-chain status to plasma-cell programs and clinical groups. |
| `1.2_dandelion-isotype.ipynb` | Builds Dandelion repertoire objects and summarizes clonotype-specific isotype and chain-status composition. |
| `1.3_cytotrace_IgHIgKIgL.ipynb` | Integrates IgH, IgK, and IgL metadata with single-cell data and compares immunoglobulin status with CytoTRACE-related plasma-cell states. |
| `1.4_IgHsaturationcurve.ipynb` | Uses repeated V(D)J-contig subsampling to generate sample-level heavy-chain repertoire saturation curves. |

## 🧰 Major Software Dependencies

The repository contains both R- and Python-based analyses. Major dependencies are summarized below.

### R workflows

- **Single-cell analysis:** Seurat, SingleCellExperiment, DropletUtils, celda, and scCustomize
- **Reference-based annotation and data conversion:** SingleR, celldex, sceasy, and reticulate
- **Differential and statistical analysis:** limma, speckle, rstatix, and ggpubr
- **Data manipulation and visualization:** dplyr, tidyr, tibble, tidyverse, ggplot2, patchwork, pheatmap, VennDiagram, and scales

### Python workflows

- **Single-cell data structures and analysis:** Scanpy and AnnData
- **B-cell receptor repertoire analysis:** Dandelion
- **Trajectory and developmental-potential analysis:** scVelo and CytoTRACE-related workflows
- **Scientific computing and statistics:** pandas, NumPy, SciPy, and statsmodels
- **Visualization:** Matplotlib

## 📊 Reproducibility

Each notebook documents its biological rationale, aim, expected inputs, workflow sections, and principal outputs. The notebooks use relative or `/home/`-based paths rather than institution-specific storage locations.

Reproduction requires alignment of cell-barcode conventions across scRNA-seq and scBCR-seq data. Particular attention should be paid to sample prefixes, 10x barcode suffixes, clonotype identifiers, productive-chain definitions, and duplicate contig handling.

## 📖 Citation

When using this repository or its analytical workflow, please cite the associated manuscript:

**Wang X, Xiong X, Xu C, Xu Y, Han H, Guan A, Gao Y, Li J, Shen K.** Loss of Productive IgH in Plasma Cell Clones Underlies a Cardiac High-Risk Phenotype in AL Amyloidosis.

Formal journal, year, DOI, and BibTeX information should be added when available.

## 📄 License

This project is licensed under the [MIT License](LICENSE).
