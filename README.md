# Financial-Forecasting-Through-Earnings-Call-Sentiment
APAN 5205 Applied Analytics Frameworks and Methods II - Final Project  
Advised by: Prof. Vishal Lala

The objective of our project is to develop a regression model with ARIMA errors that predicts the stock prices of the top 9 constituent NASDAQ stocks ("AAPL", "MSFT", "GOOG", "AMZN", "TSLA", "META", "NVDA", "PEP", "COST") by analyzing the earnings call transcripts of these companies. We selected these stocks based on the [article](https://www.nasdaq.com/articles/the-top-10-constituents-of-the-nasdaq-100-index) by NASDAQ.

It is worth noting that Alphabet has 2 stocks (GOOG and GOOGL) in the list, but the company only holds 1 earnings call transcript every quarter. Therefore, we selected the class C share as our target stock, leaving the list with 9 stocks. We retrieved the earnings call transcripts data from the FMP API and financial data from Yahoo Finance using Quantmod. The data range covers the period from 2013 to 2022, a total of 10 years. We use the data from 2013 to 2020 (8 years) for training the model and the data from 2021 to 2022 (2 years) for testing.

We performed sentiment analysis and latent semantic analysis (LSA) to extract statistics and dimensions as predictors for our ARIMA model. As the output data is highly dimensional, we used factor analysis to reduce the dimensionality. Finally, we were able to pass the predictors gained from text mining as xreg in the ARIMA function to construct a regression model with ARIMA errors. However, while the model fitted better for the training data, it overfits and performs worse on the testing data.

Moreover, we successfully implemented a Bidirectional Encoder Representations from Transformers (BERT) model to extract 738 features from the text data. However, considering that our data is already highly dimensional, we did not input the features into our ARIMA model. Instead, we performed a simple linear regression model for the stock prices based on the extracted features.
