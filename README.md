# Chargeback Data Analysis
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1IJf399gASRsr9313vLyfXVAS0C_PB07-)


This project analyzes a dataset of ~11,000 credit card transactions to identify patterns associated with fraudulent chargebacks (CBK). By performing Exploratory Data Analysis (EDA) and Feature Engineering, I identified key risk indicators that can be used to prevent financial loss.

The Goal: Reduce chargeback rates by identifying high-risk time windows and suspicious card behavior (velocity).

🛠️ Key Technologies
Python (Pandas, NumPy)

Data Visualization (Matplotlib, Seaborn)

Jupyter Notebooks

Statistical Analysis

🔍 Critical Insights
1. The "6 AM Spike" (Temporal Risk)
While transaction volume is lowest in the early morning, the Risk Rate (probability of fraud) peaks at 6:00 AM.

Finding: 1 out of every 3 transactions at 6 AM resulted in a chargeback (33.3% risk).

Impact: This window represents a concentrated period of automated bot attacks or cross-border fraud.

2. Transaction Velocity
I calculated "Velocity" as the number of transactions per card in a 24-hour window.

Finding: Cards used only once per day have a <1% risk. Cards used 3+ times per day have a >50% risk.

Impact: High velocity is the strongest predictor of fraudulent intent in this dataset.

3. Financial Loss Profiling
Total Losses Identified: Over $104,000 in fraudulent chargebacks.

Ticket Size: Fraudulent transactions averaged $183.30, significantly higher than the $126.65 average for legitimate transactions.

💡 Data-Driven Recommendations
Based on the analysis, I recommend implementing the following automated business rules:

Velocity Block: Automatically flag or block any card attempting more than 3 transactions in a 24-hour window.

Time-of-Day Authentication: Require Mandatory Two-Factor Authentication (2FA) for all transactions occurring between 5:00 AM and 7:00 AM.

High-Value Threshold: Implement manual review for all first-time transactions exceeding $180.

📁 Repository Structure
notebooks/: Contains the full Python analysis and visualization code.

data/: Contains the raw and cleaned versions of the dataset.

visuals/: PNG exports of the key risk charts for quick reference.

🚀 How to Run
Clone this repository.

Install requirements: pip install pandas matplotlib seaborn

Open Fraud_Analysis_Final.ipynb in Jupyter or VS Code.
