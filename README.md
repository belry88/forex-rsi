# Forex RSI

Terminal-style currency strength monitor for the 8 major currencies (AUD, CAD, CHF, EUR, GBP, JPY, NZD, USD) and all 28 pairs. Each pair's close is compared with its 20-period EMA on daily, weekly or monthly bars. Every currency is scored 0–7 by how many of the other seven it beats, and pairs are ranked by the gap between their two scores.

- **Live app (with data):** https://claude.ai/artifact/GUt6EJFjd3FK1A1whLsbnZ
- **GitHub Pages copy (layout only):** https://belry88.github.io/forex-rsi/

## Where the data comes from

Prices, the economic calendar and headlines load through each viewer's own **TradingView connector inside claude.ai**. Viewers without the connector see the owner's last saved snapshot, also stored in claude.ai.

The GitHub Pages copy has no access to either, so it shows the layout with a link to the live app. No market data is stored in this repository.

## Method

From the `ForexRSI_5` workbook ("RSI (2)" tab):

| Term | Formula |
|---|---|
| EMA 20 | α = 2 ÷ 21; EMAₜ = α × Closeₜ + (1 − α) × EMAₜ₋₁ |
| % from EMA | (Close − EMA20) ÷ EMA20 × 100 |
| Signal | Close > EMA20 → base currency Strong against the quote |
| Score | Number of the other 7 currencies a currency beats (0–7) |
| Diff | \|Base score − Quote score\| |
| RSI 14 | Wilder: RS = avg gain ÷ avg loss; RSI = 100 − 100 ÷ (1 + RS) |

## Branches and workflow

| Branch | Purpose |
|---|---|
| `main` | What GitHub Pages serves and what is published to claude.ai |
| `claude-code` | Every change from Claude Code lands here first |

Each change is committed on `claude-code`, logged in [CHANGELOG.md](CHANGELOG.md), opened as a pull request into `main` and merged. Changes made to the live app from a Claude chat are pulled back into the repo the same way, so the history stays complete.

## Remote Control

Start a Claude Code session for this repo that you can drive from the Claude mobile app or claude.ai/code:

```
fxrc
```

(`fxrc` is a shell shortcut for `cd ~/Claude/Trading/forex-rsi && claude remote-control --name "Forex RSI" --permission-mode acceptEdits`.) The session follows the steps in [CLAUDE.md](CLAUDE.md).

Not investment advice.
