# Sales Forecasting Using Machine Learning

A beginner-friendly time-series forecasting project prepared for a machine learning internship. The notebook explores monthly sales data, creates lag features, compares a Random Forest model against two simple baselines, evaluates the most recent 12 months without shuffling time, and forecasts the next 12 months.

## Dataset

The notebook uses the public `a10.csv` monthly sales dataset from the Selva86 datasets repository:

`https://raw.githubusercontent.com/selva86/datasets/master/a10.csv`

The dataset is public example data, not private company data. The notebook expects columns named `date` and `value`.

## Methods

- **Random Forest Regressor:** predicts monthly sales using the previous 12 observed values.
- **Last-value baseline:** predicts the next month using the latest observed value.
- **Seasonal-naive baseline:** predicts the next month using the observed value from 12 months earlier.

The latest 12 eligible observations are used as a chronological holdout. The notebook selects the method with the lowest holdout MAE for the recursive next-12-month forecast. MAE, RMSE, and R² are printed by the notebook; values should be copied into this README only after running the notebook.

## How to run

1. Open `Sales_Forecasting_New_Project.ipynb` in Google Colab or Jupyter.
2. Run all cells from top to bottom. Internet access is needed to load the dataset.
3. Inspect the model comparison table and forecast graph.
4. The notebook generates a ZIP containing the cleaned data, comparison metrics, forecast CSV, model bundle, and graphs.

## Output files

- `sales_cleaned.csv`
- `sales_model_comparison.csv`
- `sales_forecast_next_12_months.csv`
- `sales_forecast_comparison.png`
- `sales_forecast_future.png`
- `sales_historical_trend.png`
- `sales_forecasting_model.pkl`

## Limitations

This is a demonstration project based on one public time series. It does not include external drivers such as holidays, promotions, price changes, stock availability, or macroeconomic conditions. Performance on a single 12-month holdout may not generalize to other datasets or periods. Recursive multi-month predictions can become flat or drift, so users should inspect forecasts against the historical data and holdout metrics.
