# Predicting Emerging Market Trends Using Price and Trading Volume Data

## Project Overview
This project focuses on detecting **early trends in the stock market** using historical stock price and trading volume data.  
The main idea is that when people start paying attention to a stock, its **price and volume change**, which can signal the start of a new trend.

We use machine learning to identify and rank these early trend signals before they become obvious.

---

## Problem Description
Stock market trends usually start quietly and grow over time. By the time a trend is clear, it may already be too late to act.

The goal of this project is to:
- Detect **early trend signals**
- Use **simple and explainable features**
- Avoid complex or black-box models
- Focus on realistic market behavior

---

## Data Source
The data is collected from **Yahoo Finance** using the `yfinance` Python library.

**Stocks used in this project:**
- Apple (AAPL)
- Microsoft (MSFT)
- Google (GOOGL)
- Amazon (AMZN)
- Meta (META)

The dataset contains several years of **daily stock prices and trading volume** for each company.

---

## Data Preparation
The following steps were applied to prepare the data:
- Converted date columns to proper datetime format
- Sorted data by stock and date
- Removed missing values
- Combined all stocks into a single dataset
- Ensured each row represents one stock on one trading day

This process created a clean and consistent dataset for analysis.

---

## Feature Engineering
To capture early trend signals, we created the following features:

- **Moving Averages**
  - 10-day moving average
  - 30-day moving average
- **Price Momentum**
  - Daily percentage change in closing price
- **Trading Volume Features**
  - Average volume over recent days
  - Volume ratio compared to recent average
- **Volatility**
  - Short-term price variation

These features are simple, interpretable, and commonly used in financial analysis.

---

## Trend Definition
An **emerging trend** is defined as:
- An upward movement in stock price
- Supported by higher-than-normal trading volume
- Occurring before the trend becomes clearly visible

Each trading day is labeled as:
- `1` → Emerging trend  
- `0` → No emerging trend

Emerging trends are rare, which reflects real market conditions.

---

## Model Used
We use **Logistic Regression** with class balancing.

**Why Logistic Regression?**
- Easy to understand and explain
- Works well for binary classification
- Handles imbalanced data
- Produces probability scores instead of only yes/no predictions

The model predicts how likely a given day is part of an emerging trend.

---

## Evaluation Approach
Because emerging trends are rare, accuracy alone is not useful.

We evaluate the model using:
- Precision
- Recall
- F1-score
- **Precision@K**, which measures how many real trends appear in the top-ranked predictions

This approach matches real-world decision-making, where only top signals matter.

---

## Results
- The model successfully identifies early trend signals better than random guessing
- Emerging trends are ranked higher by the model
- Results are consistent across multiple stocks
- Simple price and volume features are effective for early trend detection

---

## Visualizations
The notebook includes visualizations such as:
- Stock price over time
- Moving average lines
- Highlighted emerging trend points
- Trend signals for each company

These plots help explain and validate the model’s predictions.

---

## Tools and Technologies
- Python
- pandas
- numpy
- scikit-learn
- yfinance
- matplotlib
- Google Colab

---

## Project Structure
