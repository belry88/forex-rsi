# Changelog

All edits to Forex RSI. Newest first. Versions 1–9 were built before this repository existed and are reconstructed from the project notes; from version 10 on, every entry matches a commit and pull request.

## v10 · 2026-10-22 · GitHub repository and Pages copy
- Project moved into the `belry88/forex-rsi` repository; `main` is served by GitHub Pages, changes arrive through the `claude-code` branch.
- Outside claude.ai (e.g. the GitHub Pages copy) the notice now says there is no market data and links to the live app.

## v9 · 2026-10-22 · Tooltips switch
- Added a **TOOLTIPS** checkbox in the control bar. Off hides hover/tap explanations, dotted underlines and the help cursor; on a phone, tapping a tile then filters straight away.
- Choice is saved per viewer in their browser.
- The **i** buttons on news and event risk still open on click.

## v8 · 2026-10-22 · Shared snapshot (made in a Claude chat)
- Page shared by link.
- When the owner opens the page, the latest bars, events and headlines are saved to the artifact's database. Viewers without a TradingView connector see that snapshot, with a notice of when it was saved.

## v7 · 2026-10-21 · Timeframe switch and summary
- **Daily / Weekly / Monthly** switch as the main filter; every panel recalculates.
- 8 currency tiles with D/W/M score squares, **Top setups** list, strength-trend heatmap at the top.
- Formula hovers on every column header and on key values (% EMA, RSI, Diff, Side, bars since cross, EMA slope, Δ Diff).
- Sticky control bar with a live status line; on a phone, filter taps scroll the results into view.
- New quick filter: **D·W·M aligned**.

## v6 · 2026-10-21 · Phone layout
- Currency cards, swipeable quick keys, pair column pinned in the table, larger tap targets.

## v5 · 2026-10-21 · Terminal one-page summary
- Bloomberg-style look (IBM Plex Mono and Plex Sans Condensed).
- Currency strength monitor with trend days and "why" notes.
- Excel-style sorting and ▾ column filters; quick-filter keys; filter chips.
- Major events and headlines from TradingView with source notes.

## v4 · 2026-10-21 · Data-terminal rebuild
- Rebuilt with the taste-skill "Data terminal" style: results table instead of hover cards, clickable currency strength ladder, finding line.

## v3 · 2026-10-21 · Calmer background
- Removed colour blobs, near-solid panels, higher-contrast text.

## v2 · 2026-10-21 · Renamed to Forex RSI
- Added the Opportunities page with filters and presets, RSI 14, glass design.

## v1 · 2026-10-21 · FX Strength Board
- Daily close vs EMA 20 for 28 pairs via the TradingView connector.
- Currency ranking, 8×8 matrix, 30-day history heatmap, pair board.
