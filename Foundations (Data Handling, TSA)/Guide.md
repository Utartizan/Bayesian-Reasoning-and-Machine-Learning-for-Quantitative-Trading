# Foundations of Financial Data Handling in Octave

![GitHub last commit](https://img.shields.io/github/last-commit/Utartizan/Bayesian-Reasoning-and-Machine-Learning-for-Quantitative-Trading/main?color=blue)


## Overview

This subsection serves a the foundational step in my series of quantitative trading projects implemented in Octave. It focuses on the essential skills of handling financial data, including loading, preprocessing, cleaning, performing basic time-series analysis, and visualising stock price data. 

Any code here is written in Octave, a free and open-source alternative to MATLAB, making it pretty much accessible for anyone interested in quant trading without requiring expensive software licenses.

The scripts in this folder are designed to work with historical stock price data in CSV format, such as that provided by Yahoo Finance. 

---

## Objectives

This module covers the following key areas:

1. **Loading and Preprocessing Financial Data**: Load CSV files from sources like Yahoo Finance and parse dates and numerical data.
2. **Cleaning Data**: Handle missing values, detect and correct outliers, and adjust for splits/dividends.
3. **Time-Series Analysis**: Calculate simple/log returns, annualised volatility, and moving averages.
4. **Visualisation**: Generate price plots, candlestick charts, and volume analysis to understand trends and patterns.

---

## 1. Loading and Preprocessing Financial Data

### Why It Matters
Financial data is the raw material of quant trading. It often comes in structured formats like CSV files from sources such as Yahoo Finance, Quandl (Nasdaq Data Link), or Alpha Vantage. These datasets typically include columns like `Date`, `Open`, `High`, `Low`, `Close`, `Adjusted Close`, and `Volume`. Loading and preprocessing this data ensures it’s in a format suitable for analysis, setting the stage for all subsequent steps.

### Key Concepts
- **Data Formats**: Financial data often includes mixed types (e.g., dates as strings, prices as floats). Understanding how to parse these correctly is crucial.
- **Date Handling**: Dates must be converted into a numerical format (e.g., using `datenum` in Octave) for time-series operations like sorting or calculating intervals.
- **Source Variability**: Different data providers (e.g., Yahoo Finance vs. Alpha Vantage) use different column names or formats. Preprocessing must account for this variability.

### Common Methodologies
- **Parsing CSVs**: Use tools like `textscan` or `csvread` to load data, handling headers and mixed data types appropriately.
- **Data Validation**: Check for expected columns and data types to avoid errors later.
- **Standardization**: Convert dates to a consistent numerical format and ensure numerical columns (e.g., prices) are free of non-numeric entries.

### Challenges
- **Inconsistent Formats**: Some datasets may have missing headers, extra columns, or non-standard date formats.
- **Large Datasets**: High-frequency data (e.g., tick data) can be memory-intensive, requiring efficient loading techniques.
- **Data Availability**: Free sources like Yahoo Finance may have gaps or restrictions on historical data.

### General Takeaway
Understanding how to load and preprocess data builds familiarity with financial datasets and their quirks. It also teaches the importance of data integrity—ensuring the data you work with accurately represents the market.

---

## 2. Cleaning Data

### Why It Matters
Raw financial data is rarely perfect. Missing values, outliers, and corporate actions (e.g., stock splits, dividends) can distort analysis if not addressed. Cleaning ensures the data is reliable, which is critical for generating accurate trading signals or backtesting strategies.

### Key Concepts
- **Missing Values**: Gaps in data (e.g., no price recorded for a day) can arise due to market closures, errors, or illiquidity.
- **Outliers**: Extreme price movements may be errors (e.g., data entry mistakes) or real events (e.g., flash crashes). Distinguishing between the two is key.
- **Adjusting for Corporate Actions**: Stock splits and dividends affect raw prices. Using `Adjusted Close` prices corrects for these events to provide a true economic picture.

### Common Methodologies
- **Handling Missing Values**:
  - **Forward Fill**: Use the previous day’s value (common in time-series data).
  - **Interpolation**: Estimate missing values based on surrounding data points.
  - **Flagging**: Mark missing data for exclusion in certain analyses.
- **Outlier Detection**:
  - **Z-Score**: Flag data points with a z-score above a threshold (e.g., |z| > 3).
  - **Percentile-Based**: Remove or adjust values outside the 1st/99th percentiles.
  - **Domain Knowledge**: Use market knowledge to determine if an outlier is valid (e.g., a price drop during a known crash).
- **Adjusting for Splits/Dividends**:
  - Use the `Adjusted Close` column to scale OHLC (Open, High, Low, Close) prices proportionally.
  - Alternatively, apply adjustment factors provided by data vendors.

### Challenges
- **Over-Cleaning**: Removing too many outliers can erase meaningful market events.
- **Under-Cleaning**: Failing to address missing values or errors can bias results.
- **Adjustment Accuracy**: Adjustments rely on the accuracy of `Adjusted Close` data, which may vary by provider.

### Educational Takeaway
Cleaning data teaches the importance of skepticism toward raw data. It also introduces the trade-off between preserving information and ensuring reliability—a recurring theme in quant trading.

---

## 3. Time-Series Analysis

### Why It Matters
Financial data is inherently a time series, where observations (e.g., prices) are ordered by time. Basic time-series analysis extracts key metrics like returns, volatility, and trends, which are the building blocks of trading strategies.

### Key Concepts
- **Returns**:
  - **Simple Returns**: `(P_t - P_{t-1}) / P_{t-1}`, useful for intuitive interpretation.
  - **Log Returns**: `log(P_t / P_{t-1})`, additive over time and better for statistical modeling.
- **Volatility**: A measure of price variability, often calculated as the standard deviation of returns and annualised (e.g., using 252 trading days per year).
- **Moving Averages**: Smooth price data to identify trends (e.g., 20-day Simple Moving Average).

### Common Methodologies
- **Calculating Returns**:
  - Compute daily returns from closing prices.
  - Use log returns for compounding effects over multiple periods.
- **Estimating Volatility**:
  - Calculate the standard deviation of daily log returns.
  - Annualise by multiplying by `sqrt(252)` (assuming 252 trading days).
- **Trend Analysis**:
  - Simple Moving Average (SMA): Average prices over a fixed window (e.g., 20 days).
  - Exponentially Weighted Moving Average (EWMA): Give more weight to recent prices.

### Challenges
- **Non-Stationarity**: Financial time series are often non-stationary (mean and variance change over time), complicating analysis.
- **Noise**: Daily price data can be noisy, masking true trends.
- **Look-Ahead Bias**: When calculating metrics like moving averages, ensure you only use past data to avoid unrealistic results in backtesting.

### Educational Takeaway
Time-series analysis introduces core financial concepts like returns and volatility, which are central to risk management and strategy development. It also highlights the importance of handling temporal data correctly to avoid biases.

---

## 4. Visualising Financial Data

### Why It Matters
Visualisation is a powerful tool for understanding financial data. It helps identify trends, anomalies, and patterns that might not be apparent in raw numbers. In quant trading, visualisations like candlestick charts and volume plots are standard for assessing market behavior.

### Key Concepts
- **Price Plots**: Show price trends over time, often with overlays like moving averages to highlight trends.
- **Candlestick Charts**: Display OHLC (Open, High, Low, Close) data for each period, revealing daily price action and sentiment (e.g., bullish vs. bearish days).
- **Volume Analysis**: Plot trading volume to understand market activity and liquidity.

### Common Methodologies
- **Price Plots**:
  - Plot adjusted close prices over time.
  - Overlay a moving average to smooth noise and reveal trends.
- **Candlestick Charts**:
  - For each day, plot a “candle” with a body (open to close) and wicks (high to low).
  - Color-code bodies (e.g., green for up days, red for down days).
- **Volume Plots**:
  - Use bar charts to show daily trading volume.
  - Correlate volume spikes with price movements to infer market dynamics.

### Challenges
- **Tool Limitations**: Octave lacks built-in functions for some visualisations (e.g., candlestick charts), requiring manual approximations.
- **Over-Plotting**: With large datasets, plots can become cluttered; focus on subsets or aggregations.
- **Interpretation**: Visualisations require context—e.g., a volume spike might indicate buying pressure or a data error.

### Educational Takeaway
Visualisation teaches how to communicate data insights effectively. It also builds intuition for market behaviour, such as recognising trends or spotting unusual activity through volume and price patterns.


---

## Broader Context in Quant Trading

The skills in this module are the first step in a quant trading pipeline:
1. **Data Handling**: Prepare data for analysis (this module).
2. **Feature Engineering**: Extract predictive features (e.g., technical indicators).
3. **Modeling**: Build predictive models (e.g., regression, machine learning).
4. **Strategy Development**: Design and backtest trading strategies.
5. **Execution**: Implement strategies in live markets.

Each step builds on clean, well-understood data. Errors or oversights in data handling can propagate through the pipeline, leading to flawed strategies or losses.

---
