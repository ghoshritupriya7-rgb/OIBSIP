# 📊 Sales Prediction Using Python

**Track:** Data Science  
**Task:** OIBSIP Data Science – Task 5  
**Internship:** Oasis Infobyte SIP

---

## 📌 Objective

Build a regression model that predicts product sales based on advertising spend across three media channels — **TV**, **Radio**, and **Newspaper** — using the classic Advertising dataset.

---

## 🗂️ Dataset

- **File:** `Advertising.csv`
- **Rows:** 200
- **Columns:**
  - `TV` — advertising spend on TV (in thousands of dollars)
  - `Radio` — advertising spend on Radio (in thousands of dollars)
  - `Newspaper` — advertising spend on Newspaper (in thousands of dollars)
  - `Sales` — product sales (in thousands of units)
- An unnamed index column present in the raw CSV is dropped during preprocessing.

---

## 🛠️ Tech Stack

- Python
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- Jupyter Notebook

---

## 🔍 Approach

1. **Data Loading & EDA**
   - Checked for null values and reviewed descriptive statistics
   - Visualised relationships between all features using a pairplot

2. **Individual Scatter Plots**
   - Sales vs. TV spend
   - Sales vs. Radio spend
   - Sales vs. Newspaper spend

3. **Correlation Analysis**
   - Generated a correlation matrix heatmap to identify which channels correlate most strongly with Sales

4. **Train/Test Split**
   - 80/20 split using `train_test_split`

5. **Modeling**
   - **Baseline:** Linear Regression
   - **Additional model:** Random Forest Regressor

6. **Evaluation**
   - Metrics used: **MAE**, **RMSE**, **R² Score**
   - Residual plot generated for the best-performing model to check for systematic error patterns

7. **Interpretation**
   - Compared Linear Regression coefficients and Random Forest feature importances to determine which advertising channel has the greatest impact on Sales

---

## 📈 Results

| Model | MAE | RMSE | R² Score |
|---|---|---|---|
| Linear Regression | 1.461 | 1.782 | 0.899 |
| Random Forest | 0.629 | 0.757 | 0.982 |

**Best Model:** Random Forest Regressor, with a significantly lower error (MAE and RMSE) and a higher R² score, indicating it captures non-linear relationships between advertising spend and sales more effectively than the linear baseline.

### Feature Impact

| Feature | Linear Regression Coefficient | Random Forest Importance |
|---|---|---|
| TV | 0.0447 | 0.6247 |
| Radio | 0.1892 | 0.3621 |
| Newspaper | 0.0028 | 0.0132 |

**Key Insight:** Random Forest importance identifies TV spend as the dominant driver of Sales, accounting for the majority of the model's predictive power, with Radio as a secondary contributor and Newspaper spend having a negligible effect. In the Linear Regression coefficients, Radio shows a nominally larger coefficient than TV — this is partly a scale artifact, since TV's spend values span a much wider range, which naturally shrinks its per-unit coefficient even though its total contribution to explained variance is larger.

### Residual Analysis

The residual plot for the best-performing model shows errors scattered randomly around zero with no clear funnel or curved pattern, indicating the model's errors are not systematically biased across the range of predicted sales.

---

## 📁 Repository Structure
## How to Run
1. Clone this repository
2. Ensure required libraries are installed:
3. Open `sales_prediction.ipynb` in Jupyter Notebook or Google Colab
4. Run all cells sequentially (top to bottom)
