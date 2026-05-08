Credit Stress Prediction Using XGBoost and Neural Networks

🧠 Overview
This project builds a machine learning system to predict credit market stress events using macro-financial indicators, equity indices, and credit market signals.

The goal is to model and detect rare stress conditions in financial markets using a combination of:

Feature engineering (technical indicators + spreads)
XGBoost classifier
Neural network classifier
Model interpretability (SHAP)
Threshold-based decision system

📁 Data
The dataset is constructed from publicly available financial time series downloaded via Yahoo Finance.

📈 Equity Indices
Ticker	Description
SPY	    ETF tracking the S&P 500 index
^GSPC	  Broad U.S. large-cap equity market index
^IXIC	  Technology-heavy U.S. equity index
^DJI	  Blue-chip U.S. industrial equity index

💳 Credit & Financial Markets
Ticker	Description
HYG	    High-yield corporate bond ETF (credit risk proxy)
KRE	    Regional banking sector ETF
XLF	    U.S. financial sector ETF

📉 Interest Rates & Yield Curve
Ticker	Description
^IRX	  Short-term U.S. Treasury yield
^FVX	  Intermediate-term Treasury yield
^TNX	  Benchmark U.S. long-term Treasury yield
^TYX	  Long-duration Treasury bond yield

🛢️ Commodities
Ticker	Description
GC=F	  Gold futures contract
SI=F	  Silver futures contract
CL=F	  WTI crude oil futures contract

📊 Volatility
Ticker	Description
^VIX	  Market-implied equity volatility (“fear index”)

💱 Foreign Exchange
Ticker	    Description
DX-Y.NYB	  U.S. dollar strength versus major global currencies

Time range:
2006 – Present

⚙️ Feature Engineering
The model includes engineered financial features:

Technical Indicators
Moving Averages (MA9, MA20, MA60)
MACD (EMA12 - EMA26)
RSI (14-day)
Trend direction and ratio features
Macro Features
Yield curve spreads (TNX - IRX, TYX - TNX, etc.)
Equity breadth indicators (RSP / SPY)
Market stress proxies
Lag Features
10-day lagged versions of all features

🎯 Target Variable
Credit stress is defined as:

Conditions based on divergence between bond yields and credit spreads
Proxy rule combining trend signals from rates and credit ETFs
Credit_Stress = 1 if stress condition occurs, else 0

🤖 Models
1. XGBoost Classifier
max_depth=4
learning_rate=0.05
subsample=0.8
colsample_bytree=0.8
early stopping
2. Neural Network
Fully connected dense network
LeakyReLU activation
Binary classification output

📊 Evaluation Metric
The models are evaluated using:

Accuracy
Precision / Recall / F1-score
ROC-AUC
Precision-Recall AUC (AP score)

⚖️ Decision Threshold
Because of class imbalance (~10% positive class), the decision threshold is optimized instead of using the default 0.5.

Default threshold (0.5) is not suitable
Final selected threshold:
Threshold = 0.15

This aligns closely with the empirical event frequency in training data.

📈 Key Results
ROC-AUC: ~0.97 – 0.99
Average Precision (AP): ~0.91+
Strong separation between stress and non-stress regimes

📉 Visualizations
The project includes:

ROC Curve
Precision–Recall Curve
SHAP feature importance
Raw XGBoost score distribution
Tree visualization

🔍 Key Insight
This project demonstrates that:

Financial stress events can be modeled as a probabilistic ranking problem rather than a simple classification task.

The decision threshold acts as a risk calibration parameter, not a fixed constant.

🧪 Technologies Used
Python
XGBoost
TensorFlow / Keras
Scikit-learn
SHAP
Pandas / NumPy
Matplotlib / Seaborn
yfinance

🚀 Future Improvements
Probability calibration (Platt scaling / isotonic regression)
Regime-switching models
More robust macro features
Ensemble stacking (XGB + NN + linear model)
Walk-forward validation

📌 Author Notes
This project is intended as a quantitative research prototype demonstrating:

financial feature engineering
imbalanced classification handling
interpretable ML methods
threshold-based risk modeling
