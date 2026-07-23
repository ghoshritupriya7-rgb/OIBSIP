# Task 5 - Sales Prediction Using Python

Built regression models to predict product sales based on advertising 
spend across TV, Radio, and Newspaper channels.

## Tech Stack
Python, pandas, scikit-learn, matplotlib, seaborn, Jupyter Notebook

## Approach
- Loaded the Advertising dataset (TV, Radio, Newspaper, Sales)
- Performed EDA: null check, descriptive stats, pairplot, scatter plots
- Built a correlation heatmap to identify channel impact
- Trained Linear Regression (baseline) and Random Forest Regressor
- Evaluated using MAE, RMSE, and R²
- Analyzed residuals and interpreted feature impact

## Results
- Linear Regression: MAE 1.461, RMSE 1.782, R² 0.899
- Random Forest: MAE 0.620, RMSE 0.769, R² 0.981 — best performing model

## Key Insight
TV advertising has the strongest impact on sales (correlation 0.78), 
followed by Radio (0.58), with Newspaper contributing the least (0.23).

## Files
- sales_prediction.ipynb - full notebook with code, visualizations, and analysis
