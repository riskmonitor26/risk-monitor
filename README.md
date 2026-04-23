# Credit Risk Monitor

A daily Python-based monitoring tool that tracks key financial indicators, generates price tables with moving averages, and creates professional PDF reports with charts.

## Features

- Downloads historical data for major indices, volatility, Treasury yields, high-yield bonds, and financial sector ETFs
- Calculates percentage changes (1W, 1M, 1Q, 1Y, 5Y)
- Shows 52-week high/low range
- Plots with Moving Averages (9, 20, 50, 200), MACD, RSI, and Volume
- Generates clean PDF reports with tables and embedded charts
- Automatic temporary file cleanup

## Tickers Currently Monitored

| Ticker     | Description                              |
|------------|------------------------------------------|
| DX-Y.NYB   | US Dollar Index (DXY)                    |
| ^VIX       | CBOE Volatility Index (Market Fear)      |
| ^IRX       | 13-Week Treasury Bill Yield              |
| ^FVX       | 5-Year Treasury Yield                    |
| ^TNX       | 10-Year Treasury Yield                   |
| ^TYX       | 30-Year Treasury Yield                   |
| ^IXF       | Financial Sector Index                   |
| HYG        | iShares iBoxx High Yield Corporate Bond ETF |
| XLF        | Financial Select Sector SPDR ETF         |
| KRE        | SPDR S&P Regional Banking ETF            |

## Requirements

- Python 3.8+
- Required packages:
  ```bash
  pip install yfinance pandas matplotlib reportlab


## How to Run
1. Clone or download the repository
2. Run the main script:
   ```bash
   python CreditRisk_Monitor.ipynb

├── CreditRisk_Monitor.ipynb     # Main script
├── temp/                      # Temporary plots (auto-deleted)
└── CreditRisk_Monitor_YYYYMMDD.pdf   # Generated report
