# Comparing Methods for Estimating Lifetime Default and Prepayment Rates

This repository contains the Python code used in the Substack post:  
**"Why Simple Snapshot Rates Can Seriously Mislead You in Credit Risk Modeling"**

## Overview

The code compares **four different methods** for estimating default and prepayment rates using simulated mortgage data across different observation windows (3 to 15 years):

| Method | Description |
|--------|-------------|
| **Method 1** | Snapshot Average (Loan-month records) |
| **Method 2** | Unique Loan Average (last record per loan) |
| **Method 3** | Kaplan-Meier Estimator (separate survival curves) |
| **Method 4** | Cumulative Incidence Function (Competing Risks) |

The goal is to demonstrate how simple snapshot-based methods can significantly underestimate lifetime default and prepayment rates, and how survival analysis techniques (especially competing risks) provide more accurate estimates.

## Key Findings

- Simple snapshot averages (Methods 1 & 2) tend to **underestimate** true long-term rates.
- Kaplan-Meier (Method 3) performs better but can slightly **overestimate** due to treating competing events as censoring.
- The **Cumulative Incidence Function** (Method 4) generally provides the most accurate results by properly modeling default and prepayment as competing risks.

## Files in This Repository

- `compare_4_methods_default_prepay.py` — Main script
- `default_rate_comparison.png` — Comparison chart for default rates
- `prepay_rate_comparison.png` — Comparison chart for prepayment rates
- `comparison_4_methods_manual.csv` — Output results table

## How to Run

1. Place your data file (`mortgage_panel.csv`) in the same folder as the script.
2. Run the script:

```bash
python compare_4_methods_default_prepay.py


## Data

The full simulated dataset used in this analysis is large (0.569 GB when unzipped).  
Due to GitHub file size limits, the data file is **not included** in this repository.

If you would like to access the data, please contact me at:  
**llvvzhang@yahoo.com**
