# 🧬 Mapping the Chemical Landscape of GLP-1R Compounds
### *Unsupervised Learning for Drug-Likeness Profiling*

## 📌 Project Overview
This project applies unsupervised machine learning to characterize the chemical space of **Glucagon-like peptide-1 receptor (GLP-1R)** and **EGFR** ligands. By analyzing 500 drug compounds from the ChEMBL database, the study identifies natural structural groupings and "drug-like" niches without relying on pre-defined labels.

The goal is to understand how physicochemical properties like lipophilicity, size, and polarity influence the clinical progression (`Max Phase`) of these therapeutic candidates.

## 📊 Dataset Description
The dataset contains 500 compounds with 14 variables, including:
* **Physicochemical Descriptors:** Molecular Weight, AlogP (Lipophilicity), Polar Surface Area (PSA), HBA, HBD, and #Rotatable Bonds.
* **Quality Metrics:** QED Weighted (Drug-likeness), #RO5 Violations, and Np Likeness Score.
* **Biological Metadata:** Bioactivities and Max Phase (Clinical trial stage).

## 🛠️ Technical Workflow

### 1. Data Preprocessing & EDA
* **Feature Scaling:** Applied `StandardScaler` to handle features with vastly different magnitudes (e.g., Molecular Weight vs. HBD).
* **Correlation Analysis:** Generated a heatmap to identify redundant features, such as the high correlation between Molecular Weight and Heavy Atom count.

### 2. Dimensionality Reduction
* **PCA (Principal Component Analysis):** Reduced high-dimensional chemical data into two principal components for visualization, capturing the primary drivers of molecular diversity.

### 3. Unsupervised Clustering
* **K-Means Clustering:** Implemented the Elbow Method to determine the optimal number of clusters ($K=5$).
* **Cluster Profiling:** * **Cluster 0:** Polar Scaffolds (High HBA).
    * **Cluster 1:** Heavyweights (High Mass/Size).
    * **Cluster 2:** Bio-inspired (High NP Likeness).
    * **Cluster 3:** Small Fragments (High Lipophilicity).
    * **Cluster 4:** Clinical Successes (Highest QED and Max Phase).

## 🚀 Key Insights
* **The "Sweet Spot":** Cluster 4 was identified as the most "drug-like" region, containing a high density of compounds that reached advanced clinical phases.
* **Redundancy:** Statistical analysis confirmed that structural size (Heavy Atoms/MW) is a dominant differentiator in this ligand library.
* **Interpretability:** The model successfully grouped compounds with similar therapeutic potential based purely on their structural descriptors.

