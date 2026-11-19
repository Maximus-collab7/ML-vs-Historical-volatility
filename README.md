# ML-vs-Historical-volatility
Can ML volatility forecasts build less risky portfolios than historical volatility? ESILV ML project.

First step : analyse of paper 

## Main papers

- Rathi, V., Kshirsagar, M., & Ryan, C. (2024). *Enhancing Portfolio Performance: A Random Forest Approach to Volatility Prediction and Optimization*. ICAART 2024.

   https://www.scitepress.org/Papers/2024/124646/124646.pdf

  and only for the method :
- Wade, R. (2026). *Do Better Volatility Forecasts Lead to Better Portfolios? Evidence from Graph Neural Networks*. arXiv preprint.
  
  https://arxiv.org/abs/2605.19278
  
## Other for more details

- Volatility Forecasting with Machine Learning
and Intraday Commonality 

https://arxiv.org/pdf/2202.08962

- A machine learning approach to volatility forecasting (bcp de formules)
Kim Christensen, Mathias Siggaard and Bezirgen Veliyev

https://pure.au.dk/ws/portalfiles/portal/208284743/rp21_03.pdf


## Process

0. **Data** – Daily adjusted prices (2015–2025, Yahoo Finance) for GLD, XOM, JPM, JNJ, AAPL, TLT and BTC-USD, plus SPY and VIX as market indicators. Daily log returns.
1. **Target** – Realized volatility of each asset for each week (annualized standard deviation of daily log returns). The goal is to predict next week's value.
2. **Features** – Historical volatilities over 5, 21, 63 and 252 days (`rv_5`, `rv_21`, `rv_63`, `rv_252`), 20-day momentum, short/long volatility ratio, VIX and market volatility (SPY).
3. **Forecasts** – Three volatility forecasts compared on a time-based split (train 2015–2022, validation 2023, test 2024–2025):
   - Historical volatility (baseline)
   - HAR model (linear regression)
   - Random Forest
4. **Portfolios** – Each week, minimum-variance and inverse-volatility portfolios are built with each forecast (weekly rebalancing, 10 bp transaction costs). Equal-weight portfolio as a naive benchmark.
5. **Evaluation** – Realized volatility of each portfolio over 2024–2025 answers the research question. Secondary criteria: annual return, Sharpe ratio, maximum drawdown, turnover. Robustness: block bootstrap and year-by-year walk-forward validation.











