# Single-Cell-RNA-Seq-Analysis-of-NSCLC-DTCs
## Overview
This repository contains the code and workflow for analyzing single-cell RNA sequencing (scRNA-seq) data from a 20k Mixture of NSCLC (Non-Small Cell Lung Cancer) Disseminated Tumor Cells (DTCs) dataset. The dataset, which represents samples from 7 donors, was generated using the 3' v3.1 chemistry and is sourced from 10x Genomics. The analysis was performed using the Seurat package in R, focusing on quality control, normalization, feature selection, dimensionality reduction, and clustering.

## Methodology
Data Loading: The analysis begins by loading the raw scRNA-seq data from an HDF5 file using the Read10X_h5 function. The data includes gene expression counts, which are used to initialize a Seurat object.

### Quality Control (QC)
Cells are filtered based on the number of detected features and mitochondrial gene content. QC metrics are visualized using violin and scatter plots to ensure data integrity.

### Data Normalization 
The raw counts are normalized using Seurat’s default normalization method to account for differences in sequencing depth across cells.

### Feature Selection 
Highly variable features are identified to focus on the most informative genes. This step involves selecting 2000 variable genes and visualizing them to understand their distribution.

### Scaling 
The data is scaled to adjust for differences in gene expression levels across cells, preparing it for dimensionality reduction.

### Dimensionality Reduction 
Principal Component Analysis (PCA) is performed to reduce the data’s dimensionality and identify the principal components that capture the most variance. An elbow plot is used to determine the optimal number of components.

### Clustering 
Cells are clustered using varying resolutions to identify distinct cell populations. The clustering results are visualized using UMAP (Uniform Manifold Approximation and Projection) for a non-linear representation of the data.

### Visualization
The final clusters are visualized using UMAP plots, which help in interpreting and analyzing the distinct cell groups within the dataset.

### Files and Directory Structure
scripts/: Contains R scripts for the analysis workflow.
data/: Includes the raw data files and any processed data.
results/: Stores output files, such as plots and analysis summaries.
### Usage
To replicate the analysis:

Clone the repository to your local machine.
Set the working directory to the scripts folder.
Ensure you have the required R packages installed (Seurat, tidyverse).
Run the provided R scripts to execute the analysis workflow.
### License
This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments
This analysis uses data provided by 10x Genomics. Special thanks to the research community for their contributions to single-cell transcriptomics.

