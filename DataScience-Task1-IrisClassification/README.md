#  Iris Flower Classification

## 📌 Objective
Train a machine learning classification model to identify the species of an iris flower — **Setosa**, **Versicolor**, or **Virginica** — based on its physical measurements (sepal length, sepal width, petal length, petal width).

This project is Task 1 of the **Data Science** track for the Oasis Infobyte Summer Internship Program (OIBSIP).

---

## 🛠️ Tech Stack
- Python
- scikit-learn
- pandas
- matplotlib / seaborn
- Jupyter Notebook

---

## 📂 Dataset
The Iris dataset is loaded directly from `sklearn.datasets.load_iris()` — no external download is required. It contains 150 samples (50 per species) with 4 numeric features per sample.

---

## 🔍 Project Workflow

1. **Data Loading** — Loaded the built-in Iris dataset into a pandas DataFrame.
2. **Exploratory Data Analysis (EDA)** — Checked shape, data types, null values, and descriptive statistics. Confirmed the dataset is perfectly balanced (50 samples per class) with no missing values.
3. **Visualisations** — Created a pairplot and per-feature box plots to visualise how well each species separates across the four measurements.
4. **Feature Selection Discussion** — Identified petal length and petal width as the most discriminative features, based on visual separation between species.
5. **Train/Test Split** — Split the data 80/20 using stratified sampling to preserve class balance.
6. **Model Training** — Trained two classifiers:
   - Logistic Regression
   - K-Nearest Neighbours (K=5)
7. **Model Evaluation** — Evaluated both models using accuracy, confusion matrix, and classification report (precision, recall, F1-score).
8. **Best Model Selection** — Compared both models on test accuracy and declared a winner with justification.

---

## 📊 Results

| Model | Test Accuracy |
|---|---|
| Logistic Regression | ~0.966667 |
| **K-Nearest Neighbours** | **1.000000** |

**Best-Performing Model: K-Nearest Neighbours (KNN)**

KNN achieved a perfect test accuracy of **1.000000** (30/30 correct), with zero misclassifications across all three species, including the harder Versicolor/Virginica boundary where overlap typically causes errors.

This result aligns with the feature-selection analysis: since petal length and petal width are highly discriminative and the species form fairly tight, well-separated clusters in feature space, a distance-based method like KNN can directly exploit that clustering — it doesn't need to assume any particular decision boundary shape the way Logistic Regression does.

**Caveat:** With only 30 test samples, a perfect score can partly reflect the small test set size rather than guaranteed generalization. Cross-validation across multiple splits would give a more robust confidence estimate, but for the scope of this task, KNN is declared the best model based on the held-out test results.

---

## 📁 Repository Structure

---

## ▶️ How to Run
1. Clone this repository or download the notebook.
2. Install dependencies:
3. Open `Iris_Flower_Classification.ipynb` in Jupyter Notebook or JupyterLab.
4. Run all cells from top to bottom.

---
