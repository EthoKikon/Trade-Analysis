# Trade Analysis: Bitcoin Sentiment & Trader Performance

## 🚀 Project Overview  
This repository explores how Bitcoin market sentiment (Fear vs. Greed) affects individual trader performance. We combine:  
1. **Fear/Greed Index** (daily sentiment score & category)  
2. **Hyperliquid Historical Trades** (execution price, size, PnL, account info)

Our goals:  
- Clean and merge these datasets  
- Uncover patterns (e.g. average profit & win‑rate by sentiment)  
- Statistically confirm differences (ANOVA & Tukey HSD)  
- (Bonus) Build a simple Random Forest to classify winning vs. losing trades  

## 📂 Repository Structure  
Trade-Analysis/
├── D1/ Raw CSVs (never edit)
│ ├── fear_greed_index.csv
│ └── historical_data.csv
├── D2/ Working copies of raw data
├── data/
│ ├── clean_sentiment.parquet
│ ├── clean_trades.parquet
│ └── features/
│ └── trade_features.parquet
├── notebooks/
│ ├── 00_setup_env.ipynb Setup environment & directories
│ ├── 01_data_ingestion.ipynb Load & clean raw data
│ ├── 02_eda.ipynb Exploratory Data Analysis
│ ├── 03_feature_engineering.ipynb Create lag, rolling, aggregate features
│ ├── 04_analysis_modeling.ipynb ANOVA & Random Forest classification
│ └── 05_insights_report.ipynb Final narrative & key takeaways
├── docs/
│ ├── data_dictionary.md Column definitions
│ └── insights_report.md Written report version
└── environment.yml Conda environment specification

## ⚙️ Installation & Setup  
1. **Clone the repo**  
   ```bash
   git clone https://github.com/EthoKikon/Trade-Analysis.git
   cd Trade-Analysis
2. **Create the Environment**
   ```bash
   conda env create -f environment.yml
   conda activate trade-analysis
4. **Launch Jupyter Lab**
   ```bash
   jupyter lab

📒 How to Reproduce
00_setup_env.ipynb

Install imports, set up folder structure, copy raw files to D2/.

01_data_ingestion.ipynb

Load CSVs, parse timestamps, rename/drop columns, save Parquet.

02_eda.ipynb

Plot sentiment over time, PnL distributions, merge data, bar charts, rolling correlations.

03_feature_engineering.ipynb

Build sentiment lags/rolls, trade/account aggregates, save feature matrix.

04_analysis_modeling.ipynb

Run ANOVA + Tukey test, train & evaluate Random Forest classifier.

05_insights_report.ipynb

Read through the narrative, review tables & charts, and export to PDF.

📈 Key Findings
Mean PnL differs by sentiment (ANOVA p < 0.001).

Extreme Greed vs. Extreme Fear: $33 higher average profit in Greed days.

Win‑rate lift: 37 % → 46 % from Fear → Greed.

Predictive model: Random Forest with ROC‑AUC = 0.87.

Top drivers: Trader win‑rate, average size, buy/sell bias; sentiment adds ~18 %.

📝 Notes & Next Steps
The core assignment did not require modeling—models are provided as a bonus.

To extend: integrate live price volatility, explore coin‑level effects, build an interactive dashboard.

