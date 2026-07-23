# Car Price Prediction with Machine Learning

## Objective
Build a regression model that predicts the selling price of a used car based on
features such as brand, age, mileage, fuel type, and transmission — part of the
Oasis Infobyte Data Science Internship (Task 3).

## Dataset
- **Source:** [Vehicle dataset from CarDekho](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho) — Kaggle
- **File used:** `CAR DETAILS FROM CAR DEKHO.csv`
- **Rows:** 4,340 | **Columns:** 8
- **Original columns:** `name`, `year`, `selling_price`, `km_driven`, `fuel`, `seller_type`, `transmission`, `owner`

## Tech Stack
- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- Jupyter Notebook

## Workflow
1. **Data Cleaning** — checked for null values, duplicate rows, and inconsistent
   categorical formatting (none found).
2. **Feature Engineering**
   - `car_age` derived from `year` (relative to 2020, the dataset's most recent year)
   - `brand` extracted from the first word of `name`
   - Dropped original `name` and `year` columns
3. **Exploratory Data Analysis**
   - Distribution of selling price (right-skewed)
   - Selling price vs fuel type (boxplot)
   - Selling price vs car age (scatter)
4. **Encoding** — One-Hot Encoding applied to `fuel`, `seller_type`, `transmission`,
   `owner`, and `brand` (`drop_first=True` to avoid multicollinearity)
5. **Correlation Analysis** — heatmap of core numeric features plus full correlation
   ranking of all encoded features against `selling_price`
6. **Modeling** — trained and compared two regression models:
   - Linear Regression (baseline)
   - Random Forest Regressor
7. **Evaluation** — MAE, RMSE, and R² for both models
8. **Feature Importance** — extracted from the best-performing model
9. **Residual Analysis** — checked for systematic error patterns

## Results

| Metric | Linear Regression | Random Forest |
|--------|-------------------|----------------|
| MAE | 184,882.01 | 114,983.83 |
| RMSE | 378,760.37 | 270,898.17 |
| R² | 0.5299 | 0.7595 |

**Best-performing model:** Random Forest Regressor — outperformed Linear Regression
across all metrics, achieving a ~38% lower MAE and explaining ~76% of the variance
in selling price versus ~53% for the linear model. This indicates car pricing
depends on non-linear relationships between features (age, mileage, brand) that a
linear model cannot fully capture.

**Key predictors:** `car_age` and `km_driven` were the strongest predictors of
selling price, based on Random Forest feature importance.

## Limitations
- Dataset includes only basic listing attributes — no engine size, mileage rating,
  or vehicle condition data, which likely caps achievable model accuracy.
- Residual analysis showed increasing error at higher price points, likely due to
  fewer high-price examples in the training data.
- A few brand names were affected by simple first-word extraction (e.g., "Land Rover"
  → "Land"); left uncorrected as it does not materially affect model performance.

## How to Run
1. Clone this repository
2. Ensure `CAR DETAILS FROM CAR DEKHO.csv` is in the same directory as the notebook
3. Install dependencies: `pip install pandas numpy scikit-learn matplotlib seaborn`
4. Open `car_price_prediction.ipynb` in Jupyter and run all cells top to bottom

