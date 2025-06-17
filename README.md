# 🌱 PML Final Project — Crop Recommendation with Machine Learning

### Project Category: Tabular Data (Multi-Class Classification)  
**Student Name:** Luís Pinto Coelho  
**Student ID:** 19724  
**Course:** MSc in Green Data Science  
**Professor:** Manuel Lameiras de Figueiredo Campagnolo  
**Institution:** Instituto Superior de Agronomia, Universidade de Lisboa  

---

## 🧠 Problem Statement

Agricultural productivity is highly dependent on choosing crops suited to specific soil characteristics. Farmers often base crop selection on heuristics or past experience, which can result in inefficient land use and lower yields. 

This project develops a **machine learning-based decision support system** to recommend the most suitable crops based on key soil metrics: **nitrogen (N)**, **phosphorous (P)**, **potassium (K)**, and **pH**. The tool is aimed at improving agricultural decision-making, particularly for small-scale farmers, by reducing guesswork and promoting more sustainable land use.

---

## ⚠️ Challenges

- **Multi-class classification with 22 crop classes**, increasing the complexity of model generalization.
- **Low feature dimensionality** (only 4 inputs), limiting the information available for discrimination.
- **Overlapping soil profiles**: different crops may thrive in similar conditions, introducing ambiguity.
- **Dataset limitation**: each sample is labeled with only one "optimal" crop, while in reality, multiple crops may be suitable — an issue addressed through probabilistic prediction.
- **Model explainability**: interpretability is crucial for practical adoption by end users.

---

## 📊 Dataset

The project uses the [`soil_measures.csv`](https://www.kaggle.com/datasets/mohamedmostafa259/soil-measures) dataset from Kaggle, containing **2200 samples** with features: `n`, `p`, `k`, `ph`, and the target label `crop`.

The dataset is clean, balanced (100 samples per crop), and well-suited for classification tasks. Preprocessing steps include column normalization, outlier detection, and label encoding. No missing values were found. The data was retrieved using the `kagglehub` package.

---

## 🛠️ Method or Algorithm

### Preprocessing:
- Encode target using `LabelEncoder`
- Normalize features (`StandardScaler`)
- Stratified train-test split (80/20)

### Modeling:
- Models tested: 
  - Logistic Regression (with and without polynomial features)
  - K-Nearest Neighbors
  - Support Vector Machine (RBF kernel)
  - Random Forest
  - Hard Voting Ensemble (majority vote)
  - **Soft Voting Ensemble** (for suitability distribution)

- All pipelines built using `scikit-learn`

### Optimization:
- 5-fold Cross-Validation on final model
- Permutation Feature Importance
- Bootstrap analysis for confidence intervals

---

## 📏 Evaluation

The models were assessed using:
- **Accuracy** and **Macro F1 Score**
- **Confusion Matrix** (raw and normalized)
- **Learning Curves**
- **Cross-validation mean ± std**
- **Bootstrap CI for accuracy**
- **Suitability distribution** via `predict_proba` to reflect crop versatility

This multifaceted evaluation framework ensures model robustness and interpretability, addressing both technical performance and agricultural relevance. The final model — a Voting Classifier — is saved with a custom prediction function and a suitability explorer for top crop recommendations.

Files in the repositoy:

pml_final_project.ipynb – Jupyter Notebook containing all the code related to model development, along with the final report.

