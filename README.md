# NSSP-Mini-Project-1

This repository contains a complete pipeline for preprocessing, statistical analysis, and clustering of fMRI data. The workflow is organized into three Jupyter notebooks, each covering a stage of the analysis.

## Pipeline Description

**Preprocessing (`01_preprocessing.ipynb`)**  
Includes structural and functional preprocessing steps: skull stripping (FSL BET), tissue segmentation (FSL FAST), motion correction, co-registration of functional to anatomical images (EPI→T1), normalization, and spatial smoothing. The outputs of this stage are used in all subsequent analyses.

**GLM Analysis (`02_glm.ipynb`)**  
Implements a voxel-wise General Linear Model using experimental event timings. The notebook constructs a design matrix, fits the model to the BOLD signal, and computes statistical contrasts, including a comparison between hand and foot motor conditions. Results are visualized as statistical maps over anatomical references.

**Clustering (`03_kmeans.ipynb`)**  
Applies K-means clustering to preprocessed fMRI data within a brain mask. The number of clusters is determined using standard evaluation metrics (silhouette score, Calinski–Harabasz index, Davies–Bouldin index, and elbow method), leading to an optimal solution of *k = 2*. Cluster centroids and similarity measures are analyzed for interpretation.

## Requirements

- Python 3.x  
- `numpy`, `scipy`, `matplotlib`  
- `nibabel`, `nilearn`, `scikit-learn`  
- FSL (BET, FAST, epi_reg)

## Usage

Run the notebooks in order:

1. `01_preprocessing.ipynb`  
2. `02_glm.ipynb`  
3. `03_kmeans.ipynb`

Ensure that FSL is properly installed and environment variables are configured. File paths may need to be adapted to your system.

## License

This project is intended for academic use.
