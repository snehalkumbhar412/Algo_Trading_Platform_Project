# <u>**Algo-Trading System with ML & Automation**</u>



---

## <u>**Short Description / Purpose**</u>

This system integrates machine learning and rule-based trading strategies with automation tools to create an end-to-end algo-trading solution. It fetches live market data, generates trade signals, executes backtests, logs trades to Google Sheets, and sends real-time alerts via Telegram. The system is modular, interpretable, and suitable for both research and deployment.

---

## <u>**Tech Stack**</u>

* 🐍 **Programming & Core Libraries:** Python, Pandas, NumPy
* 🤖 **Machine Learning:** Scikit-learn (Random Forest), XGBoost
* 📈 **Data Retrieval:** Yahoo Finance (`yfinance`)
* 📊 **Visualization:** Matplotlib
* 🔔 **Automation & Logging:** Google Sheets API, Telegram API
* ⚙️ **Backtesting:** Custom Python scripts

---

## <u>**Data Source**</u>

* **Source:** Yahoo Finance (via `yfinance` API)
* **Data:** Historical price data (OHLCV - Open, High, Low, Close, Volume) for user-defined stock tickers (e.g., 'AAPL', 'TSLA', 'MSFT').
* **Timeframe:** User-defined historical periods (e.g., last 6 months).

---

## <u>**Project Implementation (Features)**</u>

**Part 1: Market Data Pipeline**

The `fetch_data()` function is responsible for retrieving historical stock price data from Yahoo Finance. This module serves as the foundation for all subsequent steps, ensuring accurate and timely access to market data.

* **Features:**
    * **Date Range Selection:** Pulls data for a user-defined historical period.
    * **OHLCV Data:** Retrieves Open, High, Low, Close, and Volume.
    * **Ticker Support:** Compatible with multiple stock symbols.
    * **Clean Output:** Returns structured pandas DataFrame.

**Part 2: Signal Generation Module**

This module enhances raw price data with key technical indicators and uses them to generate actionable trading signals. It supports both rule-based and ML-assisted logic.

* **Features:**
    * **Indicator Calculation:** Adds RSI, moving averages (SMA/EMA).
    * ⚡ **Crossover Detection:** Implements RSI thresholds and MA crossovers.
    * **Hybrid Strategy Support:** Blends rule-based logic with ML outputs.
    * **Signal Labeling:** Marks Buy (1), Sell (-1), and Hold (0).
    * **NaN Handling:** Ensures logic runs on valid, non-null data.

**Part 3: Backtesting Engine**

The backtesting module evaluates the performance of the trading strategy over historical data, simulating trades and calculating key performance metrics.

* **Features:**
    * ⏳ **Historical Simulation:** Replays trades over selected time ranges.
    * **PnL Calculation:** Computes profit and loss from signals.
    * **Performance Metrics:** Includes win rate, total return, Sharpe ratio, etc.
    * **Trade Tracking:** Logs entry/exit points and timestamps.

**Part 4: Visualization Tools**

This module displays the closing price, trading signals, and technical indicators using `matplotlib` to visually analyze strategy performance.

* **Features:**
    * **Price Line Plot:** Plots the asset’s closing price over time.
    * **Buy/Sell Markers:** Highlights buy (↑) and sell (↓) signals on the chart.
    * **Indicator Overlays:** Adds moving averages or RSI.
    * **Date Axis Formatting:** Auto-rotates dates for readability.

**Part 5: Logging Utility**

This module connects to Google Sheets via the Google Cloud Sheets API to log trade data, signals, and performance metrics automatically.

* **Features:**
    * **Service Account Authentication:** Uses a secure JSON key from Google Cloud.
    * **Sheets API Integration:** Interacts directly with Google Sheets.
    * **Trade Log Automation:** Appends each trade as a new row.
    * **Real-Time Sync:** Updates logs live during strategy execution.

**Part 6: ML Model Training**

This module combines supervised machine learning (e.g., XGBoost) with rule-based strategies to generate reliable hybrid trading signals.

* **Features:**
    * **Supervised Learning:** Trains classification models on labeled historical data.
    * **Signal Labeling:** Uses rule-based logic to create training targets.
    * **Feature Engineering:** Uses technical indicators as input features.
    * **Model Evaluation:** Assesses accuracy, precision, recall, and F1-score.
    * **Hybrid Signal Logic:** Combines model predictions with rule filters.

**Part 7: Telegram Bot Alert**

This module integrates the system with Telegram, allowing for real-time alerts for Buy, Sell, and Hold signals via a Telegram bot.

* **Features:**
    * **Bot Integration:** Connects to the Telegram API using a secure bot token.
    * **Chat ID Configuration:** Sends messages to a specific personal or group chat.
    * **Real-Time Alerts:** Sends instant notifications for new signals.
    * **Trade Details:** Includes signal type, stock name, price, and timestamp.

---

## <u>**Conclusion**</u>

This project demonstrates a complete, end-to-end algorithmic trading system. By integrating a real-time data pipeline, a hybrid (ML + rules) signal generator, a backtesting engine, and automated logging/alerting, it provides a robust solution for both strategy research and live deployment.

---

## <u>**System Workflow (Step-by-Step)**</u>

1.  **Fetch Data (Yahoo Finance):** Retrieve historical OHLCV data for selected assets.
2.  **Add Indicators (RSI, SMA, etc.):** Compute technical indicators (RSI, SMAs) and store them as features.
3.  **Label Signals (Rule-Based Logic):** Apply logic (e.g., RSI or MA crossover) to label data for ML training.
4.  **Train ML Model (e.g., RF/XGB):** Train a supervised model (Random Forest/XGBoost) on the indicators and labels.
5.  **Generate Signals (Hybrid Logic):** Combine model predictions with rule-based filters for final, high-confidence signals.
6.  **Backtesting (Performance Evaluation):** Simulate trades on historical data to assess PnL, Sharpe ratio, and drawdown.
7.  **Visualization (Matplotlib Charts):** Plot price, indicators, and signals for visual analysis and refinement.
8.  **Google Sheets Logging:** Automatically log all trades and performance metrics to Google Sheets via API.
9.  **Telegram Alerts (Optional):** Send real-time buy/sell notifications to Telegram for live monitoring.

---

## <u>**Workflow Diagram**</u>
