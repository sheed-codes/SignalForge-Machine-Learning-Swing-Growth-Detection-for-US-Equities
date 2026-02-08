# SignalForge-Machine-Learning-Swing-Growth-Detection-for-US-Equities
This project explores quantitative methods for detecting potential short-term growth opportunities in US equities using machine learning and feature-based modeling.  The goal is NOT to predict prices directly, but to identify statistical signals associated with forward returns using structured time-series features.


SignalForge: Machine Learning Swing Growth Detection for US Equities
Overview

This project explores quantitative methods for detecting potential short-term growth opportunities in US equities using machine learning and feature-based modeling.

The goal is NOT to predict prices directly, but to identify statistical signals associated with forward returns using structured time-series features.

The project demonstrates a full research pipeline:

Data acquisition

Feature engineering

Forward return labeling

Walk-forward validation

Probability-based ranking

Simple strategy simulation

Research Objective

Detect stocks likely to experience significant upward price movement within a fixed forward window.

Target definition:

Binary classification problem

Label = 1 if forward return over next N trading days exceeds threshold

Otherwise label = 0

This framing avoids regression noise and focuses on probabilistic signal detection.

Dataset

Source:

Yahoo Finance historical price data

US equities (large-cap sample universe)

Fields used:

OHLC price data

Volume

Time Range:

2015 – Present

Feature Engineering

Model inputs include:

Short and medium-term momentum:

20-day return

60-day return

Trend positioning:

Distance from MA50

Distance from MA200

Breakout signals:

Relative position to 60-day high

Volatility regime:

20-day rolling volatility

Volume expansion:

Volume vs rolling average

All features use only past data to avoid lookahead bias.

Modeling Approach

Algorithm:

Logistic Regression (baseline probabilistic classifier)

Training method:

Time-based walk-forward split

No random shuffling

Evaluation on future unseen period

Evaluation metric:

ROC-AUC score

Output

Instead of raw predictions, the system generates:

Daily ranked probability board

Top candidate swing growth signals

Feature contribution insights

Example output:

date	ticker	probability
2026-02-06	AVGO	0.76
2026-02-06	UNH	0.73
2026-02-06	MSFT	0.65
Strategy Simulation (Research Only)

A simple experimental strategy:

Select top N highest probability stocks daily

Hold for fixed forward horizon

Compare against baseline average returns

This section demonstrates signal usefulness, not live trading performance.

Key Concepts Demonstrated

Time-series feature engineering

Avoiding lookahead bias

Forward-return labeling

Walk-forward validation

Probabilistic ranking systems

Quantitative signal research workflow

Limitations

Small universe sample

No transaction cost modeling

No survivorship bias adjustment

Educational research project only

Future Improvements

Gradient boosting / XGBoost

Cross-sectional ranking models

Regime detection

Risk-adjusted portfolio optimization

Expanded equity universe
