# Weather Trend Forecasting

Concise submission package for the PM Accelerator weather forecasting assessment.

## Project summary
- **Dataset:** Global Weather Repository
- **Primary target:** daily mean `temperature_celsius`
- **City modeled:** Bandar Seri Begawan
- **Time key:** `last_updated`
- **Notebook:** `notebook_DS.ipynb`

## Basic requirements
- **Data cleaning & preprocessing:** parsed timestamps, aggregated irregular observations to daily city-level rows, checked coverage, repaired short training-only gaps, reviewed outliers, and stated the normalization decision explicitly.
- **Use `last_updated` for time series analysis:** built the daily panel directly from `last_updated`.
- **EDA:** included daily temperature diagnostics, precipitation diagnostics, and multivariate exploratory analysis.
- **Temperature and precipitation visualizations:** included both in the notebook.
- **Forecasting model + evaluation:** compared moving average, ARIMA candidates, and recursive XGBoost using MAE and RMSE.

## Advanced requirements that were completed
- **Anomaly detection:** model-based outlier detection from ARIMA residuals.
- **Multiple forecasting models:** moving average, multiple ARIMA models, and multiple recursive XGBoost variants.
- **Ensemble:** XGBoost ensemble forecasts were built and evaluated.
- **Feature importance:** training-only XGBoost gain importance and feature selection.

## Final result
- The strongest model in this notebook was **ARIMA(1,1,1)**.
- ARIMA outperformed the tested XGBoost variants on the holdout window for this city-series setup.

## Repository contents
- `notebook_DS.ipynb` : full analysis
- `README.md` : summary and setup
- `requirements.txt` : dependencies
- `Weather_Forecasting_Report_Template.docx` : concise report template

## How to run
```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

Then open `notebook_DS.ipynb` and run all cells in order.
