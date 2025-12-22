# Quantitative Trading Framework & Intraday Momentum Strategy
### *Microstructure-Based Signal Logic with Intrabar Execution Simulation*

## 📌 Project Overview
This project is a high-frequency backtesting engine developed to evaluate a momentum strategy based on **Market Microstructure (CVD)** and **Trend Regimes**. Unlike standard backtesters, this framework utilizes high-resolution 1-minute data and a custom execution engine to simulate realistic price action within a single candle, ensuring the integrity of risk-management triggers.

## 🚀 Key Features
* **Data Engineering:** Automated ingestion of multi-year 1-minute datasets via **Alpaca API**.
* **Microstructure Signals:** Uses **Cumulative Volume Delta (CVD)** momentum to track institutional buying/selling pressure.
* **Execution Integrity:** Custom **Intrabar Exit Engine** that accounts for price paths (O-L-H-C) to calculate realistic slippage and trade exits.
* **Performance Analytics:** Institutional-grade reporting including **Sharpe Ratio**, **Max Drawdown**, and **Benchmark Comparison**.

## 📊 Backtesting Results (Summary)
The following results were generated over a multi-year period using a 1% risk-per-trade model and a 2:1 Reward-to-Risk ratio.

| Metric | QQQ (Nasdaq 100) | SPY (S&P 500) |
| :--- | :--- | :--- |
| **Total Return** | **141.59%** | 65.42% |
| **Benchmark (Buy & Hold)** | 117.80% | **76.41%** |
| **Sharpe Ratio (Rf=5%)** | **1.34** | 0.71 |
| **Max Drawdown** | **-7.79%** | -8.72% |
| **Profit Factor** | 1.24 | 1.21 |
| **Number of Trades** | 1,230 | 819 |

*Figure 1: Strategy Equity Curve (Green) significantly outperforming QQQ Buy & Hold (Gray) with a high Sharpe Ratio of 1.34.*

## 🛠 Strategy Architecture
1. **Regime Filter:** 50-period Daily EMA to define the primary market direction.
2. **Value Baseline:** Entry signals only valid when price is on the correct side of the **VWAP**.
3. **Trigger:** Confluence of CVD momentum and trend direction.
4. **Risk Control:** Stop-loss and Take-profit orders simulated at the intrabar level to maintain a mathematical 2:1 R:R profile.

## 📂 Technical Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib, Alpaca-Historical-Data
* **Data Format:** Apache Parquet
