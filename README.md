# Quant-Test
Please try to create a model that predicts the following month's median_close price and gives your predictions on top **20** tickers with the **highest monthly median_close_pice_change** for the next month (i.e. May 2022).

i.e. median_close_pice_change = Median Close Price (May 2022) / Median Close Price (Apr 2022) - 1

**Requirements:**
1. Please create a new table `result_{your_name/alias}` that contains the your predicted median_close prices for the 20 stocks selected by your model. 
2. You are encouraged to use any of the sample model structure below but feel free to create your own. 
3. *Accuracy is not the objective, only a working model.*


## Data
For price data, you can connect to our database where table `data_price` has open, high, low, close price, and total_return_index of 332 Hong Kong stocks from Jan 2016 until Apr 2022.
```
host: pgm-3ns7dw6lqemk36rgpo.pg.rds.aliyuncs.com
username: loratech
pw: loraTECH123
port: 5432
database: postgres
```


## (Optional) Sample Model
### A. Tree-based Model
- Use LGBMRegressor model and optimizing MSE;
- Use past 1-week / 1-month / 3-month / 1-year return (based on total return index) and past 1-year Rogers-Satchell volatility as inputs;
- Use Hyperopt (set max_eval=10) for Hyperparameter optimization;
- Use all samples after 2021 as the validation set.

### B. RNN Model
- Use RNN model;
- Use weekly open / high / low / close as inputs;
- Use all samples after 2021 as the validation set.
