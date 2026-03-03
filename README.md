# Unsupervised Learning Grouping of Dementia Patterns

This project uses machine learning to find hidden groups in a dataset of 2,149 patients. 

---

## Project Overview
I wanted to see if a clustering algorithms could find different "types" of dementia on its own, without being told the results.

### Data Dimensions
I grouped the data into three main categories:
* **Lifestyle**: BMI, smoking, drinking, and how much someone exercises or eats well.
* **Clinic Tests**: Memory test scores (MMSE) and how well someone handles daily chores.
* **Symptoms**: Problems with memory, mood, or getting confused.

### K-Means Clustering
<img width="904" height="668" alt="K-Means" src="https://github.com/user-attachments/assets/1c90b0ec-c157-4be9-9cb9-8aa740c9aa66" />
<img width="844" height="547" alt="K-Means in 2d Space" src="https://github.com/user-attachments/assets/bcd920ff-ab6e-4d55-8361-56e0d8a08722" />

### Gaussian Mixture Models
<img width="789" height="528" alt="Guassian Mixture Models" src="https://github.com/user-attachments/assets/8b1ab9b5-dbdb-415f-8733-79c3ebe19d48" />

### Agglomerative Clustering Dendrogram
<img width="1229" height="571" alt="Agglomerative Clustering Dendrogram" src="https://github.com/user-attachments/assets/c72ffbe6-5d6f-4040-83cb-1970c0a5ba44" />

---

## Findings

### 1. Discovery of Three Distinct Phenotypes
The unsupervised K-Means clustering revealed three stable patient profiles:
* **Cluster 0:** Characterised by the lowest levels of physical activity and diet quality. In this group, physical decline is the primary marker of the phenotype.
* **Cluster 1:** Despite maintaining higher functional and physical activity scores, this group exhibited the most frequent behavioral disturbances (e.g., agitation and mood changes).
* **Cluster 2:** A group where high diet quality persists despite significant cognitive impairment, suggesting decline driven by factors beyond lifestyle habits.

### 2. Identifying "Hidden" Progression
The clusters revealed deeper biological layers that traditional diagnostic labels sometimes miss:
* **Pre-Symptomatic Signatures:** While Cluster 1 had the highest concentration of Alzheimer’s cases (36.2%), the remaining "healthy" individuals in that group may represent patients at risk; those displaying behavioral markers before their cognitive scores drop enough for a formal diagnosis.
* **Anosognosia Awareness:** Patients in Cluster 0 (higher MMSE) reported more memory complaints than those in the more advanced Cluster 2. This aligns with the clinical phenomenon where patients lose the ability to recognize their own decline as the disease worsens.

<img width="850" height="542" alt="K-Means Comparison" src="https://github.com/user-attachments/assets/2ac90d04-72b8-4f50-b9c3-71512d3eabd7" />

### 3. Model Stability and Validation
To ensure the findings were robust, the project triangulated three different mathematical paradigms:
* **K-Means & Gaussian Mixture Models (GMM):** Both models showed nearly 100% certainty in patient assignment, creating highly distinct clusters in high-dimensional space.
* **Hierarchical Clustering:** The resulting Dendrogram confirmed that the most fundamental split in the data is between healthy and advanced disease states, while identifying smaller sub-variations within the dementia population.

<img width="1282" height="470" alt="K-Means vs Hierarchical" src="https://github.com/user-attachments/assets/2227ccfe-2a2b-4caa-9988-5a8228fc4ae4" />

---

## Technical Approach
The project follows a data science pipeline:
* **Feature Engineering:** Grouping variables into multi-modal categories for structured analysis.
* **Dimensionality Reduction:** Utilising PCA and UMAP to project complex 13D data into 2D maps for visual interpretation.
* **Clustering Triangulation:** Comparing Centroid-based (K-Means), Distribution-based (GMM) and Connectivity-based (Hierarchical) methods to ensure results are algorithm-independent.

---

## Dataset
The analysis was performed on the [Alzheimer's Disease Dataset](https://www.kaggle.com/datasets/rabieelkharoua/alzheimers-disease-dataset) by Rabie El Kharoua. This is an extensive dataset containing health information for 2,149 patients, generated for educational and research purposes.

## References
* [1] **Standardised Mini-Mental State Examination (SMMSE)**: Guidelines for cognitive impairment categories.
* [2] **National Library of Medicine**: Clinical definitions of Anosognosia.
* [3] **PMC Research**: Early diagnosis of Alzheimer’s disease using machine learning.
* [4] **Dataset**: Rabie El Kharoua (2024). Alzheimer's Disease Dataset.
