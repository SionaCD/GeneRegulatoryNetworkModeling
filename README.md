# 🧬 Mock Epithelium Analysis with RNA Velocity

This notebook presents a comprehensive single-cell RNA-seq analysis pipeline for epithelial cells, integrating **Scanpy**, **scVelo**, **CellRank**, and **Velorama** to explore gene expression dynamics and lineage trajectories in mock epithelial tissue.

---

## 📌 Overview

The pipeline performs:

- **Preprocessing & QC**: Cell/gene filtering, normalization, and mitochondrial content analysis.
- **Dimensionality Reduction & Clustering**: PCA, UMAP, Leiden clustering, PAGA graph abstraction.
- **Cell Type Annotation**: Marker-based annotation for stem, TA, enterocyte, goblet, and EEC cells.
- **RNA Velocity Estimation**: Using the dynamical model in `scVelo` to infer future cell states.
- **Lineage Inference**: Leveraging `CellRank` for initial/terminal state prediction and fate probabilities.
- **Driver Gene Identification**: Ranking genes via transcriptional likelihood and velocity correlation.
- **Velorama (WIP)**: Attempted integration to model regulatory gene influences across dynamic lineages.

---

## 🧪 Key Tools & Libraries

- [`scanpy`](https://scanpy.readthedocs.io)
- [`anndata`](https://anndata.readthedocs.io)
- [`scvelo`](https://scvelo.readthedocs.io)
- [`cellrank`](https://cellrank.org)
- [`episcanpy`](https://github.com/colomemaria/episcanpy)
- [`velorama`](https://github.com/berenslab/velorama) *(experimental)*

---

## 📂 Dataset

- **Input**: 10x Genomics-style filtered matrix (`matrix.mtx`, `features.tsv`, `barcodes.tsv`)
- **Additional**: Loom file containing unspliced/spliced matrices for RNA velocity
- **Outputs**: Processed data saved as `adata.h5ad` and `Mock.h5ad`

---

## 🔁 Workflow

1. **Load and preprocess matrix with Scanpy**
2. **Filter cells/genes and normalize**
3. **Identify HVGs, regress out technical factors**
4. **Embed with PCA & UMAP, cluster with Leiden**
5. **Visualize and annotate clusters using known markers**
6. **Integrate with RNA velocity loom file**
7. **Compute velocities and latent time with `scVelo`**
8. **Use `CellRank` to infer fates and map lineage transitions**
9. **Rank potential driver genes for each annotated type**
10. **(Optional)** Test Velorama for gene regulatory inference

---

## 📈 Outputs

- Clustered UMAPs annotated by marker genes and cell types
- RNA velocity vector fields and stream plots
- Latent time plots and fate maps
- Ranked driver genes saved as `.csv` files
- Preprocessed `.h5ad` files for reproducibility

---

## 🚧 Notes

- The notebook was originally run in **Google Colab** and assumes mounting of Google Drive for file access.
- `Velorama` integration is exploratory and requires proper CLI argument setup.

---

