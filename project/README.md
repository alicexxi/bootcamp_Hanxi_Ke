# Robotics-Sector Quantitative Portfolio

**Stage:** Problem Framing & Scoping (Stage 01)

## Problem Statement
Robotics-sector equities are volatile and thinly researched relative to broad-market names, making it hard for a portfolio manager to size positions without either overconcentrating in a few winners or diluting returns through naive diversification. This project builds a systematic, risk-aware portfolio construction pipeline for a ~120-stock robotics universe, aiming to deliver risk-adjusted returns that are both defensible and reproducible month over month.

## Stakeholder & User
The primary stakeholder is the internship mentor / investment team overseeing thematic robotics allocation. They review and approve monthly rebalancing decisions. The output is used directly in a monthly workflow: weights must be finalized before month-end rebalancing.

## Useful Answer & Decision
Predictive / decision-support: the deliverable is a reproducible monthly portfolio-weight table plus a risk-adjusted performance metric (Sharpe ratio). The chosen artifact is a walk-forward backtest pipeline that outputs weights, Sharpe ratio, max drawdown, and comparison charts across competing allocation strategies (equal-weight, Risk Parity, Inverse Volatility).

## Assumptions & Constraints
- Historical price data is assumed free of survivorship bias
- Rebalancing assumed executable at month-end close, no slippage modeled
- Position size capped at 10% per stock; diversification enforced via an HHI penalty
- For research/coursework use only, not an actual investment recommendation

## Known Unknowns / Risks
- Factor and risk-model effectiveness may shift with market regime
- Reported Sharpe ratios are in-sample/backtest results; out-of-sample performance is unverified
- Rolling-window parameter estimation reduces but does not eliminate look-ahead risk

## Lifecycle Mapping
Goal → Stage → Deliverable
- Define problem & stakeholder needs → Problem Framing & Scoping (Stage 01) → This README + stakeholder memo
- Acquire robotics-sector price & fundamentals data → Data Acquisition / Ingestion → Cleaned raw dataset
- Handle missing values & outliers → Data Preprocessing / Outlier Analysis → Processed dataset (data/processed/)
- Build risk/factor features → Feature Engineering → Feature pipeline (src/features.py)
- Construct & compare portfolios (Risk Parity, Inverse Volatility, etc.) → Modeling → Backtest results & weight tables
- Communicate performance & risk → Evaluation & Risk Communication / Results Reporting → Charts + summary report

## Repo Plan
data/, src/, notebooks/, docs/ ; built out in Stage 02, updated each stage thereafter
