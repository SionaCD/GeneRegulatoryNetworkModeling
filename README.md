# 🧬 Single-Cell RNA Velocity Analysis of Mock Epithelium

A comprehensive single-cell RNA sequencing analysis pipeline for studying epithelial cell dynamics using RNA velocity and lineage inference methods.

## 📖 Overview

This repository contains a complete pipeline for analyzing single-cell RNA-seq data from mock epithelial tissue, focusing on:

- **Cell type identification** and annotation using marker genes
- **RNA velocity analysis** to infer cellular dynamics and future states
- **Lineage inference** to map developmental trajectories
- **Driver gene identification** for each cell type

The analysis integrates multiple state-of-the-art tools including Scanpy, scVelo, and CellRank to provide comprehensive insights into epithelial cell biology.

## 🛠️ Pipeline Features

### Core Analysis
- ✅ **Quality Control**: Cell/gene filtering, mitochondrial content analysis
- ✅ **Preprocessing**: Normalization, HVG selection, dimensionality reduction
- ✅ **Clustering**: Leiden algorithm with PAGA graph abstraction
- ✅ **Cell Annotation**: Marker-based identification of epithelial cell types
- ✅ **RNA Velocity**: Dynamical modeling of transcriptional dynamics
- ✅ **Lineage Inference**: Initial/terminal state prediction and fate mapping

### Cell Types Identified
- 🔬 **Stem Cells**: Lgr5⁺, Smoc2⁺, Axin2⁺
- 🔄 **TA Cells**: Hmgn2⁺, Ccna2⁺, Mcm5⁺ (Transit-Amplifying)
- 🧱 **Enterocytes**: Cdhr2⁺, Fabp2⁺, Aqp8⁺
- 🫧 **Goblet Cells**: Muc2⁺, Zg16⁺, Atoh1⁺
- ⚡ **EEC Cells**: Insm1⁺, Pax6⁺ (Enteroendocrine)


## 🚀 Quick Start

### Prerequisites
- Python 3.9+
- Conda or Mamba (recommended)
- 8GB+ RAM recommended


### Run in Google Colab
📓 **[Open in Google Colab](https://colab.research.google.com/drive/1PAzsg8FP403Sk-Pm3cYIXrDCsTu3-WU3?usp=sharing)**



## 📊 Key Outputs

### Visualizations
- 🎯 Quality control metrics and filtering plots
- 🗺️ UMAP embeddings colored by cell types and marker genes
- ➡️ RNA velocity vector fields and stream plots
- ⏰ Latent time progression maps
- 🎲 Fate probability heatmaps

### Data Files
- `adata.h5ad`: Complete processed AnnData object
- `potenial_driver.csv`: Top 100 likelihood genes per cell type
- `cluster_differential_velocity.csv`: Velocity-correlated genes

## 🔬 Methodology

### Data Processing
1. **Quality Control**: Filter cells (<200 genes) and genes (<3 cells)
2. **Normalization**: Library size normalization + log transformation
3. **Feature Selection**: Highly variable genes (4,515 genes selected)
4. **Batch Correction**: Total count regression

### RNA Velocity Analysis
- **Model**: scVelo dynamical model for full transcriptional dynamics
- **Integration**: Merge spliced/unspliced count matrices
- **Inference**: Velocity vectors and latent time computation

### Lineage Analysis
- **Terminal States**: EC2, EEc, GC (CellRank identification)
- **Initial States**: Stem cells
- **Fate Mapping**: Transition probabilities for each cell


## 📚 References

- **scVelo**: Bergen, V. et al. Generalizing RNA velocity to transient cell states through dynamical modeling. *Nature Biotechnology* 38, 1408–1414 (2020).
- **CellRank**: Lange, M. et al. CellRank for directed single-cell fate mapping. *Nature Methods* 19, 159–170 (2022).
- **Scanpy**: Wolf, F.A. et al. SCANPY: large-scale single-cell gene expression data analysis. *Genome Biology* 19, 15 (2018).


---

⭐ **Star this repository if you found it helpful!**
