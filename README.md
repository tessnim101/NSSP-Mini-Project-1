# NSSP-Mini-Project-1

This repository contains a complete pipeline for preprocessing, statistical analysis, and clustering of fMRI data. The workflow is organized into three Jupyter notebooks, each covering a key stage of the analysis.

## 📁 Repository Structure
├── 01_preprocessing.ipynb # Structural & functional preprocessing
├── 02_glm.ipynb # GLM analysis and contrast computation
├── 03_kmeans.ipynb # Clustering analysis
└── README.md

---

## ⚙️ Pipeline Overview

### 1. Preprocessing (`01_preprocessing.ipynb`)

Performs structural and functional preprocessing:

- **Structural preprocessing**
  - Skull stripping (FSL BET)
  - Tissue segmentation (FSL FAST)

- **Functional preprocessing**
  - Load fMRI data
  - Variance normalization
  - Concatenate runs
  - Motion correction
  - Co-registration (EPI → anatomical using `epi_reg`)
  - Gaussian smoothing

**Notes:**
- A middle volume (e.g., scan 250) is used as a reference
- White matter segmentation improves alignment

---

### 2. GLM Analysis (`02_glm.ipynb`)

Implements a General Linear Model (GLM):

- Load preprocessed BOLD data
- Extract TR (repetition time)
- Load event timings
- Build design matrix
- Fit GLM
- Compute contrasts

**Main contrast:**
- Hand vs Foot (left/right hand vs left/right foot)

**Output:**
- Statistical maps with anatomical overlay (AAL atlas)

---

### 3. Clustering (`03_kmeans.ipynb`)

Applies unsupervised learning (K-means):

- Apply brain mask
- Evaluate optimal clusters using:
  - Silhouette Score
  - Calinski-Harabasz Index
  - Davies-Bouldin Index
  - Elbow method

**Result:**
- Optimal number of clusters: `k = 2`

Additional:
- Visualization of cluster centroids
- Pearson correlation similarity analysis

---

## 🧰 Requirements

- Python 3.x
- numpy
- scipy
- matplotlib
- nibabel
- nilearn
- scikit-learn
- FSL (BET, FAST, epi_reg)


   jupyter notebook
