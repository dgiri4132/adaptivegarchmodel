# Adaptive GARCH Volatility Forecasting for Portfolio Allocation
This project implements an adaptive volatility modeling system using GARCH and EGARCH models(which I learned from my course at DataCamp) to forecast stock volatility and allocate portfolio weights dynamically. Each model is selected on the statistical properties of the stock's return like skewness or kurtosis level, making the strategy more responsive to market conditions. I will be adding new statistical properties which will further help the project decide what models to use for more accuracy which I have been learning through the finance book Option Volatility and Pricing by Sheldon Natenberg.Contributions and suggestions for improvement are welcome!I know there are many fixes that can be applied to it.
# Project Highlights
- User Input: Choose any stocks, date range, and forecast horizon
- Adaptive Model Switching: Based on skewness and kurtosis of residuals
- Volatility Forecasting: Using GARCH and EGARCH models
- Backtesting Framework: Rolling window backtest with daily portfolio rebalancing
- Performance Metrics: Calculates Sharpe Ratio and visualizes cumulative returns.
# Methodology
  Input Collection:
  - User provides tickers, start and end date, forecast horizon.
  - Data pulled from yfinance and cleaned.
  Return Series calculation
  - Daily percentages returns computed and cleaned
  Model Selection:
  - Fit GARCH (1,1) model, calculate skewness and kurtosis of residuals and select model accordingly.
  Rolling Window Forecast:
  - For each time window:
    - Fit chosen model
    - Forecast next-day volatility
    - Allocate weights inversely to the volatility
  Portfolio Evaluation:
  - Calculate daily return based on dynamic weights
  - Compute cumulative return curve
  - print annualized Sharpe Ratio
# How to Run
- Clone the repo
- Install dependencies: pip install yfinance arch pandas numpy matplotlib scipy
- open the notebook
- follow the prompts(enter tickers,date range, and forecast horizon)
# Future Enhancements
- CVaR-based Allocation
- Mean-reverting Alpha Signals
- Benchmark Comparision
- Multi-day Volatility Forecasting
