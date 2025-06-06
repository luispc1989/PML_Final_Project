# PML Final Project – Learning What to Grow: Crop Classification from NPK and pH Levels
### Created by: Luís Pinto Coelho (19724)  
### Professor Manuel Lameiras de Figueiredo Campagnolo  
### MSc in Green Data Science, ISA, Portugal  

---

**Project category:** Multiclass classification (Tabular data)

---

## Information

---

### 🔎 Problem Statement: What problem will you be investigating? Why is it interesting?

This project tackles the problem of identifying the most suitable crop for a given field based on basic soil characteristics: nitrogen (N), phosphorus (P), potassium (K), and pH level. These are essential indicators of soil fertility, but measuring them can be costly and time-consuming. A machine learning solution to this problem can help farmers select the ideal crop to grow, optimizing yield and minimizing environmental impact.

This challenge is both practical and relevant. It supports more informed, data-driven decision-making in agriculture while reducing dependency on extensive lab analysis. It also aligns with the goals of sustainable farming and precision agriculture, making it a highly meaningful application of machine learning.

---

### ⚠️ Challenges: What are the challenges of this project?

1. **Multiclass classification complexity**: The dataset includes 22 different crop classes, which increases the complexity of classification compared to binary problems.  
2. **Feature similarity**: Some crops require similar soil conditions, making their separation difficult based on only four features.  
3. **Overfitting risk**: Due to the small number of input features and class imbalance, the model might overfit.  
4. **Model interpretability**: Understanding *why* a crop is recommended requires using advanced interpretability techniques beyond accuracy metrics.  

---

### 🌾 Dataset: What dataset are you using? How do you plan to collect it?

The dataset used is the **Soil Measures Dataset**, available on [Kaggle](https://www.kaggle.com/datasets/mohamedmostafa259/soil-measures). It contains 1988 samples with four input features (`n`, `p`, `k`, `ph`) and a categorical target (`crop`). Each row corresponds to an optimal crop for a particular soil composition. The dataset is downloaded programmatically using the `kagglehub` library, ensuring reproducibility and version control.

---

### 🤖 Method or Algorithm: What method or algorithm are you proposing?

Several supervised learning algorithms are tested and compared:

- **Data preprocessing**: Label encoding for the target, feature scaling when appropriate, and stratified train-test split.
- **Model training**: Logistic Regression, Random Forest, K-Nearest Neighbors, and SVM are evaluated using pipelines.
- **Model tuning**: Hyperparameters for the Random Forest model are optimized using `GridSearchCV`.
- **Validation**: 5-fold cross-validation is applied to the best-performing pipeline to ensure robustness.

All models are implemented in modular pipelines using `scikit-learn`.

---

### 📊 Evaluation: How will you evaluate your results? What kind of analysis will you use to evaluate and/or compare your results?

Model evaluation includes:

- **Accuracy** and **macro F1 score** on the test set.
- **Cross-validation** score (5-fold) to evaluate generalization.
- **Confusion matrices** (both raw and normalized) to analyze misclassifications.
- **Learning curves** to assess underfitting/overfitting behavior.
- **Permutation Feature Importance** to identify which features are most predictive.
- **SHAP plots** for global (summary) and local (waterfall) interpretability, allowing model predictions to be explained transparently.

---

