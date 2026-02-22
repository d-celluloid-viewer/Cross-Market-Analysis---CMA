# Cross-Market Analysis: Crypto, Oil and Stocks with SQL and Streamlit

## Project Description
This project focuses on building a cross-market analytics platform powered by SQL to compare cryptocurrencies with traditional assets like oil and stock indices. The primary objective is to identify patterns, correlations, and relative performance between these diverse asset classes using historical data from 2020 to 2026.

---

## Skills Takeaway
- API Integration (CoinGecko and Yahoo Finance)
- Database Design (SQL)
- SQL Analytics and Query Optimization
- ETL (Extract, Transform, Load) Workflows
- Streamlit Dashboard Development
- Data Manipulation with Pandas

---

## Domain
Financial Analytics / Business Intelligence (BI)

---

## Problem Statement
Cryptocurrency is frequently compared to traditional assets, often labeled as "digital gold." This project aims to determine if crypto behaves as a distinct asset class or follows traditional market trends. By aggregating data on Top Cryptocurrencies, Oil (WTI Benchmark), and Global Stock Indices (S&P 500, NASDAQ, NIFTY), the platform provides a comparative analysis of volatility and performance.

---

## Business Use Cases
- Investment Research: Analyze if Bitcoin moves in correlation with or against oil/stock markets.
- Risk Management: Assess the volatility of crypto relative to traditional benchmarks.
- Macro-Economic Analysis: Study the impact of global events, such as oil price spikes, on crypto.
- Trading Strategy Testing: Validate hypotheses for hedging or cross-market entries.
- Educational BI Tool: Demonstrates data warehousing and financial relationships.

---

## Project Approach

### 1. Data Collection
- Cryptocurrency (CoinGecko API)
    - Metadata: id, symbol, name, market_cap, circulating_supply, etc.
    - Historical Prices: 1-year daily price data for top 3 coins.
- Oil Prices (WTI Crude)
    - Dataset: WTI daily prices from 2020 to 2026.
- Stock Prices (Yahoo Finance)
    - Tickers: ^GSPC (S&P 500), ^IXIC (NASDAQ), ^NSEI (NIFTY).
    - Period: January 2020 to September 2025.

### 2. Database Design and Implementation
The project utilizes relational databases (MySQL, PostgreSQL, or SQLite) to store structured financial data.

#### Table: Cryptocurrencies
- id: VARCHAR(50) (Primary Key)
- symbol: VARCHAR(10)
- name: VARCHAR(100)
- current_price: DECIMAL(18, 6)
- market_cap: BIGINT
- market_cap_rank: INT
- total_volume: BIGINT
- circulating_supply: DECIMAL(20, 6)
- total_supply: DECIMAL(20, 6)
- ath: DECIMAL(18, 6)
- atl: DECIMAL(18, 6)
- date: DATE

#### Table: Crypto_prices
- coin_id: VARCHAR(50) (Foreign Key)
- date: DATE
- price_usd: DECIMAL(18, 6)

#### Table: Oil_prices
- date: DATE (Primary Key)
- price_usd: DECIMAL(18, 6)

#### Table: Stock_prices
- date: DATE
- ticker: VARCHAR(20)
- open: DECIMAL(18, 6)
- high: DECIMAL(18, 6)
- low: DECIMAL(18, 6)
- close: DECIMAL(18, 6)
- volume: BIGINT

---

## SQL Analytics Overview

### Cryptocurrency Analysis
- Identify top 3 coins by market capitalization.
- Filter coins with circulating supply exceeding 90% of total supply.
- Calculate average market cap rank for high-volume assets (>$1B).

### Market Trends
- Analyze Bitcoin price trends for specific timeframes (e.g., January 2025).
- Calculate oil price volatility (annual max-min difference).
- Determine annual average oil prices and COVID-era (2020) price crashes.

### Cross-Market Join Queries
- Compare Bitcoin vs. Oil average prices for 2025.
- Correlate Bitcoin closing prices with Crude Oil prices on identical dates.
- Compare NASDAQ and Ethereum daily price trends for 2025.
- Multi-join analysis: Daily comparison of S&P 500, Oil, and Bitcoin.

---

## Streamlit Application Structure

### Page 1: Filters and Data Exploration
- Dynamic date range filters.
- Summary metrics for Bitcoin, Oil, S&P 500, and NIFTY averages.
- Integrated daily market snapshot using SQL JOINs.

### Page 2: SQL Query Runner
- Dropdown selection for predefined analytical queries.
- Real-time execution and display of SQL results in tabular format.

### Page 3: Top Crypto Analysis
- Detailed drill-down for selected top cryptocurrencies.
- Line charts for daily price trends and historical data tables.

---

## Technical Stack
- Language: Python
- Libraries: Streamlit, Pandas, Yfinance
- Database: SQL (MySQL / PostgreSQL / SQLite)
- API: CoinGecko API
- Data Format: CSV, JSON

---

## Expected Results
- Successful extraction and pagination of CoinGecko API records.
- Automated SQL schema creation and data insertion via Python DB-API.
- A fully functional three-page Streamlit dashboard for financial BI.
- Clean, transformed datasets stored in a relational structure.
