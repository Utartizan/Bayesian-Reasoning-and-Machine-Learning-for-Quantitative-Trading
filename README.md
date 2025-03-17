# Quantitative Trading Study Notes in Octave: Preparing for Interviews and Work

## Introduction

Welcome to my personal study repository, where I document my learning journey as I prepare for quantitative trading interviews and future work in the field. This repository is a comprehensive collection of notes, code snippets, and educational reflections on key topics in quant trading, all implemented using Octave which is essentially a free, open-source numerical computing tool.

Quantitative trading involves using mathematical models, statistical techniques, and computational methods to identify and execute trading opportunities. As I work towards a career in this field, I’ve organised this repository into around 13 topics, each representing a critical area of study. These topics range from foundational data handling to advanced stochastic modelling, covering concepts frequently tested in quant interviews and applied in real-world trading roles.

This `README.md` serves as both an educational overview and a guide to my study progress. It explains the purpose of each topic, the key concepts I’ve learnt, and how they relate to quant trading interviews and work. Whether you’re a fellow learner or just curious, I hope this repository provides value and inspiration for your own journey.

---

## Purpose of This Repository

This repository serves multiple purposes:
1. **Track My Learning**: Document my progress as I study quantitative trading concepts in preparation for interviews and work.
2. **Solidify Understanding**: Implement key ideas in Octave to deepen my grasp of the mathematics and logic behind them.
3. **Prepare for Interviews**: Focus on topics commonly tested in quant interviews, such as stochastic processes, derivatives pricing, and optimisation.
4. **Share Knowledge**: Provide an educational resource for others preparing for similar roles, with explanations and code examples.

---

## Why Octave?

I chose Octave for this project because it’s a free, open-source alternative to MATLAB, making it accessible for self-study (basically I'm poor and my university doesnt have MATLAB software). Its benefits include:
- **Numerical Computing**: Efficient matrix operations for handling financial data.
- **Visualisation**: Basic plotting functions to explore data trends.
- **Transparency**: Coding from scratch in Octave forces me to understand the underlying maths, which is crucial for interviews.
- **Cost-Free**: No financial barriers, allowing me to focus on learning rather than software costs.

While Octave may lack some advanced features of commercial tools, it’s an excellent tool for building intuition and preparing for the technical rigour of quant roles.

---

## Topics Covered

The repository is organised into 15 modules, each focusing on a specific area of quantitative trading. Below, I outline each topic, its relevance to quant trading interviews and work, and the key concepts I’ve studied. These topics reflect my study progression, from foundational skills to advanced techniques.

### 1. Foundations of Financial Data Handling
- **Relevance**: Understanding how to handle financial data is the first step in any quant role. Interview questions often involve data preprocessing or time-series analysis.
- **Key Concepts Learnt**:
  - Loading and parsing financial data (e.g., CSV files from Yahoo Finance).
  - Cleaning data: handling missing values, outliers, and adjustments for splits/dividends.
  - Calculating returns (simple and log), volatility, and moving averages.
  - Visualising data with price plots, candlestick charts, and volume analysis.
- **Study Notes**: This topic taught me the importance of data integrity. Clean, reliable data is critical for accurate modelling and strategy development.

### 2. Basic Statistics for Trading
- **Relevance**: Statistical measures are fundamental to risk assessment and signal generation, often tested in interviews (e.g., calculating correlations or testing normality).
- **Key Concepts Learnt**:
  - Descriptive statistics: mean, variance, skewness, kurtosis of returns.
  - Correlation and covariance analysis for asset relationships.
  - Rolling statistics like moving averages and volatility.
  - Hypothesis testing (e.g., Jarque-Bera test for normality).
- **Study Notes**: I learnt how to quantify market behaviour and relationships, which are essential for portfolio construction and risk management.

### 3. Probability and Bayesian Reasoning
- **Relevance**: Probabilistic reasoning is key in quant trading, and Bayesian methods are often discussed in interviews for updating beliefs based on new data.
- **Key Concepts Learnt**:
  - Discrete and continuous probability distributions (normal, log-normal).
  - Bayesian updating for price movement probabilities.
  - Monte Carlo simulations for estimating outcomes.
  - Hidden Markov Models (HMM) for market regime detection.
- **Study Notes**: This topic helped me understand uncertainty in markets and how to model it systematically.

### 4. Stochastic Processes for Price Modelling
- **Relevance**: Stochastic models are a staple in quant interviews (e.g., “Derive the GBM solution” or “Explain mean reversion”).
- **Key Concepts Learnt**:
  - Brownian Motion and Geometric Brownian Motion (GBM) for price simulation.
  - Mean-reverting processes (e.g., Ornstein-Uhlenbeck) for pairs trading.
  - Jump diffusion models for sudden price changes.
  - Stochastic volatility models (e.g., Heston model).
- **Study Notes**: I gained insight into the mathematical foundations of price dynamics, which are crucial for derivatives pricing and risk management.

### 5. Technical Analysis and Indicators
- **Relevance**: While not always the focus in interviews, understanding technical indicators helps in discussing systematic trading strategies.
- **Key Concepts Learnt**:
  - Common indicators: RSI, MACD, Bollinger Bands, Stochastic Oscillator.
  - Trend-following strategies (e.g., moving average crossovers).
  - Momentum strategies and backtesting.
- **Study Notes**: This topic bridged the gap between discretionary and systematic trading, showing how rules can be derived from data.

### 6. Portfolio Optimisation
- **Relevance**: Portfolio optimisation (e.g., Markowitz theory) is a common interview topic, especially for risk management roles.
- **Key Concepts Learnt**:
  - Mean-variance optimisation (efficient frontier).
  - Risk metrics: Value-at-Risk (VaR), Conditional Value-at-Risk (CVaR).
  - Black-Litterman model for incorporating views.
  - Kelly Criterion for position sizing.
- **Study Notes**: I learnt how to balance risk and reward, a key skill for portfolio management.

### 7. Options and Derivatives Pricing
- **Relevance**: Derivatives pricing (e.g., Black-Scholes) is a core interview topic for quant roles.
- **Key Concepts Learnt**:
  - Black-Scholes model for European options.
  - Monte Carlo methods for option pricing.
  - Binomial tree model for discrete pricing.
  - Implied volatility and the volatility smile.
- **Study Notes**: This topic deepened my understanding of option pricing and the role of stochastic calculus in finance.

### 8. Machine Learning for Trading
- **Relevance**: Machine learning is increasingly relevant in quant trading, often discussed in interviews for predictive modelling roles.
- **Key Concepts Learnt**:
  - Linear and logistic regression for returns prediction.
  - Clustering (e.g., k-means) for pattern identification.
  - Neural networks for price forecasting.
- **Study Notes**: I explored how data science techniques can enhance traditional quant methods.

### 9. Time-Series Analysis and Forecasting
- **Relevance**: Time-series models like ARIMA and GARCH are often tested in interviews, especially for roles involving volatility forecasting.
- **Key Concepts Learnt**:
  - ARIMA models for price forecasting.
  - GARCH models for volatility forecasting.
  - Cointegration for pairs trading.
  - Kalman filters for smoothing and state estimation.
- **Study Notes**: This topic improved my ability to model and predict temporal patterns in financial data.

### 10. Risk Management and Performance Metrics
- **Relevance**: Risk management is critical in quant roles, and metrics like Sharpe ratio are common in interviews.
- **Key Concepts Learnt**:
  - Drawdowns (maximum, average).
  - Performance metrics: Sharpe, Sortino, Calmar ratios.
  - Stress testing portfolios.
  - Risk parity allocation.
- **Study Notes**: I learnt how to quantify and manage risk effectively, a key skill for any quant trader.

### 11. High-Frequency Trading (HFT) Concepts
- **Relevance**: HFT concepts are niche but may come up in interviews for specialised roles.
- **Key Concepts Learnt**:
  - Order book simulation and market impact.
  - Latency and execution modelling.
  - Market microstructure analysis.
  - HFT strategies (market making, statistical arbitrage).
- **Study Notes**: This topic introduced me to the fast-paced world of HFT and its unique challenges.

### 12. Advanced Stochastic Models
- **Relevance**: Advanced models may appear in interviews for senior quant roles or research positions.
- **Key Concepts Learnt**:
  - Levy processes for fat tails and jumps.
  - Fractional Brownian Motion for long-memory effects.
  - Regime-switching models for market states.
  - Copulas for modelling asset dependence.
- **Study Notes**: This topic pushed my understanding of complex price behaviours.

### 13. Sentiment Analysis and Alternative Data
- **Relevance**: Alternative data is a growing field, sometimes discussed in interviews for innovative quant roles.
- **Key Concepts Learnt**:
  - Parsing news or social media data.
  - Basic NLP: sentiment scoring, keyword extraction.
  - Event-driven strategies (e.g., earnings, central bank announcements).
- **Study Notes**: I explored how non-traditional data can enhance trading signals.

---

## How This Prepares Me for Interviews and Work

Each topic aligns with skills and knowledge tested in quant trading interviews or required in professional roles:
- **Technical Skills**: Coding in Octave hones my programming and numerical skills, often tested in coding interviews.
- **Mathematical Foundations**: Topics like stochastic processes and derivatives pricing prepare me for theoretical questions (e.g., “Derive the Black-Scholes PDE”).
- **Practical Applications**: Backtesting, risk management, and optimisation reflect real-world tasks in quant roles.
- **Problem-Solving**: Implementing complex models (e.g., Heston, GARCH) builds my ability to tackle challenging problems under pressure.

---

## Study Progress and Reflections

As I work through these topics, I’m tracking my progress and reflections in each folder’s `README.md`. For example:
- **Challenges**: Understanding stochastic calculus took time, but coding GBM simulations clarified the concepts.
- **Aha Moments**: Realising how Bayesian updating can refine trading signals was a breakthrough.
- **Interview Prep**: Practising portfolio optimisation problems has prepared me for common interview questions.

This repository is a living document of my learning journey, updated as I deepen my knowledge.

---

## How to Use This Repository

### Prerequisites
- **Octave**: Install Octave 4.0 or later from [GNU Octave](https://www.gnu.org/software/octave/download.html).
- **Sample Data**: Many scripts use CSV files from Yahoo Finance. Download historical data (e.g., for AAPL) and place it in the `data/` folder.

### Navigation
- Each folder (`01_foundations_data_handling/` to `15_optimisation_execution/`) contains:
  - Scripts (`.m` files) implementing the topic.
  - A `README.md` with detailed explanations and my study notes.
  - Sample outputs (e.g., plots) where applicable.
- Start with `01_foundations_data_handling/` and progress sequentially, or jump to topics relevant to your interests.

### Example Usage
To explore a topic, navigate to its folder and run the scripts in Octave. For instance:
```octave
cd 01_foundations_data_handling
run('load_data.m')
run('clean_data.m')
run('timeseries_analysis.m')
run('visualise_data.m')
