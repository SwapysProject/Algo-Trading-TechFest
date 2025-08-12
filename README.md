🚀 Features
Cleans price data (removes commas, converts to numeric)

Calculates:

EMA (20 & 50)

RSI (14)

MACD + Signal line

Bollinger Bands (20-period)

ATR (14) — for dynamic stop-loss and target

Multi-signal confirmation: buys only when ≥ 3 out of 4 indicators agree

ATR-based dynamic targets & stop-loss

Tracks portfolio growth, accuracy, and trade log

Saves executed trades to advanced_trade_log.csv

Plots equity curve

📦 Requirements
Install dependencies before running:

text
pip install pandas numpy matplotlib
📂 Usage
Place your CSV dataset in the project folder.

Must contain at least: Date, Open, High, Low, Close

Optional: Volume

Example CSV format:

text
Date,Open,High,Low,Close,Volume
2024-01-01,150,155,148,152,100000
2024-01-02,152,158,150,157,120000
Edit the script to update the CSV file path:

python
file_path = "Training Dataset/Adani Enterprises.csv"
Run the script:

text
python trading_strategy.py
View Output:

Printed performance metrics

Portfolio value chart

advanced_trade_log.csv with trade details

📊 Output Examples
Console:

text
Initial Cash: ₹1000
Final Portfolio Value: ₹1185.50
Total Return: 18.55%
Total Trades: 12
Winning Trades: 8
Accuracy: 66.67%
Plot:

Line chart showing portfolio value over time

CSV (advanced_trade_log.csv):

text
Date,Action,Price,Target,Stoploss/Reason
2024-02-03,Buy,152,155.5,150.8
2024-02-07,Sell,156,Target Hit
⚙️ Strategy Logic
Buy Conditions (Need ≥ 3 True):

EMA(20) > EMA(50)

RSI > 50

MACD > MACD Signal

Price > Bollinger Middle Band

Sell Conditions:

Price hits ATR-based target

Price hits ATR-based stop-loss

🔍 Notes
This is a backtest — does not execute real trades.

Adjust parameters for different risk profiles.

Works with any timeframe (daily, hourly, etc.) if CSV data matches format.

If Volume column is missing, volume filter will be skipped automatically.
