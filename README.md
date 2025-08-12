# 📈 Advanced Technical Trading Strategy Backtester

## 🚀 Features
- **Cleans price data** — removes commas, converts to numeric.
- Calculates:
  - **EMA** (20 & 50)
  - **RSI** (14)
  - **MACD** + Signal Line
  - **Bollinger Bands** (20-period)
  - **ATR** (14) — for dynamic stop-loss & target
- **Multi-signal confirmation** — Buys only when **≥ 3 out of 4 indicators agree**.
- **ATR-based dynamic targets & stop-loss**.
- Tracks:
  - Portfolio growth
  - Accuracy
  - Trade log
- Saves executed trades to `advanced_trade_log.csv`.
