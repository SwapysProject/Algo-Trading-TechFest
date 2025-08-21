# EMA Crossover Trading Strategy

A Python-based algorithmic trading strategy implementation using Exponential Moving Average (EMA) crossover signals with target profit and stop-loss mechanisms.

## Overview

This project implements a systematic trading strategy for stock analysis using the EMA crossover technique. The strategy uses 50-day and 200-day exponential moving averages to generate buy/sell signals, with built-in risk management through target profit and stop-loss levels.

## Features

- **EMA Crossover Strategy**: Uses 50-day (short) and 200-day (long) exponential moving averages
- **Risk Management**: Configurable target profit (2%) and stop-loss (0.5%) levels
- **Performance Metrics**: Calculates total return, accuracy, and Sharpe ratio
- **Trade Logging**: Detailed CSV export of all executed trades
- **Backtesting Simulation**: Tests strategy on historical stock data

## Requirements

```
pandas
numpy
```

## Installation

1. Clone or download the project files
2. Install required dependencies:
```bash
pip install pandas numpy
```

## File Structure

```
project/
├── script.py                              # Main trading strategy script
├── Training Dataset/
│   └── Adani Enterprises.csv             # Stock data file
└── ema_trade_log_with_results_3.csv      # Generated trade log (after execution)
```

## Data Format

The CSV file should contain the following columns:
- **Date**: Trading date
- **Open**: Opening price
- **High**: Highest price of the day
- **Low**: Lowest price of the day
- **Close**: Closing price

## Strategy Logic

### Buy Signal
- Triggered when Short EMA (50-day) crosses above Long EMA (200-day)
- Executes only if sufficient cash is available
- Sets target price at 2% above buy price
- Sets stop-loss at 0.5% below buy price

### Sell Signal
Sells position when any of these conditions are met:
1. **Target Hit**: Price reaches 2% profit target
2. **Stop-Loss Hit**: Price falls to 0.5% loss level
3. **EMA Crossover**: Short EMA crosses below Long EMA

## Configuration Parameters

```python
short_window = 50          # Short-term EMA period
long_window = 200          # Long-term EMA period
target_pct = 0.02          # Target profit percentage (2%)
stoploss_pct = 0.005       # Stop-loss percentage (0.5%)
initial_cash = 1000        # Starting capital in ₹
risk_free_rate_annual = 0.05  # Risk-free rate for Sharpe ratio (5%)
```

## Usage

1. Place your stock data CSV file in the `Training Dataset/` folder
2. Update the file path in the script if necessary
3. Run the script:
```bash
python script.py
```

## Output Metrics

The script generates the following performance metrics:

- **Initial Cash**: Starting investment amount
- **Final Portfolio Value**: Total value at strategy completion
- **Total Return**: Percentage return on investment
- **Total Trades**: Number of trades executed
- **Winning Trades**: Number of profitable trades
- **Accuracy**: Percentage of winning trades
- **Sharpe Ratio**: Risk-adjusted return metric

## Sample Output

```
Initial Cash: ₹1000
Final Portfolio Value: ₹1250.45
Total Return: 25.05%
Total Trades: 15
Winning Trades: 9
Accuracy: 60.00%
Sharpe Ratio: 1.35
```

## Trade Log

All trades are automatically saved to `ema_trade_log_with_results_3.csv` with the following information:
- Date of trade
- Action (Buy/Sell)
- Execution price
- Target price
- Stop-loss price
- Trade result (Target Hit/Stoploss Hit/Crossover)

## Strategy Advantages

- **Trend Following**: Captures major price movements
- **Risk Management**: Built-in profit targets and stop-losses
- **Systematic Approach**: Removes emotional decision-making
- **Backtesting Capability**: Tests strategy on historical data

## Strategy Limitations

- **Lagging Indicators**: EMAs are based on past prices
- **Sideways Markets**: Poor performance in non-trending markets
- **Whipsaws**: Multiple false signals in volatile conditions
- **Single Asset**: Currently designed for individual stock analysis

## Customization

To modify the strategy:

1. **Change EMA Periods**: Adjust `short_window` and `long_window`
2. **Risk Parameters**: Modify `target_pct` and `stoploss_pct`
3. **Capital**: Change `initial_cash` amount
4. **Risk-Free Rate**: Update `risk_free_rate_annual` for Sharpe calculation

## Risk Disclaimer

This is a backtesting tool for educational and research purposes only. Past performance does not guarantee future results. Always conduct thorough analysis and consider consulting financial advisors before making investment decisions.

## License

This project is open source and available under standard terms.