# Currency & Risk Monitor

A Python-based currency exchange rate monitor and risk analysis tool.

## Project Overview
This project tracks exchange rates for major currencies against the US Dollar and highlights currencies with significant movements over different time periods (1 day, 1 week, 1 month, 3 months, 6 months, 1 year, etc.).

It generates:
- Daily and long-term exchange rate tables
- Risk highlight reports for currencies with large changes
- Visual trend charts grouped by exchange rate magnitude

## Features
- Fetches real-time and historical exchange rates
- Calculates percentage changes over multiple time horizons
- Identifies high-risk currencies based on movement thresholds
- Generates professional PDF reports with tables and charts
- Flexible observation periods (not fixed to 10 years)

## Technologies Used
- Python 3
- pandas
- requests
- plotly
- reportlab (for PDF generation)

## How to Run
1. Clone or download the repository
2. Run the main script:
   ```bash
   python currency_monitor.ipynb