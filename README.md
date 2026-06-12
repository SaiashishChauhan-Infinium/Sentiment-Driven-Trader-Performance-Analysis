# 📊 Bitcoin Market Sentiment vs Hyperliquid Trader Performance

An exploratory data analysis project investigating how Bitcoin market sentiment (Fear & Greed Index) relates to the trading behavior and profitability of real Hyperliquid traders.

## 🧭 Overview

This project merges two real-world datasets — **211,218 on-chain perpetual futures trades** from 32 Hyperliquid accounts (May 2023 – May 2025) and the **daily Bitcoin Fear & Greed Index** (Feb 2018 – May 2025) — to answer a simple question:

> **Does market sentiment (Fear, Greed, Extreme Fear, Extreme Greed) influence how traders behave and how well they perform?**

The analysis covers trading volume, position sizing, win rates, PnL distribution, buy/sell skew, and behavioral differences between top and bottom performing traders — all sliced by sentiment regime.

## 🔍 What's Inside

- **Full Jupyter Notebook** (`sentiment_trader_analysis.ipynb`) — end-to-end, executable analysis
- **14 charts** covering distributions, correlations, win rates, PnL by sentiment, and behavioral patterns
- **Top 10 key findings** + unexpected patterns in Summary Insights.pdf
- **Sentiment-aware trading recommendations** and risk management guidelines
- **Executive summary** suitable for stakeholder presentations
- **Cleaned & merged dataset** ready for further analysis

## 📁 Project Structure

```
project/
├── sentiment_trader_analysis.ipynb   # Main analysis notebook
├── README.md
├── requirements.txt
├── Summary Insignts.pdf
├── data/
│   ├── fear_greed_index.csv          # BTC Fear & Greed Index (2018–2025)
│   └── historical_data.csv           # Hyperliquid trade history (2023–2025)
└── outputs/
    ├── charts/                       # 14 generated PNG charts
    └── merged_dataset.csv            # Cleaned & sentiment-tagged trade data
```

## 🚀 Getting Started

```bash
git clone <repo-url>
cd project
pip install -r requirements.txt
jupyter notebook sentiment_trader_analysis.ipynb
```

Or re-run the full analysis headlessly:

```bash
jupyter nbconvert --to notebook --execute sentiment_trader_analysis.ipynb --output sentiment_trader_analysis.ipynb
```

## 🧪 Methodology

- **Date matching**: Each trade is mapped to the BTC sentiment classification for its execution date (IST → calendar date).
- **Realized PnL focus**: Many rows have `closedPnL = 0` (position-opening trades). Performance metrics (win rate, avg/median PnL) are computed on **closed trades only**.
- **Leverage proxy**: The raw data has no explicit `leverage` column. **Trade size in USD** is used as a transparent proxy for risk-taking/aggressiveness, clearly labeled wherever used.
- **Sentiment ordering**: All charts use a consistent ordinal scale — `Extreme Fear → Fear → Neutral → Greed → Extreme Greed`.

## 💡 Highlights

- Win rates stay close to ~50% across all sentiment regimes — sentiment doesn't predict *direction*, but strongly correlates with **position sizing** and **trade frequency**.
- **Extreme Fear** shows the highest share of losing trades and the largest average loss size.
- **Greed/Extreme Greed** periods show elevated average trade sizes — a signature of overconfidence/FOMO-driven sizing.
- Top-performing traders maintain **consistent average PnL across all sentiment regimes**, suggesting disciplined risk management — not sentiment-timing — drives outperformance.

## 🛠️ Tech Stack

- Python, pandas, NumPy
- Matplotlib, Seaborn
- Jupyter / nbconvert

## 📄 License

Feel free to use, fork, and adapt this analysis for educational or research purposes.