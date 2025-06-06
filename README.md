# Project Proposal: *Learning What to Grow – Crop Classification from NPK and pH Levels*

**Author:** Luís Pinto Coelho  
**Student No.:** 19724  
**Course:** Machine Learning – Mestrado em Green Data Science  
**Academic Year:** 2024/2025

---

## 🧠 What is the goal of your project?

To build a multi-class machine learning model that helps farmers determine the optimal crop to grow in a given field based on easily measurable soil metrics: **Nitrogen (N)**, **Phosphorous (P)**, **Potassium (K)**, and **pH**.

This tool aims to **automate and simplify decision-making** for farmers, promoting **data-driven agriculture** that maximizes yield and resource efficiency.

---

## 🌱 Why is it important?

- **Soil testing is expensive**: Farmers may not afford to measure many variables.
- **Crop selection is critical**: Wrong decisions lead to poor yield and economic loss.
- This tool contributes to **precision farming**, sustainability, and **optimised land usage**.

---

## 📦 What dataset are you using?

- **Source**: Kaggle → [`mohamedmostafa259/soil-measures`](https://www.kaggle.com/datasets/mohamedmostafa259/soil-measures)
- **Format**: Tabular CSV
- **Features**:
  - `N`, `P`, `K` — soil nutrient levels
  - `pH` — soil acidity
  - `crop` — optimal crop label (22 classes)

---

## 🔍 What challenges do you expect?

1. **Multi-class classification** with 22 different crop types.
2. **Small number of features** (only 4), making high accuracy difficult.
3. **Potential overlap** between crop preferences.
4. **Need for interpretability** in real-world decision support.

---

## 🔧 How will you build the solution?

### 🧼 Data Preparation
- Clean and validate column names
- Encode target (`crop`) using `LabelEncoder`
- Stratified train-test split (80/20)
- Use `StandardScaler` when needed

### 🤖 Models Compared
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Random Forest
- Support Vector Machine (SVM)

### 🛠️ Model Pipeline
- Modular `sklearn.pipeline.Pipeline` architecture
- Hyperparameter tuning with `GridSearchCV` for Random Forest
- Best model saved with `joblib`

---

## 📊 How will you evaluate it?

### Metrics:
- Accuracy
- Macro F1 Score
- Confusion Matrix (Raw + Normalized)
- Cross-validation (CV=5)
- Learning Curves
- **Permutation Feature Importance**

### Note:
> Advanced interpretability techniques like **SHAP** were considered but ultimately not used in the final version due to compatibility issues and limited feature complexity.

---

## ✅ What results do you expect?

- Achieve classification accuracy **above 90%**, as dataset is clean and balanced.
- Confirm **key predictive variable** (likely Nitrogen or pH).
- Deliver a **fully functional prototype** for crop recommendation from soil input.

---

## 📁 Deliverables

- Python notebook + script
- Trained model (`.pkl`) and label encoder
- Report (PDF)
- `README.md` for GitHub with visualizations and demo predictions

---

## 🏁 Final Model Summary

- Best model: **Random Forest Classifier**
- Accuracy: ~**0.96**
- Interpretation: **Permutation Feature Importance**
- Deployment-ready function: `predict_crop(n, p, k, ph)`

---
