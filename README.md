# Forecasting the 2-year Treasury yield

Time-series models of monthly changes in the US 2-year Treasury yield (FRED series `DGS2`, 2000 onwards), tested out of sample from 2020 against a random walk.

The notebook works through:

1. Stationarity tests (ADF, KPSS) and choosing an AR lag length (AIC/BIC)
2. Residual diagnostics: Ljung-Box, ARCH-LM, Jarque-Bera
3. GARCH, GJR-GARCH and EGARCH models with Student-t errors
4. Expanding-window out-of-sample forecasts of the mean and volatility, scored against a random walk and constant variance (RMSE, Clark-West, QLIKE, Diebold-Mariano)
5. Adding lagged CPI, core CPI and industrial production as regressors

Write-up: [jamescreedysmith.com/projects/2-year-treasury-yield-model](https://www.jamescreedysmith.com/projects/2-year-treasury-yield-model)

## Running it

The data comes from FRED, which needs a free API key ([get one here](https://fred.stlouisfed.org/docs/api/api_key.html)).

```bash
pip install -r requirements.txt
export FRED_API_KEY=your_key_here
jupyter notebook "2 year rates.ipynb"
```
