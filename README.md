# Cross-Market Analysis: Crypto, Oil & Stocks with SQL and Streamlit

project deployment can be found [here](https://cross-market-analysis---cma-dcvhere.streamlit.app/)

## Project Overview
*   **Domain:** Financial Analytics & Business Intelligence (BI)
*   **Objective:** Compare cryptocurrency behavior against traditional assets (oil, stock indices) to evaluate if crypto acts as "digital gold" or an independent asset class.
*   **Core Tasks:** Identify patterns, correlations, and relative performance across these markets over recent years.

## Tech Stack & Skills
*   Python (Pandas, API requests, Data Cleaning)
*   SQL (Database Design, Complex Queries, Joins)
*   Streamlit (Dashboarding, UI creation)
*   ETL Workflow (Extract, Transform, Load)

## Business Use Cases
*   **Investment Research:** Determine if Bitcoin moves with or against oil and stock markets.
*   **Risk Management:** Compare crypto volatility to traditional assets for portfolio management.
*   **Macro-Economic Analysis:** Study the impact of global events (oil spikes, stock crashes) on crypto prices.
*   **Cross-Market Trading Strategies:** Test hypotheses (e.g., buying BTC when oil falls, hedging with S&P 500 during downturns).
*   **Educational BI Tool:** Demonstrate data warehousing, SQL analytics, and financial relationships.

## Data Sources & Collection
*   **Cryptocurrency (CoinGecko API):** 
    *   Metadata for top 250 coins based on market capitalization.
    *   1-year historical daily prices for the Top 3 coins (e.g., Bitcoin, Ethereum).
*   **Oil Prices (WTI Crude):**
    *   Daily prices loaded from a public GitHub CSV dataset (Jan 2020 to Jan 2026).
*   **Stock Prices (Yahoo Finance API):**
    *   Historical daily data for indices: S&P 500 (^GSPC), NASDAQ (^IXIC), NIFTY (^NSEI) (Jan 2020 to Sept 2025).

## Database Architecture
*   **Relational Database:** Compatible with MySQL, PostgreSQL, or SQLite via Python connectors.
*   **Tables Designed:**
    *   `cryptocurrencies`: Stores metadata (id, symbol, name, market cap, supply, ATH, ATL).
    *   `crypto_prices`: Daily historical prices (linked via foreign key to cryptocurrencies).
    *   `oil_prices`: WTI crude oil daily prices.
    *   `stock_prices`: Daily OHLCV data for selected stock indices.

## Dashboard Features (Streamlit)
*   **Page 1: Market Overview**
    *   Date range filters for dynamic data exploration.
    *   KPIs: Average prices for Bitcoin, Oil, S&P 500, and NIFTY.
    *   Daily Market Snapshot: Joined table comparing daily prices across all assets simultaneously.
*   **Page 2: SQL Query Runner**
    *   Dropdown menu to select and execute predefined cross-market SQL queries (e.g., finding highest price differences, average prices).
    *   Live execution of analytics directly on the connected SQL database.
*   **Page 3: Top 3 Crypto Analysis**
    *   Specific coin selection and date filtering.
    *   Visualization of daily price trends and detailed price data tables.

## Expected Outcomes
*   Automated extraction and ETL pipeline handling API pagination and raw datasets.
*   Transformed datasets stored in a well-structured relational SQL schema.
*   A fully functional, multi-page Streamlit application for interactive cross-market data exploration.
cross_market_analysis_explainer.md
Displaying cross_market_analysis_explainer.md.
