# Limex-Trading-Summer-Challenge-25-Documentation
Event-Driven Trading Strategy with Catalyst Detection and Lime API Execution This repository contains the research, development, and implementation of a short-horizon event-driven trading strategy that systematically captures market inefficiencies around catalysts such as earnings surprises, corporate actions, and regulatory changes.

# Event-Driven Trading Strategy with Catalyst Detection
This repository contains the research, development, and implementation of a short-horizon event-driven trading strategy that systematically captures market inefficiencies around catalysts such as earnings surprises, corporate actions, and regulatory changes. The strategy was developed and deployed during the Limex Trading Challenge Summer 2025, where it achieved 1st place in Absolute Returns and 2nd place in Sharpe Ratio.

# Methodology
## Hypothesis
Markets tend to underreact or inefficiently price short-term catalysts such as earnings surprises, regulatory approvals, M&A announcements, and abnormal trading volume. By systematically identifying and quantifying these events, it is possible to generate alpha through timely long or short positioning.

## Research Process
* Conducted a literature review on event-driven strategies, drawing from academic sources such as Barberis et al. (1998) on investor sentiment, and empirical findings on post-earnings announcement drift (Bernard & Thomas, 1989).
* Designed a catalyst detection framework integrating structured financial data, unstructured news feeds, and third-party brokerage APIs.
* Benchmarked against passive and momentum-driven baselines to validate alpha generation.

## Data Sources
* Market Data: Historical OHLCV data from third-party vendors. **(Algorithm code execution won't be attached in this repository for proprietary purposes.)**
* Fundamental Data: Earnings reports, analyst revisions, corporate filings.
* Sentiment Data: News and social media feeds processed via NLP and sentiment scoring.
* Market Microstructure Signals: Abnormal volume, order flow imbalance, and volatility clustering.

## Signal Development
* Catalyst Scoring Model: Machine learning ensemble (XGBoost, LightGBM) to predict probability and directional impact of catalysts.
* Portfolio Allocation: Exposure capped at ~20% per signal, scaled by model confidence score.
* Risk Controls: Position caps, stop-loss thresholds, and sector diversification to prevent overconcentration.

## Backtesting and Optimization
* Framework: Custom Python backtesting with Backtrader and TradingView integration.
* Bias Control: Adjustments for survivorship bias, lookahead bias, and realistic transaction costs.
* Hyperparameter Tuning: Bayesian optimization (via Optuna) with walk-forward cross-validation.
* Validation: Time-series cross-validation, out-of-sample testing, and regime-based evaluation.

## Execution Pipeline
* Automated signals, position sizing and direction indicators via TradingView, followed by manual inputs into Lime Interface.
* Real-time monitoring of open positions, exposure, and order confirmations.
* Fail-safe mechanisms for API downtime and trade execution delays.

## Results
* **1st in Absolute Returns** ($117,850 / 17.85%) and **2nd in Sharpe Ratio** (2.75) across 559 trades taken in Limex Trading Challenge Summer 2025.
Achieved <3% maximum drawdown while maintaining strong alpha capture.
Demonstrated consistent ability to exploit post-event price drift in both earnings and high-volume anomaly scenarios.
Sharpe Ratio exceeded baseline momentum models by a significant margin.

Over the 1 month trading period, the ortfolio shows a maximum drawdown of about ~2%, which is quite low relative to the gains (up to +19%). This suggests a **strong return-to-risk profile**: high upside volatility but controlled downside.

## Proposed Improvements
1. Alternative Datasets
    * Options flow and implied volatility surfaces.
    * ESG and sustainability event tracking.
    * Real-time retail sentiment indicators.
3. Model Enhancements
    * Reinforcement learning for adaptive execution strategies.
    * Dynamic thresholding of catalyst scores based on volatility regimes.
    * Graph neural networks to capture sector and supply chain linkages.
4. Risk Management
    * Multi-horizon risk-adjusted capital allocation.
    * Incorporation of tail-risk hedging strategies.

## References
* Bernard, V. L., & Thomas, J. K. (1989). Post-Earnings-Announcement Drift: Delayed Price Response or Risk Premium? Journal of Accounting Research.
* Barberis, N., Shleifer, A., & Vishny, R. (1998). A model of investor sentiment. Journal of Financial Economics.
* Jegadeesh, N., & Titman, S. (1993). Returns to Buying Winners and Selling Losers: Implications for Stock Market Efficiency. Journal of Finance.
* Cartea, Á., Jaimungal, S., & Penalva, J. (2015). Algorithmic and High-Frequency Trading. Cambridge University Press.
