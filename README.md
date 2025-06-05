# Learning What to Grow: Crop Classification from NPK and pH Levels

### Created by: Luís Pinto Coelho (19724)

### Professor Manuel Campagnolo

### MSc in Green Data Science, ISA, Portugal

---

## Project Proposal – Practical Machine Learning 2024/2025

### Project category: Tabular Data – Multi-class Classification

---

### Problem Statement

Farmers often struggle to determine which crop to plant in a given season due to limited access to soil analysis tools. Understanding the chemical composition of soil—namely nitrogen (N), phosphorous (P), potassium (K), and pH—can greatly influence the success of agricultural production. However, such data is costly to collect at scale. This project aims to use machine learning to predict the most suitable crop based on these four key soil parameters, enabling more sustainable and data-driven decisions in agriculture. By learning from existing labeled soil profiles, the model can support efficient and ecologically conscious crop planning.

---

### Challenges

1. **Limited feature set**: With only four input variables, the model must be effective without rich context.
2. **Class imbalance**: The dataset contains multiple crop categories with varying frequency.
3. **Generalization**: Ensuring the model can generalize to new, unseen soil profiles.
4. **Interpretability**: Making the model's reasoning accessible to non-technical users, such as farmers or agronomists.

---

### Dataset

The project uses the [Soil Measures Dataset](https://www.kaggle.com/datasets/mohamedmostafa259/soil-measures) from Kaggle. It includes 1985 soil samples with the following columns:

* `N`: Nitrogen content ratio in the soil
* `P`: Phosphorous content ratio
* `K`: Potassium content ratio
* `pH`: Acidity level of the soil
* `crop`: Label indicating the optimal crop (target variable)

This dataset is publicly available and sufficiently annotated for supervised classification tasks.

---

### Method or Algorithm

The methodology includes:

* Data cleaning, outlier detection (via Z-score), and encoding
* Feature scaling and splitting with stratified train/test partitions
* Model development using:

  * Logistic Regression (linear and polynomial)
  * Support Vector Machine (SVM)
  * K-Nearest Neighbors (KNN)
  * Random Forest
  * Ensemble Voting Classifier
* Hyperparameter tuning and cross-validation

The best model will be selected based on evaluation performance and deployed in a prediction function.

---

### Evaluation

Models will be evaluated using:

* **Accuracy** and **macro-averaged F1-score**
* **Confusion matrices** (both raw and normalized)
* **Cross-validation** (5-fold)
* **Bootstrap resampling** to compute 95% confidence intervals
* **Learning curves** to assess generalization behaviour
* **Feature importance** using permutation methods and SHAP

This evaluation ensures that the model is both robust and interpretable.


