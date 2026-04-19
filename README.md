# Classifying ADHD from Resting-State Functional Connectivity Using Machine Learning

## Overview

This repository presents a baseline computational neuroimaging pipeline to classify ADHD and control participants using resting-state fMRI functional connectivity features.

Using atlas-based ROI time series extracted from preprocessed scans, subject-level connectivity matrices were converted into machine learning features and evaluated using cross-validated classification models.

The project emphasizes transparent reporting, reproducibility, and critical interpretation of results in small-sample clinical neuroimaging.

---

## Research Question

Can ROI-level resting-state functional connectivity distinguish ADHD participants from controls in a lightweight public dataset subset?

---

## Dataset

* Nilearn ADHD resting-state fMRI dataset
* 20 processed subjects
* ADHD and control labels available
* Publicly accessible through Python

---

## Methods

### 1. Data Preparation

* Downloaded public ADHD resting-state fMRI data
* Extracted diagnosis labels and participant metadata

### 2. ROI Time-Series Extraction

* Harvard-Oxford cortical atlas
* Regional mean signal extraction

### 3. Functional Connectivity

* Pearson correlation matrices generated for each subject

### 4. Feature Engineering

* Upper triangle of connectivity matrices used as model features

### 5. Classification

* Logistic Regression baseline model
* Stratified 5-fold cross-validation

### 6. Evaluation

* Accuracy
* ROC-AUC
* Confusion Matrix
* Precision / Recall / F1-score

---

## Results

Cross-validated evaluation revealed strong rank-order class discrimination but poor threshold-based classification:

* Accuracy: 0.20
* ROC-AUC: 0.96

This contrast illustrates how classification accuracy alone can be misleading and why threshold-independent metrics such as ROC-AUC are important in imbalanced or clinically noisy datasets.

---

## Interpretation

This negative result is informative and reflects common challenges in clinical neuroimaging machine learning:

* Small sample sizes
* High-dimensional feature spaces
* Dataset heterogeneity
* Motion and preprocessing confounds
* Diagnostic label complexity
* Need for stronger feature selection and model tuning

---

## Repository Structure

```text id="1nqg5e"
repo3-adhd-classification/
│── notebooks/
│   ├── 01_download_labels.ipynb
│   ├── 02_connectivity_features.ipynb
│   └── 03_classification.ipynb
│
│── data/
│── figures/
│── results/
│── README.md
```

---

## Future Directions

* Larger balanced cohorts
* Feature selection pipelines
* SVM / ensemble classifiers
* Site harmonisation
* Motion confound control
* External validation datasets
* Explainable AI approaches

---

## Skills Demonstrated

* Python for scientific computing
* Neuroimaging analysis with Nilearn
* Functional connectivity workflows
* Clinical machine learning pipelines
* Cross-validation and model evaluation
* Transparent scientific reporting

---

## Author

Aditya Sundaray

Computational neuroscience portfolio project for PhD/research applications.
