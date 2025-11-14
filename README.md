# Nexus Bank Financial Analytics and Modeling Platform

## Overview

A production-ready financial data engineering platform for algorithmic trading, portfolio optimization, and fraud detection built on Databricks and Delta Lake. Processes 60,000+ records from multiple financial data sources with machine learning models and AI-powered insights.

## Key Results

- 60,632 records processed from Yahoo Finance, FRED, and fraud datasets
- 2.71% MAPE in stock price forecasting (ARIMA model)
- 0.519 ROC-AUC for fraud detection (Logistic Regression)
- 86.7% of predictions within 5% accuracy
- 99.7% reduction in portfolio analysis time (40 hours to 5 minutes)

## Technology Stack

- **Platform:** Databricks, Delta Lake
- **Processing:** PySpark, Spark SQL
- **ML Models:** ARIMA, Prophet, Logistic Regression, Random Forest
- **Visualization:** matplotlib, seaborn
- **AI:** Databricks Foundation Models (Claude, Llama)
- **Data Sources:** yfinance, FRED API

## Project Components

### Data Pipeline
- Ingested 6,241 stock prices, 1,022 economic indicators, 3,369 crypto prices, 50,000 fraud transactions
- 100% API success rate with incremental loading capability
- Delta Lake with ACID transactions, Z-ordering, and change data feed

### Feature Engineering
- 15+ technical indicators: moving averages (7, 14, 50, 200-day), RSI, Bollinger Bands, volatility
- 13 fraud detection features: transaction patterns, amount deviation, customer behavior
- Forward-fill logic for economic data alignment

### Machine Learning Models

**Stock Forecasting:**
- ARIMA(5,1,2): MAE $6.21, RMSE $9.07, MAPE 2.71%
- Prophet: MAE $6.20, RMSE $8.49, MAPE 2.72%
- 98.3% accuracy within 10% tolerance

**Fraud Detection:**
- Logistic Regression: ROC-AUC 0.5190
- Random Forest: ROC-AUC 0.4885
- Top signals: customer average amount, transaction amount, amount deviation ratio

### Portfolio Analytics
- Sharpe ratio analysis (Apple: 1.84, Microsoft: 1.72)
- Correlation matrix (average: 0.68)
- 13.68% volatility reduction through diversification
- Identified 17 highly correlated stock pairs

### AI Integration
- Databricks Foundation Models for automated insights
- Portfolio analysis and fraud pattern recognition
- Natural language to SQL conversion

## Installation

1. Clone repository and install dependencies:
git clone [https://github.com/aysrivastava/Captone_Project---Group-4.git]
pip install yfinance pandas-datareader fredapi statsmodels prophet scikit-learn matplotlib seaborn

2. Import notebook to Databricks and configure:
CATALOG_NAME = "nexus_bank"
SCHEMA_NAME = "financial_data"


3. Execute cells 1-56 sequentially

## Usage

Query stock forecasts:
SELECT * FROM nexus_bank.financial_data.stock_price_forecasts
WHERE date >= '2024-10-01'

Query fraud predictions:
SELECT * FROM nexus_bank.financial_data.fraud_model_predictions
WHERE lr_probability > 0.7

Query portfolio metrics:
SELECT ticker, sharpe_ratio, annualized_return_pct
FROM nexus_bank.financial_data.portfolio_risk_metrics
ORDER BY sharpe_ratio DESC


## Team

- Ayush Srivastava (G24AI2036) - Data acquisition, Delta Lake architecture
- Harshita Gupta (G24AI2017) - Data quality, pipeline automation
- Ashitha C (G24AI2034) - Feature engineering
- Vivekanand (G24AI2101) - Predictive modeling
- Shreyansh Kumar (G24AI2029) - Portfolio analytics, AI integration

## License

Educational project for M.Tech Data Engineering capstone program for Group 4.
