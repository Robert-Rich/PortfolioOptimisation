# Portfolio Optimisation and Allocation Tool

A modular Python package for performing mean-variance portfolio optimisation using real-world equity data. This tool enables users to compute and visualise the efficient frontier, as well as derive optimal asset allocations under customisable target returns.

---

## Features

- **Data Loading**: Fetches historical adjusted (or close) prices via `yfinance`, with built-in handling for library updates.
- **Statistics Computation**: Calculates annualised expected returns and covariance matrix from daily price data.
- **Mean-Variance Optimisation**: Solves a quadratic program in `cvxpy` to minimise portfolio variance subject to full investment and long-only (non-negative weights) constraints, with optional target return.
- **Efficient Frontier Generation**: Builds a grid of target returns and computes corresponding portfolio risk (standard deviation), packaging results into a DataFrame.
- **Visualisation**: Plots the efficient frontier (risk vs. return) using Matplotlib for intuitive portfolio analysis.
- **Customisable Inputs**: User-defined tickers, date range, target returns, and solver settings for flexibility.

## Usage

1. **Configure Inputs**

   - Edit `main.py` to set:
     - `tickers`: e.g., `['AAPL', 'MSFT', 'GOOGL']`
     - `start_date`, `end_date`: historical data range
     - `target_return`: annual return objective

2. **Run the Tool**

   ```bash
   python main.py
   ```

3. **Inspect Outputs**

   - Efficient frontier plot via Matplotlib.
   - Terminal output of optimized weights for chosen target return.
   - Frontier data accessible as a Pandas DataFrame (exportable to CSV).

## Example

```bash
python main.py
```

```text
Optimised Weights for Return = 15.00%:
AAPL     0.23
MSFT     0.32
GOOGL    0.28
AMZN     0.17
dtype: float64
```

## Extending the Tool

- **Short Selling**: Remove non-negativity constraint in `optimise_port`.
- **Black–Litterman**: Integrate user views on expected returns.
- **Transaction Costs**: Add cost terms to the optimisation objective.
- **Interactive Dashboard**: Build a front-end with Streamlit or Flask + Plotly.



##
