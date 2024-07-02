# Pairs Trading Algorithm

## Project Overview
This project presents a pairs trading algorithm designed to exploit market inefficiencies by taking long and short positions in two highly correlated stocks. The algorithm was backtested using historical data for ONGC and ZOMATO stocks from January 2022 to April 2024, achieving a total return of 21.4%.

## Introduction
Pairs trading is a market-neutral strategy that involves taking long and short positions in two correlated stocks to profit from their relative price movements.

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

## Conclusions
- **Total Return**: 21.4%
- **Annualized Return (CAGR)**: 0.09%
- **Sharpe Ratio**: 2.69
- **Maximum Drawdown**: -0.031
- **Beta**: 0.547
- **Alpha**: 0.0535
- **Cumulative Returns of the strategy used on the 2 stocks**:
![output2](https://github.com/shreyasdahale/Pairs-Trading-Algorithm/assets/146332434/a0d53ea7-f1dc-4963-9984-8380af3b8410)

## Recommendations
- Implement stop-loss strategies.
- Diversify into additional pairs.
- Regularly review and adjust the algorithm.

## How to Use
1. **Data Collection**: Fetch historical price data and create a dataframe.
2. **Identify Best Pair**: Use cointegration tests to select the pair with the lowest p-value.
3. **Calculate Spread**: Use the Engle-Granger method to calculate and normalize the spread.
4. **Generate Signals**: Buy signal at normalized spread < -0.9, sell signal at > 0.9.
5. **Backtest**: Simulate trades based on signals and evaluate performance.
6. **Graph plotted to implement the stratergy as explained in the User Guide under the Generating Trading Signals section**:
![output](https://github.com/shreyasdahale/Pairs-Trading-Algorithm/assets/146332434/2842a434-ba7a-4ec6-8a59-b59ae3e91b8e)


## Getting Started
### Prerequisites
- Python 3
- Libraries: pandas, numpy, statsmodels, matplotlib

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/shreyasdahale/Pairs-Trading-Algorithm.git
   ```
2. Navigate to the project directory:
   ```bash
   cd pairs-trading-algorithm
   ```
3. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```
   
For more details, refer to the [User Guide](Pairs%20Trading%20Algorithm%20User%20Guide%20200624.docx) and [Backtesting Report](Pairs%20Trading%20Algorithm%20Backtesting%20Report.docx).
