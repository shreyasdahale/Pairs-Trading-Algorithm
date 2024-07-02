# Pairs Trading Algorithm

## Project Overview
This project presents a pairs trading algorithm designed to exploit market inefficiencies by taking long and short positions in two highly correlated stocks. The algorithm was backtested using historical data for ONGC and ZOMATO stocks from January 2022 to April 2024, achieving a total return of 21.4%.

## Introduction
Pairs trading is a market-neutral strategy that involves matching a long position with a short position in two correlated stocks. The strategy aims to profit from the relative price movements of the two stocks, irrespective of the overall market direction.

## Key Features
- Identifies the best pair of stocks based on cointegration tests.
- Normalizes the spread between the two stocks to generate trading signals.
- Backtests the strategy on historical data to assess performance.
- Provides key performance metrics and risk analysis.

## Backtesting Results
- **Initial Portfolio Value**: ₹100,000
- **Final Portfolio Value**: ₹121,399.99
- **Total Return**: 21.4%
- **Period**: January 2022 - April 2024

## Conclusions Derived
- **Total Return**: 21.4%
- **Annualized Return (CAGR)**: 0.09%
- **Standard Deviation (Volatility)**: 0.033
- **Sharpe Ratio**: 2.69
- **Maximum Drawdown**: -0.031
- **Sortino Ratio**: 28.77
- **Calmar Ratio**: -2.899
- **Beta**: 0.547
- **Alpha**: 0.0535
- **Cumulative Returns of the strategy used on the 2 stocks**:
![output2](https://github.com/shreyasdahale/Pairs-Trading-Algorithm/assets/146332434/a0d53ea7-f1dc-4963-9984-8380af3b8410)

The algorithm demonstrated a positive risk-adjusted performance with manageable drawdown risk and lower sensitivity to market movements.

## Risk Analysis
- **Volatility**: The portfolio showed moderate volatility with a standard deviation of 0.033.
- **Drawdown Risk**: Maximum drawdown was 3.1%.
- **Sharpe Ratio**: 2.69, indicating strong risk-adjusted returns.
- **Sortino Ratio**: 28.77, highlighting excellent management of downside risk.
- **Calmar Ratio**: -2.899, indicating a need for improved drawdown risk management.
- **Beta**: 0.547, showing lower sensitivity to market movements.
- **Alpha**: 0.0535, indicating outperformance over the benchmark index.

## Recommendations
- **Risk Management**: Implement stop-loss strategies to manage and minimize drawdowns.
- **Diversification**: Consider diversifying into additional pairs to spread risk and reduce overall portfolio volatility.
- **Review Strategy**: Continuously review and adjust the trading algorithm to sustain and improve excess returns.
- **Performance Monitoring**: Regularly monitor the portfolio and make adjustments as needed to align with evolving market conditions and enhance performance.

## How to Use

### Step-by-Step Explanation
1. **Data Collection**
   - Fetch historical price data for a list of stocks. This data is used to calculate the spread and perform further statistical analysis. Create a dataframe with the stock data of interest.

2. **Identifying the Best Pair**
   - Calculate the p-values of cointegration tests between each pair of stocks. Cointegration tests determine whether two time series are likely to move together in the long term. Select the pair with the lowest p-value, as it indicates the strongest relationship.

3. **Calculating and Normalizing the Spread**
   - Calculate the spread between the two stocks using the Engle-Granger method. This involves using linear regression to find the parameter for Stock 2 and then computing the difference to obtain the spread.
   - Normalize the spread using a 30-day moving average and standard deviation:
     - **30-day moving average (mean)**: Smooths out short-term fluctuations.
     - **30-day standard deviation**: Measures the spread's volatility.
   - The normalized spread is calculated by subtracting the 30-day moving average from the spread and then dividing by the 30-day standard deviation.

4. **Generating Trading Signals**
   - **Buy Signal**: Triggered when the normalized spread crosses below -0.9. This triggers a buy for Stock 1 and a sell for Stock 2, and remains active until the spread crosses above -0.5, at which point the position is closed.
   - **Sell Signal**: Triggered when the normalized spread crosses above 0.9. This triggers a sell for Stock 1 and a buy for Stock 2, and remains active until the spread crosses below 0.5, at which point the position is closed.

5. **Backtesting the Strategy**
   - Simulate trades based on generated signals. Calculate profits and losses to evaluate performance. Key metrics have been calculated to analyze the performance of the algorithm.

6. **Graph plotted to implement the stratergy as explained in the User Guide under the Generating Trading Signals section**:
![output](https://github.com/shreyasdahale/Pairs-Trading-Algorithm/assets/146332434/2842a434-ba7a-4ec6-8a59-b59ae3e91b8e)

## Getting Started
To run the pairs trading algorithm, follow the instructions below:

### Prerequisites
- Python 3
- Libraries: pandas, numpy, statsmodels, matplotlib

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/pairs-trading-algorithm.git
   ```
2. Navigate to the project directory:
   ```bash
   cd pairs-trading-algorithm
   ```
3. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Algorithm
1. Prepare your dataset by fetching historical price data for your stocks and save it as a CSV file.
2. Run the algorithm:
   ```bash
   python pairs_trading_algorithm.py
   ```

### Analyzing Results
- After running the algorithm, review the generated plots and performance metrics to assess the strategy's effectiveness.
- Refer to the detailed backtesting report and user guide for a comprehensive analysis.

For more details, please refer the [User Guide](Pairs Trading Algorithm User Guide 200624.docx) and [Backtesting Report](Pairs Trading Algorithm Backtesting Report.docx).
