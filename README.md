# Should I Be Trading?

A Bloomberg Terminal-style market intelligence dashboard that evaluates the current stock market environment and outputs a clear, actionable swing trading decision.

## Live Dashboard

**[https://appforgelabs.github.io/ShouldIBeTrading](https://appforgelabs.github.io/ShouldIBeTrading)**

## What It Does

- **YES / CAUTION / NO** — single high-signal trading verdict based on a weighted market quality score
- **Market Quality Score (0–100%)** — composite of Volatility (25%), Momentum (25%), Trend (20%), Breadth (20%), Macro (10%)
- **Execution Window Score** — separate metric evaluating whether setups are actually working right now
- **All 11 S&P sector ETFs** — heatmap with 5-day performance and 50d SMA status
- **Bloomberg terminal aesthetic** — dark navy/black, green monospace, sharp borders
- **Auto-refreshes every 45 seconds** from Yahoo Finance (client-side, no backend)
- **FOMC alert banner** — flags pre-meeting windows with position sizing warning
- **Swing / Day mode toggle** — adjusts score thresholds
- **Terminal Analysis** — auto-generated plain-English regime summary

## Data Sources

- Yahoo Finance (via CORS proxy) — SPY, QQQ, VIX, TNX, DXY, all sector ETFs
- No API keys required. No backend. Pure static HTML.

## Scoring Logic

| Category | Weight | Inputs |
|---|---|---|
| Volatility | 25% | VIX level, 5d slope, 1Y percentile |
| Momentum | 25% | Sector 5d performance spread, tech leadership |
| Trend | 20% | SPY vs 20/50/200d SMA, QQQ vs 50d, RSI 14d |
| Breadth | 20% | Sectors above 50d SMA count |
| Macro | 10% | 10Y yield, DXY, FOMC proximity |

**Decision thresholds:** ≥80 → YES | 60–79 → CAUTION | <60 → NO

## Built By

[Appforgelabs](https://github.com/Appforgelabs) · Powered by Luka (The Machinist's Market Maker)

> Not financial advice. For educational and research purposes only.
