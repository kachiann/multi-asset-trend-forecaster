# 📈 Multi-asset Trend Forecaster

> Progressively built Deep Learning models for short-term market trend prediction across multiple ETF asset classes.

---

## Overview

This project explores the application of deep learning to financial time series forecasting. Starting from simple feedforward architectures and progressively advancing to recurrent and unified multi-output models, the goal is to predict short-term market trends across five major asset classes — and ultimately evaluate an asset allocation strategy based on those predictions.

---

## Asset Classes

| Asset Class     | ETF Name                              | Symbol |
|-----------------|---------------------------------------|--------|
| Equity          | SPDR S&P 500 ETF                      | `SPY`  |
| Fixed Income    | iShares 20+ Year Treasury Bond ETF    | `TLT`  |
| Cash-like       | iShares 1-3 Year Treasury Bond ETF    | `SHY`  |
| Precious Metals | SPDR Gold Shares                      | `GLD`  |
| Crude Oil       | Invesco DB Oil Fund                   | `DBO`  |

---

## Project Structure

```
multi-asset-trend-forecaster/
│
├── data/
│   └── raw/                    # Downloaded ETF price data (via yfinance)
│
├── notebooks/
│   ├── 01_eda.ipynb             # Exploratory Data Analysis
│   ├── 02_feedforward.ipynb     # Feedforward Neural Networks
│   ├── 03_cnn.ipynb             # Convolutional Neural Networks
│   ├── 04_rnn_lstm.ipynb        # Recurrent Architectures (RNN / LSTM)
│   └── 05_multi_output.ipynb    # Unified Multi-Output Model
│
├── src/
│   ├── data_loader.py           # Data download & preprocessing
│   ├── features.py              # Feature engineering
│   ├── models/
│   │   ├── feedforward.py
│   │   ├── cnn.py
│   │   ├── rnn.py
│   │   └── multi_output.py
│   └── strategy.py              # Asset allocation strategy & backtesting
│
├── results/
│   ├── figures/                 # Plots and visualizations
│   └── metrics/                 # Model evaluation outputs
│
├── requirements.txt
└── README.md
```

---

## Methodology

### Step 1 — Data Collection & EDA
- Download daily prices for each ETF using `yfinance`
- **Training period**: January 2010 – December 2016
- **Validation period**: January 2017 – December 2017
- **Test period**: January 2018 – December 2022
- Exploratory analysis: summary statistics, return distributions, stationarity tests (ADF), seasonality, and correlation structure

### Step 2 — Feedforward & CNN Models
- Apply shallow feedforward networks to each asset class independently
- Apply 1D CNN architectures on rolling windows of price/return data
- Evaluate in-sample and out-of-sample trend prediction accuracy

### Step 3 — Recurrent Architectures
- Build RNN and LSTM models to capture temporal dependencies
- Compare sequence-based learning against static window approaches

### Step 4 — Unified Multi-Output Model
- Combine all asset classes into a single shared-backbone model
- Use multi-output heads to simultaneously predict trends for all ETFs
- Evaluate cross-asset learning transfer

### Step 5 — Strategy Backtesting
- Translate model predictions into a long/short/cash asset allocation strategy
- Evaluate out-of-sample performance: cumulative returns, Sharpe ratio, max drawdown
- Benchmark against equal-weight and buy-and-hold strategies

---

## Installation

```bash
git clone https://github.com/kachiann/multi-asset-trend-forecaster.git
cd multi-asset-trend-forecaster
pip install -r requirements.txt
```

---

## Results Summary

> *(To be updated as experiments are completed)*

| Model               | Asset   | Accuracy | Sharpe (OOS) |
|---------------------|---------|----------|--------------|
| Feedforward         | SPY     | —        | —            |
| CNN                 | SPY     | —        | —            |
| LSTM                | SPY     | —        | —            |
| Multi-Output        | All     | —        | —            |

---

## Key References

- LeCun, Y., Bengio, Y., & Hinton, G. (2015). *Deep learning*. Nature.
- Fischer, T., & Krauss, C. (2018). *Deep learning with long short-term memory networks for financial market predictions*. European Journal of Operational Research.
- Gu, S., Kelly, B., & Xiu, D. (2020). *Empirical asset pricing via machine learning*. Review of Financial Studies.

---

## License

This project is developed for academic purposes.

---

*Built with Python · TensorFlow/PyTorch · yfinance*
