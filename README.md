# Monte Carlo Risk Analysis: S&P 500 vs. NVIDIA

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📊 Project Overview
This repository provides a quantitative framework for forecasting stock price trajectories using **Geometric Brownian Motion (GBM)**. By simulating 5,000 potential outcomes over a 252-day trading year, this tool compares the risk-adjusted performance of a benchmark index (**S&P 500**) against a high-volatility growth asset (**NVIDIA**).

The simulation accounts for:
* **Drift ($\mu$):** The average historical daily return (expected trend).
* **Diffusion ($\sigma$):** The historical volatility (market noise).
* **Random Shocks:** Normal distributions applied to price paths to model uncertainty.

## 🖼️ Results & Visualizations

### 1. Simulated Price Paths
The plot below visualizes 5,000 potential price trajectories. The bold lines represent the expected (mean) path for each asset. Note that the Y-axis is capped at 200% to maintain visual clarity for the S&P 500 benchmark.

<img width="1005" height="624" alt="Monte Carlo Simulator Price Paths" src="https://github.com/user-attachments/assets/3b0d5d27-a813-437a-8031-3304d249666d" />

### 2. Performance Diagnostics
The following table summarizes the statistical outcomes of the simulation:

<img width="662" height="197" alt="Monte Carlo Simulator Performance" src="https://github.com/user-attachments/assets/77a650d4-facb-4e7e-8020-7ed672260b8e" />

---

## 🧐 Interpretation of Results

Based on the 5,000 simulated scenarios, here is how to read the data:

* **Expected Return:** NVIDIA typically shows a much higher "mean" return than the S&P 500, but the "spread" (the cloud of thin lines) is much wider, indicating higher uncertainty.
* **Sharpe Ratio:** This is the most critical metric. A Sharpe Ratio > 1.0 is considered good. If NVIDIA has a higher Sharpe than the S&P 500, it means you are being adequately compensated for the extra "rollercoaster" ride of holding the stock.
* **Value at Risk (VaR):** The "95% Max Loss" tells you the worst-case scenario you should be prepared for in a typical year. You will notice NVIDIA's VaR is significantly deeper than the S&P 500's, highlighting the risk of concentration.
* **Probability of Profit:** Even if an asset has a high return, its probability of profit might be similar to the index. This is because high volatility can lead to extreme "outlier" gains that pull the average up, even if many individual paths end in the red.

## 🛠️ Installation & Usage
1. **Clone the repository:**
   ```bash
   git clone [https://github.com/lokar10/monte-carlo-risk-analysis.git](https://github.com/lokar10/monte-carlo-risk-analysis.git)
2. Install requirements: pip install -r requirements.txt
3. Run the simulation: python simulation.py
