# forex-probability-distribution-data-science

📈 Forex Probability Distribution Analysis

This project analyzes the probability distribution of Forex log returns using real exchange rate data.
It is designed to be robust to messy datasets, automatically locate CSV files, and perform a full statistical distribution analysis including visualization and hypothesis testing.

📌 Objectives

Load Forex exchange rate data from CSV files automatically

Clean and normalize inconsistent datasets

Compute log returns, the standard approach in financial modeling

Visualize empirical distributions and compare them to a normal distribution

Test normality using the Kolmogorov–Smirnov (KS) test

📂 Project Structure
.
├── forex_probability_analysis.py
├── daily_forex_rates.csv   (optional – auto-detected)
└── README.md

The script automatically scans the working directory and subfolders for CSV files.
If daily_forex_rates.csv exists, it is preferred.

📊 Dataset Requirements

The CSV file must contain the following information (column names may vary):

Required Field	Accepted Variants
Date	date, datetime, timestamp
Base Currency	base_currency, base, base_ccy
Quote Currency	currency, quote, ccy
Exchange Rate	exchange_rate, rate, close, value

The script automatically:

Normalizes column names

Detects valid columns

Stops execution if critical data is missing

⚙️ Installation & Dependencies

Install required libraries:

pip install numpy pandas matplotlib scipy
▶️ How to Run
python forex_probability_analysis.py

The script will:

Locate a CSV file automatically

Clean and validate the dataset

Select a currency pair (USD/EUR preferred if available)

Compute log returns

Plot the empirical distribution

Perform a KS normality test

Output descriptive statistics

🧮 Methodology
1. Log Returns

Log returns are computed as:

𝑟
𝑡
=
ln
⁡
(
𝑃
𝑡
𝑃
𝑡
−
1
)
r
t
	​

=ln(
P
t−1
	​

P
t
	​

	​

)

They are preferred in finance because they:

Are time-additive

Handle compounding naturally

Improve statistical modeling properties

2. Descriptive Statistics

Mean → average return

Standard deviation → volatility

3. Distribution Visualization

Histogram of empirical log returns

Overlaid Normal Probability Density Function (PDF)

This allows visual inspection of how closely Forex returns follow a normal distribution.

4. Kolmogorov–Smirnov Test

The KS test compares the empirical distribution with a theoretical normal distribution:

KS statistic → distance between distributions

P-value → statistical significance

Lower KS values and higher p-values indicate closer alignment with normality.

📤 Output Example
Selected currency pair: USD/EUR
Mean: 0.00012
Std: 0.0048
KS statistic: 0.062
P-value: 0.21
N: 2450
🛡️ Robustness Features

Automatic CSV discovery

Column name normalization

Missing-data detection

Zero-variance protection

NaN / infinite value handling

The script fails safely and explicitly instead of producing misleading results.

🚀 Possible Extensions

Compare multiple currency pairs

Fit alternative distributions (Student-t, skew-normal)

Time-windowed volatility analysis

VaR and CVaR estimation

Monte Carlo simulations

📚 Academic Context

This project demonstrates:

Probability distribution analysis

Financial time series modeling

Statistical hypothesis testing

Data cleaning and validation

Suitable for:

Probability & Statistics

Financial Econometrics

Data Science coursework
