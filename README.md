# Indonesia's Economic Causality & Forecasting

This is an individual side-project made by Moch Nabil Farras Dhiya (me) in June - July 2022, 
as a mean to analyze whether there is a relationship between COVID-19, Currency Exchange, and Stock Market, especially in Indonesia. Specifically, it was done to implement my scraping, data analytics, and time-series modeling knowledges using Python and MySQL as the database.

# Dataset
The data used in this project is obtained from MySQL Local Database (COVID-19) from my Automated COVID-19 project and YFinance (Currency & Stock Market Price).

# Steps
1.   Extracting data from External Sources (Yahoo Finance) and Local DB
2.   Transform the data (making sure it is usable and consistent)
3.   Analyze the trend and perform statistical test to analyze the relationship between these data
4.   TSA forecasting to predict the economic condition (ARIMA, ARIMAX, SARIMA)
5.   Perform portfolio optimization, limited to BBCA.JK and ^JKSE stock price (which are used in this analysis)

# Current Result
1.   In general, we are 95% confidence that all of these data have significant correlation with COVID-19 data. In addition, BBCA and ^JKSE stock market are also correlated with IDR/USD currency exchange, but not with IDR/JPY currency exchange.
1.   The best models to predict BBCA stock price are: (1) ARIMA(3,1,1), (2) ARIMAX(3,1,1,'IDR/USD'), and (3) SARIMA(1,1,1)x(0,1,1,12).
2.   Even though ARIMA and ARIMAX model has better AIC and RMSE, not all of their coefficients are statistically significants. In contrast, SARIMA model's coefficients are all statistically significants. In addition, SARIMA model also able to capture the trend of the BBCA stock price trend, unlike the first 2 models.
3.   Based on SARIMA(3,1,1)x(0,1,1,52) model, we can see that for the **next 7 days (2022-08-07 - 2022-08-13)**, we can expect that the **BBCA stock market price** will be have a decrement trend from **7600 IDR to 7450 IDR**, and a **margin error of ~6.3%**..
4.   Using mCVAR algorithm, it is recommended to all-out invest into BBCA.JK stock market.

# Future Improvement
1.   Compare the current model with GARCH model, as it is a financial data with high volatility. In addition to that, a Deep Learning method will also be done.
2.   Create a dashboard using Streamlit which consists of the daily data and forecasted values for the next 7 days.
