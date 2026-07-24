# Unemployment Analysis with Python
### Regional and Temporal Trends, with Focus on COVID-19 Impact in India

Exploratory data analysis of unemployment data across Indian states/UTs, examining regional disparities and the impact of the COVID-19 lockdown on unemployment rates.

## Objective

Perform exploratory data analysis on unemployment data to uncover regional and temporal trends, with a focus on the impact of the COVID-19 pandemic on unemployment rates in India.

## Dataset

- **File:** `Unemployment in India.csv`
- **Coverage:** 28 states/UTs, monthly estimates
- **Period:** May 2019 – June 2020
- **Key columns:**
  - `Region` — State/UT
  - `Date` — Month of estimate
  - `Estimated Unemployment Rate (%)`
  - `Estimated Employed`
  - `Estimated Labour Participation Rate (%)`

## Tech Stack

- Python 3
- pandas, numpy — data manipulation
- matplotlib, seaborn — visualization

## Project Structure
## Analysis Workflow

1. **Data Loading & Cleaning**
   - Stripped whitespace from column headers and string fields
   - Removed duplicate rows
   - Converted numeric columns and parsed `Date` (day-first format)
   - Dropped fully blank rows

2. **Descriptive Statistics** — summary stats across all numeric fields

3. **Region-wise & Month-wise Trends** — average unemployment rate grouped by state and by calendar month

4. **Time-Series Visualization** — unemployment rate over time for the top 3 highest-average states

5. **Bar Chart** — top 10 states ranked by average unemployment rate

6. **Correlation Heatmap** — relationships between unemployment rate, employment, and labour participation rate

7. **Pre-COVID vs. Post-COVID Comparison** — mean unemployment rate before and after India's nationwide lockdown (March 25, 2020)

## Key Findings

- **~87% spike in unemployment during lockdown** — average rate rose from 9.51% (pre-COVID) to 17.77% (post-COVID), peaking at 23.64% in April 2020, with partial recovery to 10.55% by June 2020. This points to a sharp, short-lived shock rather than a permanent structural collapse — at least within this dataset's window.

- **Unemployment stress was regionally uneven.** Tripura, Haryana, and Jharkhand recorded average rates 3–4x higher than the lowest states (Meghalaya, Odisha, Assam). Tripura's elevated rate predates COVID, suggesting a pre-existing structural issue, while Haryana's and Jharkhand's high averages were driven specifically by the lockdown spike.

- **Unemployment rate was nearly uncorrelated with labour participation rate** (r ≈ 0.003), suggesting the crisis was driven by job losses among people already in the workforce rather than by people entering or exiting the labour market — consistent with a sudden-shock event like a lockdown rather than a gradual economic shift.

## How to Run
