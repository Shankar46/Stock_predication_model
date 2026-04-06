Stock Price Prediction using Random Forest & Technical Indicators
This repository contains a Python-based machine learning pipeline that predicts stock price movements (specifically for ONGC.NS) using historical data and various technical indicators. The model utilizes a RandomForestRegressor and live data fetching via the yfinance API.

🚀 Overview
The script performs the following steps:

Data Acquisition: Downloads 1 year of historical daily data for the specified ticker.

Feature Engineering: Calculates a suite of technical indicators using TA-Lib:

Moving Averages (SMA, EMA)

Relative Strength Index (RSI)

Moving Average Convergence Divergence (MACD)

Average Directional Index (ADX)

Bollinger Bands

Average True Range (ATR)

Preprocessing: Handles missing values and scales features using StandardScaler.

Modeling: Trains a Random Forest Regressor on historical trends.

Live Prediction: Fetches real-time minute-level data to predict the closing price for the current time interval.

🛠 Prerequisites
Before running the script, ensure you have the following installed:

1. TA-Lib (Technical Analysis Library)
This script relies on TA-Lib. It can be tricky to install via pip directly on some systems.

Windows: Download the pre-compiled .whl file from here and install it using pip install <filename>.whl.

macOS/Linux: Use Homebrew or your package manager:

Bash
brew install ta-lib
2. Python Dependencies
Install the required Python packages:

Bash
pip install yfinance pandas numpy scikit-learn pytz
📂 Project Structure
main.py: The core script containing data processing, model training, and live prediction.

README.md: Project documentation.

📈 Usage
Simply run the script to train the model and see the latest prediction:

Bash
python main.py
Configuration
You can modify the ticker variable in the script to track different stocks:

Python
ticker = 'AAPL' # Change to any yfinance compatible ticker
📊 Model Details
The model treats the stock prediction as a regression problem:

Training Set: 80% of the historical daily data (sequential split to preserve time-series integrity).

Test Set: 20% of the historical daily data.

Evaluation: Outputs the Mean Squared Error (MSE) to gauge accuracy.

⚠️ Disclaimer
This project is for educational purposes only. Stock market investments carry inherent risks. This model should not be used as the sole basis for financial decisions. Past performance does not guarantee future results.
