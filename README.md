# Portfolio Risk Analysis — VaR & Expected Shortfall

## Overview

This project builds and analyzes an optimized equity portfolio and evaluates its downside risk using:

- **Maximum Sharpe Ratio optimization**
- **Historical Value at Risk (VaR)**
- **Parametric (Gaussian) VaR**
- **Historical Expected Shortfall (CVaR)**
- **Parametric Expected Shortfall**

The goal is to measure not only portfolio performance, but also tail risk under both empirical and theoretical assumptions.

---

## Portfolio Construction

- Selected multiple equities across sectors.
- Computed expected returns and covariance matrix.
- Optimized weights using the **Maximum Sharpe Ratio** approach.
- Generated daily portfolio returns using optimized weights.

---

## Risk Measures Implemented

### Historical VaR (95%)

- Computed the 5th percentile of daily portfolio returns.
- Measures the worst loss observed in the bottom 5% of historical outcomes.
- Makes **no distributional assumptions**.

---

### Parametric VaR (95%)

- Assumes returns follow a normal distribution.
- Uses mean and standard deviation of portfolio returns.
- Mean + (Z × Standard Deviation)

Where:
- Z = -1.645 for 95% confidence.

---

### Historical Expected Shortfall (CVaR)

- Calculates the **average loss** within the worst 5% of returns.
- Captures the severity of tail risk beyond VaR.

Historical CVaR = Average (returns ≤ Historical VaR)

---

### Parametric Expected Shortfall (CVaR)

- Computes tail average assuming normal distribution.
- Uses the normal PDF and quantile function.

Parametric CVaR = Mean − Std Dev × [ -1.645 / Alpha ]

---

## Key Findings

- Historical and Parametric VaR produced very similar results.
- This suggests the portfolio’s return distribution is approximately normal around the center.
- However, **Expected Shortfall revealed deeper tail losses**, highlighting that extreme downside risk is larger than VaR alone indicates.
- Measuring both performance (Sharpe ratio) and tail risk (VaR & CVaR) provides a more complete view of portfolio risk.

---

## Why This Matters

- VaR provides a loss threshold.
- CVaR measures how severe losses are beyond that threshold.

This project demonstrates how portfolio optimization and risk management tools can be combined to evaluate both return efficiency and downside exposure.

---

## Tools Used

- Python
- NumPy
- Pandas
- SciPy
- Matplotlib
- PyPortfolioOpt
- yfinance

---

## 📌 Conclusion

An optimized portfolio can deliver strong risk-adjusted performance while still carrying meaningful tail risk.  
Combining Sharpe ratio optimization with VaR and Expected Shortfall analysis provides a robust framework for portfolio risk evaluation.

