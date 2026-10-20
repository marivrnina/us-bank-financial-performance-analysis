# U.S. Bank Financial Performance & Risk Analysis

### Exploratory Data Analysis | Python · Pandas · Seaborn

## Project Overview

This project explores the financial performance and risk indicators of **4,388 U.S. banks** using publicly available quarterly financial data from the Federal Deposit Insurance Corporation (FDIC).

The analysis focuses on bank profitability, asset size, lending activity, and capital adequacy. It also examines data quality issues and relationships between key financial indicators.

The objective is to understand how financial performance differs across banking institutions and identify patterns that may be relevant to financial analysis.

## Dataset

**Source:** [Federal Deposit Insurance Corporation (FDIC)](https://www.fdic.gov/bank-data-guide/data-downloads)

- **Dataset:** FDIC Quarterly Financial Data
- **Reporting period:** Q3 2025 (September 30, 2025)
- **Institutions:** 4,388
- **Original variables:** 161
- **Geographic coverage:** United States

The dataset contains institution-level financial information, including assets, deposits, income, profitability ratios, and regulatory capital indicators.

## Tools & Technologies

- **Python** — Data processing and analysis
- **Pandas** — Data cleaning, aggregation, and financial comparisons
- **NumPy** — Numerical operations
- **Matplotlib & Seaborn** — Statistical visualizations
- **Jupyter Notebook** — Interactive analysis and documentation

## Methodology

### 1. Data Exploration & Cleaning

- Examined dataset structure, data types, and missing values.
- Identified and removed eight completely empty columns.
- Checked for duplicate records and unusual financial observations.
- Investigated extreme profitability ratios.
- Examined zero reported risk-based capital ratios and performed a separate sensitivity analysis excluding those values.

### 2. Financial Performance Analysis

Analyzed three key profitability indicators:

| Metric | Description |
|---|---|
| Return on Assets (ROA) | Measures profitability in relation to total assets |
| Return on Equity (ROE) | Measures profitability in relation to shareholders' equity |
| Net Interest Margin (NIM) | Measures net interest income relative to average interest-earning assets |

Calculated descriptive statistics and examined profitability distributions.

### 3. Bank Size Comparison

Grouped institutions into four categories based on total assets:

- Under $1 billion
- $1 billion–$10 billion
- $10 billion–$100 billion
- Over $100 billion

Compared median profitability across bank-size groups. Medians were used to reduce the influence of extreme financial observations.

### 4. Financial Risk Analysis

Examined two indicators:

- **Loan-to-Deposit Ratio:** Loans compared with deposits, providing insight into lending intensity and potential funding pressure.
- **Risk-Based Capital Ratio:** Regulatory capital relative to risk-weighted assets, providing insight into capital adequacy.

Investigated reported zero capital ratios separately because their reporting meaning had not been fully established.

### 5. Correlation Analysis

Used **Spearman rank correlation** to explore relationships between profitability and financial risk indicators.

Spearman correlation was selected because it is less sensitive to extreme observations than Pearson correlation and does not require linear relationships.

## Key Findings

### Overall Bank Profitability

| Metric | Result |
|---|---:|
| Median ROA | 1.10% |
| Median ROE | 10.96% |
| Median Net Interest Margin | 3.67% |
| Banks with negative ROA | 227 (5.2%) |

Most institutions reported positive returns on assets, although profitability varied across banks.

### Profitability by Bank Size

Banks with more than $100 billion in assets had a median ROA of **1.14%**, slightly higher than the approximately 1.10% median among banks with less than $1 billion in assets.

However, the largest banks had a lower median net interest margin of **3.04%**, compared with **3.75%** among banks with less than $1 billion in assets.

This suggests that higher net interest margins do not necessarily correspond to higher overall profitability. Other factors, such as noninterest income, operating expenses, and differences in banking business models, may also contribute.

### Financial Risk & Data Quality

**1,720 institutions (39.2%)** had reported risk-based capital ratios of zero.

These observations were investigated separately, and an additional analysis was performed excluding zero values.

The median capital ratio changed from 12.93% to 15.53% when zero observations were excluded, demonstrating the sensitivity of financial summaries to data treatment.

The reporting meaning of these zeros requires further verification.

### Correlation Analysis

- **ROA and ROE:** Strong positive Spearman correlation (0.84).
- **ROA and NIM:** Moderate positive correlation (0.54).
- **Profitability and selected risk indicators:** Generally weak relationships in the overall analysis.
- **Capital ratio and loan-to-deposit ratio:** Moderate negative correlation (approximately −0.45) in the analysis excluding zero reported capital ratios.

These relationships are descriptive and do not establish causation.

## Conclusion

The analysis suggests that larger U.S. banks are not necessarily substantially more profitable when measured by return on assets.

Although the largest institutions demonstrated slightly higher median ROA, they also reported lower net interest margins, highlighting the importance of examining multiple financial indicators when evaluating banking performance.

The project also demonstrates how data quality, outliers, and reporting conventions can influence financial analysis.

## Limitations

- The dataset covers a single reporting period, so the analysis does not establish long-term financial trends.
- Extreme financial ratios may reflect unusual events, institution-specific structures, or reporting issues.
- Zero risk-based capital ratios require further verification against FDIC reporting definitions.
- Financial risk is assessed using selected indicators rather than a comprehensive bank risk model.
- Correlations do not imply causal relationships.

## Data Source

Federal Deposit Insurance Corporation (FDIC)  
[FDIC Bank Data Downloads](https://www.fdic.gov/bank-data-guide/data-downloads)

