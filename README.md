# APEX MARKETS — Global Stock Intelligence Dashboard

> **61 stocks · 307,000+ records · 25 years of market data (2000–2025)**  
> A full end-to-end data analytics project: raw data → cleaning → analysis → interactive dashboard.

---

## Live Preview

![Dashboard Preview](./assets/preview.png)

> Open `apex_markets_dashboard.html` directly in any browser — no server, no dependencies, no setup.

---

## Project Overview

APEX MARKETS is a self-contained, interactive financial analytics dashboard built to surface meaningful patterns across 61 global stocks spanning two and a half decades of trading data. The project covers the full analytics lifecycle: data acquisition, cleaning, feature engineering, exploratory analysis, and visual storytelling through a production-quality dashboard.

The goal was simple: take messy, real-world stock data and turn it into something a portfolio manager, analyst, or curious investor could actually learn from — without needing a BI tool or a subscription.

---

## Features

### Dashboard Pages

| Page | Description |
|------|-------------|
| **01 Overview** | Executive KPIs, top gainers/losers, return vs. volume bubble chart, full sortable leaderboard |
| **02 Time Series** | Multi-stock monthly avg close trends from 2000–2025, selectable by ticker |
| **03 Industries** | Average return, volatility, and volume benchmarked by industry sector |
| **04 Countries** | Country-level performance comparison with market share breakdown |
| **05 Risk & Volatility** | Volatility distribution, risk-return scatter, drawdown analysis |
| **06 Company Dive** | Per-company deep dive: candlestick charts, return distribution, volume trends |

### Interactive Controls

- **Filter Panel** — Filter simultaneously by country, industry, performance tier (bullish/bearish), volatility band (low/medium/high), and price range
- **Active Filter Chips** — Visual chips display active filters with one-click removal
- **Smart Sort** — Sort the leaderboard by avg return, volume, volatility, avg close, total volume, or all-time high
- **Top N Filter** — Instantly narrow to Top 5 / 10 / 20 / 30 stocks by any metric
- **Reset All** — One-click full filter reset

---

## Dataset

| Attribute | Detail |
|-----------|--------|
| Stocks | 61 global companies |
| Records | ~307,000 daily rows |
| Time Range | January 2000 – 2025 |
| Fields | Date, Open, High, Low, Close, Volume, Ticker, Company, Industry, Country |
| Source | World Stocks dataset (public) |

### Data Cleaning Steps

Raw data required significant preprocessing before analysis:

1. **Null handling** — Identified and removed rows with missing OHLCV values
2. **Type normalization** — Ensured date parsing consistency across all 61 tickers
3. **Return engineering** — Computed daily percentage return per ticker: `(Close - Prev Close) / Prev Close × 100`
4. **Volatility scoring** — Calculated standard deviation of daily returns per stock (annualized basis)
5. **Aggregation** — Built per-ticker summary stats: avg close, avg return, avg volume, total volume, all-time high, max drawdown
6. **Country & industry tagging** — Validated and standardized categorical labels across all records

Cleaning was performed using **Julius AI** for rapid iteration, with manual validation at each stage.

---

## Tech Stack

| Layer | Tools |
|-------|-------|
| Data Cleaning | Julius AI, Python |
| Analysis | Exploratory data analysis (EDA) on aggregated metrics |
| Dashboard | HTML5, CSS3, Vanilla JavaScript |
| Charting | [Chart.js v4.4.1](https://www.chartjs.org/) |
| Design | Custom dark-theme UI (no frameworks) |
| AI Assistance | Claude AI (dashboard UI generation) |

No Tableau. No Power BI. No paid tools. Fully open and browser-native.

---

## Getting Started

```bash
# Clone the repo
git clone https://github.com/yourusername/apex-markets-dashboard.git

# Navigate to the project
cd apex-markets-dashboard

# Open the dashboard
open apex_markets_dashboard.html
# or just double-click the file in your file explorer
```

No npm install. No build step. No backend required. Works offline.

---

## Project Structure

```
apex-markets-dashboard/
│
├── apex_markets_dashboard.html   # Self-contained dashboard (all JS/CSS inline)
├── world_stocks_cleaned.csv      # Cleaned dataset used for analysis
├── assets/
│   └── preview.png               # Dashboard screenshot for README
└── README.md
```

---

## Key Analytical Findings

- **Volatility ≠ Returns**: Several of the highest-volatility stocks in the dataset delivered below-average long-term returns. A handful of mid-volatility names quietly outcompounded the rest.
- **Industry Concentration**: A disproportionate share of positive average daily returns came from fewer than 3 industry sectors across the 25-year window.
- **Volume as a Signal**: Stocks in the top quartile by average volume did not systematically outperform lower-volume peers — suggesting liquidity and performance are largely decoupled at this dataset's scale.
- **Country Dispersion**: Significant variance exists between country clusters, with certain markets showing persistent negative average returns across the full 2000–2025 period.

---

## What I Learned

- End-to-end ownership of an analytics project is fundamentally different from working on isolated tasks. Every design decision upstream (how you clean data, what you aggregate) cascades into what stories you can tell downstream.
- Building a dashboard without a BI tool forces you to think carefully about what actually needs to be interactive versus what's just visual noise.
- Volatility analysis at scale surfaces patterns that single-stock analysis completely misses.

---

## Author

**[Your Name]**  
Data Analyst | [LinkedIn](https://linkedin.com/in/yourprofile) · [Portfolio](https://yourportfolio.com) · [GitHub](https://github.com/yourusername)

---

## License

This project is open-source under the [MIT License](./LICENSE).  
Dataset sourced from public domain world stocks data.
