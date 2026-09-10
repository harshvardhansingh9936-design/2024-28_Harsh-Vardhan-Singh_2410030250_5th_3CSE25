# Financial Data Analysis Internship — Junior Data Analyst

## Internship Submission

**Student:** Harsh Vardhan Singh  
**Roll No.:** 2410030250  
**Session:** 2024–28  
**Semester:** 5th  
**Section:** 3CSE25  
**Organization:** YuvaIntern  
**Role / Designation:** Junior Data Analyst  
**Internship Period:** 07 August 2026 – 04 September 2026

---

## Project Title

### Historical AAPL Market Data Analysis & Predictive Modeling

A practical financial data analytics project using Apple Inc. (AAPL) historical daily market data. The work demonstrates a complete data-analysis workflow covering acquisition, validation, cleaning, feature engineering, exploratory analysis, visualization, and predictive modeling.

> **Scope:** This repository is exclusively for the **Junior Data Analyst internship** submission. It does not include or represent the separate Junior Web Developer internship.

---

## Project Overview

The project follows a four-week analytical workflow built around the same AAPL dataset:

| Week | Focus | Key Work |
|---|---|---|
| **Week 1** | Planning & Data Acquisition | Defined analytical questions, data sources, workflow, quality controls, and reproducibility plan; acquired AAPL historical data using `yfinance`. |
| **Week 2** | Data Wrangling & Processing | Parsed and validated the market data, checked missing/duplicate/invalid records, engineered financial features, and implemented IQR/Z-score outlier flags. |
| **Week 3** | EDA & Visualization | Performed descriptive and distributional analysis, examined returns, volatility and volume, produced six analytical visualizations, and interpreted statistical outliers. |
| **Week 4** | Predictive Modeling | Built chronological train/test predictive models for next-day closing price and next-day return; compared model performance with a naive persistence baseline. |

---

## Dataset

- **Security:** Apple Inc. (AAPL), Nasdaq
- **Data type:** Daily historical OHLCV market data
- **Analysis period:** 02 January 2020 – 31 December 2024
- **Market variables:** Open, High, Low, Close, Volume
- **Processed records:** 1,258 dated market records
- **Primary acquisition workflow:** Yahoo Finance data through Python's `yfinance` library

The raw dataset is preserved separately from the processed dataset to support reproducibility and transparent data-quality decisions.

---

## Analytical Workflow

```text
Data Acquisition
       ↓
Data Validation & Quality Checks
       ↓
Cleaning & Structuring
       ↓
Feature Engineering
       ↓
Exploratory Data Analysis
       ↓
Visualization & Interpretation
       ↓
Predictive Modeling
       ↓
Performance Evaluation
       ↓
Documentation & Reproducibility
```

### Key engineered features

- Daily return
- Log return
- Intraday range percentage
- Volume change percentage
- 20-day rolling volatility
- Short moving averages (SMA)
- Return-based outlier flags using IQR and Z-score methods

---

## Week 3 — Key Findings

The exploratory analysis found that:

- AAPL's closing price increased from approximately **$72.27 to $248.62** across the analysis period.
- Mean daily return was approximately **+0.12%**, with a standard deviation of approximately **1.99%**.
- **52 trading days** were flagged as statistical return outliers, with **55.8% occurring in 2020**.
- Trading volume showed a **moderate positive relationship** with the absolute size of daily price movements (**Pearson r ≈ 0.55**).

These results are descriptive and are not intended as investment advice or a trading recommendation.

---

## Week 4 — Predictive Modeling

The final stage tested whether same-day market information could meaningfully predict the next trading day's outcome.

### Primary target

**Next-day closing price** using a chronological 80/20 train/test split without shuffling.

### Models evaluated

1. Naive persistence baseline — tomorrow's close approximated by today's close
2. Single-feature linear regression using Close
3. Multivariate linear regression using engineered market features
4. Secondary linear regression for next-day Daily Return

### Headline test results

| Model | Test R² | Test RMSE |
|---|---:|---:|
| Naive persistence baseline | **0.9873** | **$2.87** |
| Close-only linear regression | 0.9871 | $2.89 |
| Multivariate linear regression | 0.9868 | $2.93 |
| Next-day return regression | -0.0567 | 0.0145 |

The high price-level R² values should not be interpreted as strong forecasting skill because AAPL prices are highly persistent over adjacent trading days. The naive baseline slightly outperformed the trained price models. The negative test R² for next-day returns provides a more demanding test and indicates weak out-of-sample predictive power for the selected linear features.

---

## Tools & Technologies

- **Python**
- **Pandas** — data loading, cleaning and transformation
- **NumPy** — numerical computation
- **Matplotlib** — visualization
- **Scikit-learn** — regression and model evaluation
- **Jupyter Notebook** — interactive analysis and documentation
- **yfinance** — financial market data acquisition
- **Git & GitHub** — version control and project organization

---

## Submission Documents

The college submission repository is intended to contain the following required documents:

- 📄 **Internship Report**
- 📊 **Internship Presentation (PPT)**
- 🏆 **Junior Data Analyst Internship Certificate**

Additional project notebooks, source code, datasets, figures, and supporting reports may be included when required for technical evidence.

---

## Reproducibility

The analysis was designed so that the workflow can be inspected and reproduced from the documented notebooks and Python scripts. Raw data is kept separate from processed data, transformation decisions are documented, and chronological splitting is used for predictive modeling to reduce temporal leakage risk.

---

## Important Note

This project is an **academic/internship data-analysis project**. Historical market analysis and model results should not be interpreted as financial advice, investment recommendations, or guarantees of future performance.

---

## Author

**Harsh Vardhan Singh**  
B.Tech — Computer Science Engineering  
IILM University, Greater Noida  
Session 2024–28
