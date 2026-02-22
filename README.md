PROJECT IMPLEMENTATION REPORT: CROSS-MARKET ANALYTICS PLATFORM

I. PROJECT OVERVIEW
This project establishes a comprehensive data pipeline and visualization dashboard to analyze the correlation between Cryptocurrencies, Crude Oil, and Global Stock Indices. The primary objective is to determine how digital assets interact with traditional macro-economic indicators using SQL for data management and Streamlit for business intelligence.

II. CORE FUNCTIONS AND STEP-BY-STEP IMPLEMENTATION

STEP 1: MULTI-SOURCE DATA EXTRACTION
The project initiates by fetching live and historical data from three distinct sources:

    Cryptocurrency Data: Utilizing the CoinGecko API to extract market metadata for 250 coins and detailed 365-day historical price data for the top 3 market-cap assets.

    Oil Market Data: Importing WTI (West Texas Intermediate) daily price records from a remote CSV repository covering the period from 2020 to 2026.

    Stock Market Data: Leveraging the Yahoo Finance API (yfinance) to download historical daily OHLCV (Open, High, Low, Close, Volume) data for the S&P 500, NASDAQ, and NIFTY 50 indices.

STEP 2: DATA CLEANING AND TRANSFORMATION
Once extracted, the raw data undergoes processing via the Pandas library:

    Data Filtering: Selecting specific columns such as Market Cap, Circulating Supply, and All-Time Highs.

    Date Standardization: Converting various timestamp formats into a unified SQL-compatible DATE format (YYYY-MM-DD).

    Currency Normalization: Ensuring price comparisons are consistent across assets (INR/USD conversion where applicable).

STEP 3: RELATIONAL DATABASE SCHEMA DESIGN
To facilitate complex cross-market analysis, a structured SQL database is implemented with four primary tables:

    Table "cryptocurrencies": Acts as a master record for coin metadata.

    Table "crypto_prices": Stores time-series daily price data linked via Foreign Keys.

    Table "oil_prices": A specialized table for daily WTI crude benchmarks.

    Table "stock_prices": Captures high-resolution trading data for global indices.

STEP 4: AUTOMATED DATA INGESTION (ETL)
Using Python database connectors (such as sqlite3 or sqlalchemy), the system automates:

    Table Creation: Defining schemas with appropriate Data Types (DECIMAL for precision, BIGINT for volume).

    Record Insertion: Using cursor-based execution to populate tables with the transformed datasets.

STEP 5: ADVANCED SQL ANALYTICS
The project executes a variety of analytical queries to derive insights:

    Trend Analysis: Identifying Bitcoin's highest daily prices and annual volatility.

    Supply Metrics: Filtering coins based on circulating-to-total supply ratios.

    Join Operations: Performing INNER JOINS across different tables to compare, for example, the price of Bitcoin against the closing price of the S&P 500 on the same calendar date.

STEP 6: STREAMLIT DASHBOARD DEVELOPMENT
The final phase involves building a multi-page interactive web application:

    Dashboard Page: Features real-time filtering where users select date ranges to view average market snapshots (Bitcoin vs. Oil vs. Stocks).

    SQL Explorer: A dedicated interface for users to select and run predefined SQL queries, displaying results in an interactive table format.

    Asset Deep-Dive: A focused analysis page for specific top-tier cryptocurrencies, incorporating trend visualizations and data tables.

III. TECHNICAL REQUIREMENTS

    Programming: Python 3.x

    Database: SQL (MySQL, PostgreSQL, or SQLite)

    Libraries: Streamlit, Pandas, Requests, Yfinance

    API Access: CoinGecko Public API

IV. PROJECT TIMELINE AND SUBMISSION
The implementation is designed for a 14-day development cycle, concluding with a live evaluation and a project demonstration.
