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
