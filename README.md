# Boston Housing Price Prediction

A linear regression model that predicts median home values in the Boston area from 13 neighborhood and structural features, built with scikit-learn.

## Project Overview

This project uses the classic Boston Housing dataset to explore the relationship between housing prices and factors like crime rate, number of rooms, pupil-teacher ratio, and distance to employment centers. The goal is to build and evaluate a simple, interpretable regression model that estimates a home's median value (`MEDV`) from these features.

## Dataset

- **Source:** `bostonhouseprice.csv` (included in this repo) — the classic Boston Housing dataset
- **Size:** 506 records × 14 columns
- **Target variable:** `MEDV` — median value of owner-occupied homes (in $1000s)
- **Features:** `CRIM` (per-capita crime rate), `ZN` (residential land zoned for large lots), `INDUS` (non-retail business acres), `CHAS` (borders the Charles River), `NOX` (nitric oxide concentration), `RM` (average rooms per dwelling), `AGE` (share of owner-occupied units built before 1940), `DIS` (distance to employment centers), `RAD` (highway accessibility index), `TAX` (property tax rate), `PTRATIO` (pupil-teacher ratio), `B` (proportion of Black residents, a legacy census-derived measure), `LSTAT` (% lower-status population)

## Approach

1. **Exploratory analysis** — inspected data types, summary statistics, and distributions with `df.info()` and `df.describe()`.
2. **Train/test split** — split the 506 records 80/20 into training (404 rows) and test (102 rows) sets using `train_test_split`.
3. **Modeling** — fit a `LinearRegression` model from scikit-learn on the training set.
4. **Evaluation** — scored the model on the held-out test set using mean squared error and R².

## Results

| Metric | Value |
|---|---|
| Mean Squared Error | 18.11 |
| R² Score | 0.776 |

The model explains about **78% of the variance** in median home value on unseen data. Room count (`RM`) and pupil-teacher ratio (`PTRATIO`) carry some of the largest coefficients, consistent with the intuition that housing size and school quality are strongly tied to home prices.

## Tools Used

- Python
- pandas, numpy
- scikit-learn (`LinearRegression`, `train_test_split`, `mean_squared_error`, `r2_score`)
- matplotlib

## Repository Contents

- `boston_housing_price_prediction.ipynb` — the full analysis notebook (EDA, modeling, evaluation)
- `bostonhouseprice.csv` — the dataset
- `README.md` — this file

## How to Run

1. Clone the repo and open the notebook in Jupyter.
2. Install dependencies: `pip install pandas numpy scikit-learn matplotlib`
3. Update the `pd.read_csv(...)` path in the first cell to point to `bostonhouseprice.csv` in this repo, then run all cells.

## Author

**Varshitha Reddy** — [github.com/RVarshitha](https://github.com/RVarshitha)
