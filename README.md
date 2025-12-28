# Market Trend Analysis: Predictive Modeling and Quantitative EDA

## Project Overview
This project focuses on the comprehensive analysis of historical market data, aiming to identify patterns in asset price movements and develop a predictive model for daily returns. The study covers the entire pipeline from data integrity validation and Exploratory Data Analysis (EDA) to the implementation of machine learning classification models.

The core objective was to determine whether technical indicators could provide a statistically significant edge in predicting market direction within a low-volatility environment.

## Data Source
The dataset used in this analysis was sourced from Kaggle.

**Dataset Name:** Market Trend Analysis Dataset

**Author:** Kundan Sagar Bedmutha

**Source Link:** [Link to Kaggle Dataset](https://www.kaggle.com/datasets/kundanbedmutha/market-trend-analysis-dataset)

**License:** CC BY 4.0 - [Link to License](https://creativecommons.org/licenses/by/4.0/)

## Key Methodology
### 1. Data Integrity and Cleaning
Financial datasets often suffer from "look-ahead bias" and survivorship bias. To ensure a robust foundation, the following steps were taken:
- **Handling Missing Values:** Implemented Forward Fill (ffill) to maintain time-series continuity without introducing future information.
- **Logical Validation:** Applied constraints to ensure daily high/low/close price consistency (e.g., ensuring High >= Low).
- **Feature Engineering:** Developed technical indicators including RSI (Relative Strength Index), MACD (Moving Average Convergence Divergence), and 50-day Simple Moving Averages (SMA).

### 2. Quantitative Exploratory Data Analysis (EDA)
The EDA phase focused on the statistical properties of market returns:
- **Distribution Analysis:** Identified high kurtosis (leptokurtic distribution) with narrow tails, suggesting a highly stable market regime with rare extreme events.
- **Multicollinearity Check:** Discovered a high correlation (0.86) between RSI and MACD, leading to strategic feature selection to avoid model redundancy.

### 3. Machine Learning Framework
A 3-class classification approach was adopted to distinguish between meaningful trends and market noise:
- Target Labeling: Movements were classified as Up (1), Down (-1), or Neutral (0) using a 0.5% volatility threshold.
- Splitting Strategy: Utilized a chronological Time-Series Split (70% Train / 15% Val / 15% Test) to respect the temporal nature of the data.
- Model Benchmarking: Evaluated Random Forest, XGBoost, and Logistic Regression.

## Results and Findings
**Predictive Performance:** The optimized Random Forest model achieved a Final Test Accuracy of 0.41. Given a 3-class random baseline of 0.33, this represents an ~8% predictive edge.

**Generalization:** The minimal variance between Validation (0.42) and Test (0.41) accuracy scores confirms the model's stability and resistance to overfitting.

**Feature Importance:** Analysis revealed that while price action (Close/SMA) remains the primary driver, momentum indicators (RSI/MACD) provide critical secondary signals for trend identification.

## Tools and Technologies
**Language:** Python (Pandas, NumPy)

**Environment:** Google Colab

**Machine Learning:** Scikit-Learn, XGBoost

**Visualization:** Matplotlib, Seaborn, Plotly


## Conclusions
The analysis proves that even in a highly concentrated, low-volatility market, quantitative indicators can provide a reliable signal for directional movement. The project demonstrates the full lifecycle of a data science task, emphasizing the importance of domain-specific data preparation and the cautious interpretation of statistical models in finance.
