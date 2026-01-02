# Monte Carlo Simulation: S&P 500 vs. NVIDIA

This project utilizes **Geometric Brownian Motion (GBM)** to simulate 5,000 potential price paths for the S&P 500 ($GSPC) and NVIDIA (NVDA). The goal is to compare a diversified index against a high-volatility momentum stock using risk-adjusted metrics.

## 🚀 Key Features
- **Data Ingestion:** Real-time market data via `yfinance`.
- **Stochastic Modeling:** Implementation of GBM using drift ($\mu$) and volatility ($\sigma$).
- **Risk Metrics:** Calculates **Sharpe Ratio** and **95% Value at Risk (VaR)**.
- **Visualization:** Normalized comparison (Base 100) to visualize relative performance.

## 📊 Methodology
The simulation follows the stochastic differential equation:
$S_t = S_0 \exp(( \mu - \frac{1}{2}\sigma^2)t + \sigma W_t)$

Where $W_t$ represents the Wiener process (random shocks).

## 📈 Results
![Simulation Results](plots/sim_results.png)

*(Tip: Upload your plot image to the /plots folder so it shows up here!)*

## 🛠️ Installation
1. Clone the repo: `git clone https://github.com/YOUR_USERNAME/repo-name.git`
2. Install dependencies: `pip install -r requirements.txt`
3. Run the script: `python scripts/simulation.py`
