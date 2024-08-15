# RSI-WILLR-Stop-Loss-Optimizer-for-BTC-USDT-Trading-Strategy
Daaaaaaaaaaaaaaamn this works!

Date:
15th August 2024

1. Introduction
The "RSI-WILLR Stop-Loss Optimizer" is a Python-based tool designed to optimize a trading strategy that combines the Relative Strength Index (RSI) and the Williams %R (WILLR) technical indicators. This tool is specifically tailored for the BTC/USDT trading pair and allows for comprehensive parameter tuning, including the optimization of stop-loss values. The optimizer is built to facilitate systematic and robust backtesting, ensuring that the strategy is both profitable and risk-managed.

2. Strategy Overview
2.1. Relative Strength Index (RSI)
The RSI is a momentum oscillator that measures the speed and change of price movements. It oscillates between 0 and 100 and is typically used to identify overbought or oversold conditions in a market. In this strategy:

Buy Signal: RSI crosses below a certain threshold (indicating an oversold condition).
Sell Signal: RSI crosses above a certain threshold (indicating an overbought condition).
2.2. Williams %R (WILLR)
The Williams %R is a momentum indicator that moves between 0 and -100, providing insights into potential market reversals. It is often used to detect overbought or oversold levels:

Buy Signal: Williams %R crosses below a specific threshold (indicating a potential reversal from oversold conditions).
Sell Signal: Williams %R crosses above a specific threshold (indicating a potential reversal from overbought conditions).
2.3. Stop-Loss Mechanism
The stop-loss is a risk management tool that automatically triggers a sell order when the price drops below a predetermined percentage from the entry point. This mechanism is critical for protecting against significant losses during adverse market movements.

3. Optimization Framework
3.1. Parameter Ranges
The optimizer tests a wide range of parameters to identify the most effective combination for the RSI, WILLR, and stop-loss settings:

RSI Buy Threshold: 5 to 95 (in steps of 5)
RSI Sell Threshold: 40 to 95 (in steps of 5)
WILLR Buy Threshold: -100 to -5 (in steps of 5)
WILLR Sell Threshold: -100 to -5 (in steps of 5)
Stop-Loss: -30% to -1% (in steps of 1%)
3.2. Cumulative Profit Calculation
The script evaluates each parameter combination by calculating the cumulative profit over the backtested period. Cumulative profit is the sum of all profits and losses from each trade executed under a specific parameter set.

3.3. Best Parameter Selection
The optimizer selects the parameter set that yields the highest cumulative profit while also considering other metrics such as the number of trades, win rate, and maximum drawdown.

4. Technical Details
4.1. Script Components
The script is composed of several key components:

RSIWILLRStrategy Class: Implements the strategy logic, including the calculation of RSI and WILLR indicators, signal generation, and trade execution with stop-loss.
fetch_ohlcv Function: Retrieves historical OHLCV (Open, High, Low, Close, Volume) data for the BTC/USDT pair using the CCXT library.
manual_hyperopt Function: Conducts the hyperoptimization by testing different parameter combinations and selecting the optimal set based on performance metrics.
4.2. Data Handling
Data Source: Binance exchange, accessed via the CCXT library.
Candle Data: The script fetches 336 candles with a 30-minute timeframe, providing a robust dataset for backtesting.
Initial Balance: The simulation starts with a 500 USDT balance, reflecting a realistic trading scenario.
4.3. Performance Metrics
The script outputs several key performance metrics for each parameter set tested:

Cumulative Profit: Total profit after all trades are executed.
Number of Trades: Total trades executed during the backtest.
Win Rate: Percentage of profitable trades.
Maximum Drawdown: The largest peak-to-trough decline during the backtest.
Final Balance: The remaining balance after all trades are completed.
5. Usage Instructions
5.1. Prerequisites
Ensure you have Python 3.x installed along with the required libraries:

bash
Copy code
pip install pandas numpy ccxt
5.2. Running the Script
Save the script as RSI_WILLR_StopLoss_Optimizer.py and execute it via the command line:

bash
Copy code
python RSI_WILLR_StopLoss_Optimizer.py
5.3. Output
The script will print the best-performing parameter set and the associated performance metrics. This output includes the optimal RSI thresholds, WILLR thresholds, and stop-loss percentage.

6. Conclusion
The RSI-WILLR Stop-Loss Optimizer is a powerful tool for traders looking to refine their strategies through systematic backtesting and optimization. By leveraging this script, traders can identify the most profitable and risk-averse settings for the RSI, WILLR, and stop-loss parameters, specifically tailored for the BTC/USDT trading pair.
