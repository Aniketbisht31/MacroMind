# MacroMind

---

# **MacroMind Analyst**

### *Automated Bitcoin & Crypto Market Intelligence System*

A fully automated crypto market analyst powered by GPT-5 and n8n. It is built to remove emotional bias like fomo and fud and deliver daily , data-driven investment insights.

**Learn. Automate. Analyze. Repeat.**

---

## **Project Overview**

MacroMind Analyst shows how AI and workflow automation can combine various financial data into a smart decision engine. It continuously fetches, analyzes, and interprets macro, meso, and micro indicators, producing natural-language reports and actionable forecasts every day, free from emotional influence.

The system includes:

* Quantitative data from global macro and on-chain sources
* GPT-5 reasoning for unbiased interpretation
* n8n automation for orchestration, scheduling, and delivery

---

## **System Diagram**

```
        ┌────────────────────────┐
        │  Macro Data Feeds      |
        │ (Yields, Fed Rate, etc)|
        |                        |
        └────────────┬───────────|
                     │
        ┌────────────▼────────────┐
        │  Core Crypto Data       │
        │ (BTC, ETH, Volume, etc.)│
        └────────────┬────────────┘
                     │
        ┌────────────▼────────────┐
        │ On-Chain & Derivatives  │
        │ OI, Funding, Volatility │
        └────────────┬────────────┘
                     |
      ┌──────────────▼──────────────┐
      │ Data Cleaning & Engineering │
      │ (Custom JS indicators)      │
      └──────────────┬──────────────┘
                     │
      ┌──────────────▼──────────────┐
      │ Macro / Micro / Cycle Logic │
      │  → Market Phase Detection   │
      │  → Risk Sentiment Mapping   │
      └──────────────┬──────────────┘
                     │
      ┌──────────────▼──────────────┐
      │ Consolidation & GPT-5 Model │
      │  → Signal Generation        │
      │  → Natural-Language Digest  │
      └──────────────┬──────────────┘
                     │
      ┌──────────────▼──────────────┐
      │ Google Sheet / Dashboard    │
      │ Daily Log + Backtesting     │
      └─────────────────────────────┘
```
![alt text](image.png)

---

## **Workflow Structure**

### I. Data Ingestion & Cleaning

Fetches multi-source data from:

* Macro: Treasury yields, Fed funds rate, inflation expectations
* Crypto Core: BTC, ETH, volume, volatility
* Derivatives: Open interest, funding, DEX metrics
* Sentiment: News APIs, Twitter trends, Google interest

Each dataset is cleaned and standardized in **n8n Code (JS)** nodes, handling nulls, aligning timestamps, and scaling metrics for consistency.

---

### II. Feature Engineering & Micro Analysis

Custom JavaScript logic computes:

* Trend and momentum indicators (EMA, MACD, RSI)
* Volatility clusters and VWAP ratios
* Short-term flow metrics
* Bull/Bear threshold detectors

Outputs are combined into a clean feature set for higher-level modeling.

---

### III. Macro & Fundamental Analysis

Combines traditional finance indicators with blockchain metrics to assess:

* Liquidity and risk conditions
* Market phase (Bull / Bear / Accumulation / Distribution)
* Cross-market correlations (BTC ↔ Gold ↔ Yields ↔ Oil)

---

### IV. Consolidation & Modeling

The final “Clean Sheet Row” merges all features into a single structured JSON. That is passed to a **GPT-5 model** (via OpenAI node) using a dynamic prompt template:

```
Input: {MacroScore}, {MicroSignal}, {Dominance}, {CycleTag}, {SentimentIndex}
→ GPT-5 Output: Natural-language forecast + confidence + suggested action
```

**Example Output:**

> “After the October liquidity dip, the model signals neutral-to-bullish stabilization. Lower yields support risk appetite, but gold’s rise caps momentum. **Action:** Accumulate BTC between 112K and 114K, hold 40% for dips to 106K. **Confidence:** 76% — moderate conviction, improving environment.”

---

### V. Output & Automation

* Append to Google Sheets — daily logs and backtesting archive
* Deliver via Telegram, Email, or WhatsApp — optional AI digest
* n8n Scheduler (Cron) — executes automatically each morning

---

## **Architecture Summary**

| Layer                  | Role                                                       |
| ---------------------- | ---------------------------------------------------------- |
| Macro                  | Global risk and liquidity metrics (Fed, yields, oil, gold) |
| Meso                   | BTC dominance, alt season indicators, risk-on/off signals  |
| Micro                  | Technicals: RSI, MACD, volatility, trend strength          |
| AI Layer (GPT-5)       | Contextual synthesis and narrative generation              |
| Automation Layer (n8n) | Fetching, merging, cleaning, and execution                 |
| Storage / Output       | Google Sheets, Airtable, or dashboards                     |

---

## **Core Principles**

* Bias-Free Analysis — zero FOMO, zero FUD
* Continuous Learning — GPT-5 adjusts based on recent market data
* Transparency — every step visible in n8n workflow
* Human-Like Reports — outputs resemble professional analyst notes
* Data Diversity — combines macro, sentiment, and on-chain data

---

## **Tech Stack**

| Component                       | Purpose                                   |
| ------------------------------- | ----------------------------------------- |
| n8n.io                          | Automation engine for data orchestration  |
| GPT-5 (OpenAI API)              | Market reasoning and report generation    |
| Binance / Glassnode / FRED APIs | Real-time and macro data feeds            |
| Google Sheets / Airtable        | Storage and backtesting                   |
| JavaScript                      | Feature engineering inside n8n Code nodes |

---

## **Example Daily Digest**

```
Date: November 8, 2025
BTC Trend: Bullish Accumulation
Macro Score: 7.2/10 — Liquidity improving
Fear & Greed Index: 68
Alt Season Probability: 42%
Sentiment: Mildly Positive
Action: Accumulate BTC on dips near 112K
Confidence: 76% — moderate conviction
```

---

## **Use Cases**

* Investors and traders — get unbiased, data-driven market intelligence
* Research analysts — automate report generation
* Developers — extend to multi-asset dashboards
* Educators — demonstrate AI and automation working together in finance

---

## **Development Roadmap**

* Add backtesting and performance dashboards
* Integrate contextual memory
* FOMO/FUD sentiment visualization
* Expand coverage: ETH, SOL, macro ETFs
* Add confidence-weighted ensemble scoring

---

## **Disclaimer**

This project is for **educational and research purposes** only. It does **not constitute financial advice**. Always apply independent judgment.

---

## **Support**

If you find this project valuable, **star it on GitHub** and follow for updates. Let’s build transparent, unbiased, and intelligent financial automation together.

---

