# Quantitative-Investment-in-Gold

## Problem Statement
This project analyzes the economic laws and core logic of gold's rise and fall, summarizes the key contributing factors and further extracts extra information through data analysis of factor correlation to create new variables. With possible independent factors of 7 categories including basic, percent_change, pct_threshold, continuity, homodirectivity, intensity and momentum, the project establishes the multiple linear regression model with feature selection to predict the gold or its percent change, and implements the strategy back test in the ten-year period from January 2013 to January 2023.

## Data Description
Original data includes dependent varible Wind Gold Index and its percent_change. Five basic factors: USD index, Real yields on US Treasury Bonds (10Y), Inflation Expectation of US, Oil Price, USD Liquidity. Meta daily data is obtained from Wind and converted to monthly data by averaging. Pct_change factors are the percent change of 5 basic factors. Pct_threshold factors are the categorical factors indicating if the pct_change of USD and Oil price is over the threshold. Continuity factors represent the number of periods each factor maintains in the same direction. Homodirectivity is a dummy variable whether percent changes of USD index and USD Liquidity are in the same direction since they are two strong factors through analysis. Momentum factors include current gold index, percent change of gold, and average percent change of gold in recent 2 or 3 periods.

## Brief Introduction of the strategy
#### Benchmark: HS300 index and cash, half position, monthly update
#### Back test period: January 2013 - January 2023
#### Strategy: Multiple linear regression model, pct_change of Wind Gold Index as independent variable, dependent variables include 5 basic factors, 5 pct_change factors, 2 pct_threshold factors and 4 momentum factors. Feature selection before each period through SelectKBest (k=5, scoring function=f_regression). Rolling window training with 108 samples in each period.

## File Description
File 'data.csv' is original data after first-step transformation, with all except continuity factors included.
File 'hs300_month.csv' includes data of HS300 Index.
File 'strategy.ipynb' is the main file for back test strategy.
