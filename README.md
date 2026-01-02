# Monte Carlo Simulation: S&P 500 vs. NVIDIA

This project utilizes **Geometric Brownian Motion (GBM)** to simulate 5,000 potential price paths for the S&P 500 (^GSPC) and NVIDIA (NVDA). The goal is to quantify the risk-reward trade-off between a diversified market index and a high-growth momentum stock using risk-adjusted metrics.

## 🚀 Key Features
- **Data Ingestion:** Automated market data retrieval via `yfinance`.
- **Stochastic Modeling:** Implementation of GBM using historical drift ($\mu$) and volatility ($\sigma$).
- **Risk Metrics:** Calculates **Sharpe Ratio** (Risk-Adjusted Return) and **95% Value at Risk (VaR)**.
- **Visualization:** Normalized comparison (Base 100) to visualize relative performance and dispersion.

## 📊 Methodology
The simulation follows the stochastic differential equation for Geometric Brownian Motion:

$$S_t = S_0 \exp\left(\left(\mu - \frac{1}{2}\sigma^2\right)t + \sigma W_t\right)$$

Where:
- $S_t$: Predicted price at time $t$
- $\mu$: Expected annual return (drift)
- $\sigma$: Annual volatility
- $W_t$: Brownian motion (random shocks)

## 📈 Results & Visualizations

### Price Path Simulation
The chart below shows 5,000 simulated paths. Notice the "fan" of outcomes—NVIDIA shows much wider dispersion, representing its higher volatility.

<img width="1005" height="624" alt="Monte Carlo Simulator Chart" src="https://github.com/user-attachments/assets/b9060dee-4bf9-4647-8441-49bca5e80aef" />

### Performance Diagnostics
The following table summarizes the quantitative output of the simulation:

<img width="670" height="192" alt="Monte Carlo Simulator Performance Diagnostics" src="https://github.com/user-attachments/assets/abf9025e-349d-45dd-a7a3-6f7fff72b654" />

## 🧐 Analysis & Insights
- **Risk vs. Reward:** While NVIDIA shows significantly higher expected returns, the wide distribution of green paths demonstrates much higher uncertainty.
- **Value at Risk (VaR):** The 95% VaR metric allows us to quantify the "worst-case" scenario. NVIDIA's VaR is significantly deeper than the S&P 500, requiring higher risk tolerance.
- **Sharpe Ratio:** By subtracting the risk-free rate (4%) from the returns and dividing by volatility, we determine if the "extra" volatility of NVDA is actually generating superior risk-adjusted returns compared to the benchmark.

## ⚠️ Model Limitations
- **Log-Normal Assumption:** This model assumes returns are normally distributed. In real markets, "fat tails" (extreme events) occur more frequently than GBM predicts.
- **Constant Volatility:** The model assumes volatility remains constant over the 252-day period, whereas market volatility is typically stochastic.

## 🛠️ Installation & Usage
1. Clone the repo:
   ```bash
   git clone [https://github.com/lokar10/repo-name.git](https://github.com/lokar10/repo-name.git)
2. Install dependencies: pip install -r requirements.txt
3. Run the script: python simulation.py
