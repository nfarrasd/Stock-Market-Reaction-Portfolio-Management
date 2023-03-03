# Indonesia's Economic Causality & Forecasting

This is an individual side-project made by Moch Nabil Farras Dhiya (me) as a mean to analyze whether there is a relationship between COVID-19, Currency Exchange, and Stock Market, especially in Indonesia. Specifically, it was done to implement my scraping, data analytics, time-series modeling, and Neural Network knowledges using Python and MySQL as the database 
(soon changed to use COVID-19 API because I plan to deploy the data using Streamlit, where I can not possibly do if I host the data on local database).

## Dataset
The data used in this project is obtained from MySQL Local Database (COVID-19) from my Automated COVID-19 project and YFinance (Currency & Stock Market Price).

## Steps
1.   Extracting data from External Sources (Yahoo Finance) and Local DB
2.   Transform the data (making sure it is usable and consistent)
3.   Analyze the trend and perform statistical test to analyze the relationship between these data
4.   TSA forecasting to predict the economic condition (ARIMA, ARIMAX, SARIMA, GARCH, LSTM, and CNN)
5.   Perform portfolio optimization, limited to BBCA.JK and ^JKSE stock price (which are used in this analysis)

## Current Result
1.   In general, we are 95% confidence that all of these data have significant correlation with COVID-19 data. In addition, BBCA and ^JKSE stock market are also correlated with IDR/USD currency exchange, but not with IDR/JPY currency exchange.
2.   The best models to predict BBCA stock price are: (1) LSTM, (2) ARIMAX(4,1,0,'IDR/USD'), and (3) ARIMA(4,1,0).
3.   Based on ARIMAX(3,1,1)x(0,1,1,52) model, we can see that for the **next 7 days (2022-08-07 - 2022-08-13)**, we can expect that the **BBCA stock market price** will be relatively stagnant at **8790 IDR** with a **margin error of ~4.47%**.
4.   Using Markowitz Mean-Variance Model, it is recommended to heavily invest (almost all-out) into ^JKSE stock market.

## Future Improvement
1.  Create a dashboard using Streamlit which consists of the daily data and forecasted values for the next 7 days.
