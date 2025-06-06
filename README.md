# 🌱 PML Final Project — Crop Recommendation with Machine Learning

### Project Category: Tabular Data (Multi-Class Classification)  
**Student Name:** Luís Pinto Coelho  
**Student ID:** 19724  
**Course:** MSc in Green Data Science  
**Professor:** Manuel Lameiras de Figueiredo Campagnolo  
**Institution:** Instituto Superior de Agronomia, Universidade de Lisboa  

---

## 🧠 Problem Statement

Agricultural success depends heavily on choosing the right crop for a given field, which in turn is influenced by soil nutrient content and chemical balance. Farmers often rely on experience or trial-and-error to guide crop decisions, but this can lead to inefficiencies or reduced yield. 

In this project, we aim to develop a **machine learning model** capable of recommending the most suitable crop for a given field, based on basic soil measurements: **nitrogen (N)**, **phosphorous (P)**, **potassium (K)**, and **pH**. This type of decision support system can improve productivity, reduce uncertainty, and support more sustainable agricultural practices, especially for smallholder farmers with limited technical expertise.

---

## ⚠️ Challenges

- **Multi-class complexity**: The dataset includes **22 crop types**, which increases the classification difficulty.
- **Low feature dimensionality**: Only 4 numeric features are available, which places higher demand on model selection and feature engineering.
- **Ambiguity**: Similar soil profiles may correspond to multiple viable crops, introducing uncertainty in decision boundaries.
- **Interpretability**: Providing transparent and explainable recommendations is critical for trust and usability.

---

## 📊 Dataset

We use the publicly available [`soil_measures.csv`](https://www.kaggle.com/datasets/mohamedmostafa259/soil-measures) dataset from Kaggle. It includes **1988 samples**, each with soil measurements (`n`, `p`, `k`, `ph`) and a corresponding optimal crop label (`crop`). 

The dataset is balanced and clean, requiring only minor preprocessing (standardization of column names, label encoding). Data was downloaded via `kagglehub`.

---

## 🛠️ Method or Algorithm

1. **Preprocessing**: 
   - Clean column names
   - Encode categorical target using `LabelEncoder`
   - Normalize input features using `StandardScaler`
   - Train/test split (80/20) with stratification

2. **Model Training**:  
   - Compare multiple models: Logistic Regression, K-Nearest Neighbors, SVM, Random Forest  
   - Integrate each into a `sklearn.pipeline` for clarity and reproducibility

3. **Tuning & Optimization**:  
   - GridSearchCV for hyperparameter tuning (Random Forest)  
   - 5-fold cross-validation  
   - Feature importance via Permutation Importance

---

## 📏 Evaluation

We will use the following metrics to assess performance:
- **Accuracy**
- **Macro F1 Score**
- **Confusion Matrix** (raw and normalized)
- **Learning Curves**
- **Cross-validation scores** (mean ± std)

This evaluation strategy provides both quantitative performance and qualitative insight into model behavior. The final model will be saved using `joblib` and include a prediction function for new soil samples.

---

