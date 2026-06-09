# Synthetic Data Modeling Test

**A comprehensive regression modeling project comparing OLS (with piecewise linear splines) vs. tree-based models (Random Forest & XGBoost) on synthetic data.**

## 📋 Project Overview

This repository contains a full modeling workflow on a **synthetic dataset** (`Modeling Test Data.csv`) designed with known **piecewise linear relationships** in `var_3` and `var_9`.

The goal was to:
- Perform thorough **EDA** (distributions, correlations, scatter plots)
- Build and iterate on **OLS models** (linear → quadratic → dummy variables → piecewise splines)
- Compare performance with **Random Forest** and **XGBoost**
- Demonstrate how a well-specified linear model can outperform black-box tree models when the true data-generating process is known

**Final Best Model**: Piecewise OLS (R² ≈ **0.998**, Test MAE ≈ **0.445**)

## 📊 Dataset

- **File**: `Modeling Test Data.csv`
- **Size**: 10,000 rows × 11 columns
- **Target**: `y`
- **Features**: `var_1` to `var_10` (mixture of continuous and categorical)

**Key characteristics discovered**:
- Strong linear and quadratic effects in `var_2`, `var_3`, and `var_9`
- Piecewise linear behavior in `var_3` and `var_9` (structural breaks at 0 and 200k for `var_3`; 0 / 100k / 200k for `var_9`)
- `var_10` is categorical (5 levels)

## 🛠️ Models Built & Results

| Model                          | Test R²   | Test MAE   | Test RMSE  | Notes |
|--------------------------------|-----------|------------|------------|-------|
| **Piecewise OLS (final)**      | **0.9972**| **0.4455** | **0.8525** | **Best overall** |
| XGBoost                        | 0.9914    | 0.8554     | 1.5099     | Strong but behind OLS |
| Random Forest                  | 0.9512    | 2.1941     | 3.5883     | Decent |
| Quadratic OLS + var_10 dummy   | 0.9179    | 3.7262     | 4.6535     | Good baseline |

**Why the piecewise OLS won**: It directly encodes the true piecewise structure of the synthetic data, making it extremely accurate and highly interpretable.

## 📁 Repository Structure

├── Modeling Test.ipynb          # Main Jupyter notebook (full workflow)
├── Modeling Test Data.csv       # Synthetic dataset
├── requirements.txt             # Python dependencies
├── README_Modelling_Test.md

