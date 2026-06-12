# Bitcoin Sentiment vs Hyperliquid Trader Performance Analysis

## Overview
This project analyzes the relationship between Bitcoin market sentiment (Fear & Greed Index) and Hyperliquid trader performance using 211,224 trade records (32 accounts, May 2023 - May 2025) merged with daily BTC sentiment classifications (Feb 2018 - May 2025).

## Project Structure
```
project/
├── sentiment_trader_analysis.ipynb   # Main analysis notebook
├── README.md
├── requirements.txt
├── data/
│   ├── sentiment.csv                 # BTC Fear & Greed Index
│   └── historical_data.csv           # Hyperliquid trade history
└── outputs/
    ├── charts/                       # All generated PNG charts
    ├── merged_dataset.csv            # Cleaned & merged dataset
    └── final_report.pdf              # Stakeholder-ready PDF report
```

## How to Run
```bash
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute sentiment_trader_analysis.ipynb --output sentiment_trader_analysis.ipynb
```

## Methodology Notes
- **Leverage proxy**: The raw Hyperliquid data has no explicit `leverage` field. Trade size (USD) is used as the primary proxy for risk-taking/aggressiveness, clearly labeled throughout.
- **Date matching**: Each trade is matched to the BTC sentiment classification of its execution date (IST timezone, normalized to calendar date).
- **Closed PnL**: Many rows have `closedPnL = 0` (position-opening trades). Performance analysis focuses on rows with non-zero realized PnL ("closed trades").

## Key Sections in Notebook
1. Introduction & Dataset Description
2. Data Cleaning & Preprocessing
3. Data Merging
4. EDA (sentiment distribution, PnL distribution, volume, trade sizing, buy/sell mix)
5. Sentiment vs Performance (win rates, PnL by regime, size vs PnL, correlations)
6. Behavioral Pattern Analysis (aggressiveness, trading intensity, loss patterns, top vs bottom traders)
7. Key Findings (Top 10 insights)
8. Trading Recommendations
9. Executive Summary
