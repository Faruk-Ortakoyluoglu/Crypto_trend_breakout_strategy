This Python script implements a trend breakout-based trading signal generator for crypto assets using linear regression and confidence interval projections. 
It aims to detect potential short-term sell signals by fitting a linear model on a historical window, projecting confidence intervals forward, and simulating a take-profit / stop-loss outcome.

Features:
  - ✅	Reads and prepares OHLCV data for multiple symbols.
  - ✅Applies linear regression (statsmodels) on a rolling window.
  - ✅	Projects lower confidence bounds forward.
  - ✅	Detects crossover-based sell signals.
  - ✅	Simulates profit/loss scenarios with visual plots.
  - ✅	Avoids signal spamming with a configurable cooldown mechanism.
  - ✅	Visualizes each signal and its profit/loss zone with Matplotlib.

Updates

During backtesting, I observed that in many cases where the slope of the regression line was steep, the price action tended to pull back sharply — often triggering the stop-loss before reaching the take-profit target. 
To better understand this behavior, I analyzed the distribution of signal slopes in histogram.ipynb, comparing the frequency of profitable vs. losing trades across slope intervals.

This analysis revealed a consistent pattern: beyond a certain slope threshold, the likelihood of stop-loss outcomes increased significantly. 
This is likely due to the nature of strong trends — where price often retests the trendline after a sharp move, creating false breakout signals.

As a result, I refined the strategy to only allow signals within an empirically determined optimal slope range. 
This adjustment reduced overfitting to extreme trends and improved the balance between win rate and reward/risk.
