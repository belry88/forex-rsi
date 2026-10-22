# Forex RSI: working notes for Claude

Single-page app in `index.html` (terminal-style FX currency strength monitor). The owner is not a developer: explain results in plain language.

## Where things live

- Repo: https://github.com/belry88/forex-rsi (`gh` is at `~/.local/bin/gh`, signed in as belry88)
- GitHub Pages serves `main`: https://belry88.github.io/forex-rsi/ (layout only, no market data)
- Live app with data (claude.ai artifact): https://claude.ai/artifact/GUt6EJFjd3FK1A1whLsbnZ
  - Uses the viewer's TradingView connector (`mcp-tv-get-ohlcv`, `mcp-tv-get-economic-calendar`, `mcp-tv-get-news`) and an artifact `db` snapshot (`snap/*`, owner writes). Shared by link.

## Every change, in this order

1. If the live artifact may have been edited elsewhere (e.g. a Claude chat), read it with the Artifact tool (`action: "read"`), copy it into `index.html` without the publish skeleton (file starts at `<title>`), and commit it as its own changelog entry first.
2. Work on branch `claude-code` (`git switch claude-code && git pull`).
3. Edit `index.html`. Keep the existing design, the 28 pairs, the formulas in README.md and the TradingView/snapshot data flow.
4. Syntax-check the inline script (e.g. extract it and run `node --check`; Node is at `~/.local/node/bin/node`).
5. Add a `CHANGELOG.md` entry at the top: next version number, date, short plain-language bullets.
6. Commit (end the message with the co-author line), push, open a PR into `main` with `gh pr create`, merge it with `gh pr merge --merge`, then fast-forward `claude-code` to `main` and push.
7. Republish the live app: Artifact tool, `file_path` = this repo's `index.html`, `url` = the artifact link above. Omit `capabilities` so the stored ones (mcp, db, user) carry forward.
8. Update the Obsidian note `~/Claude/Trading/Forex RSI.md` (setup log line).

## Never

- Commit market data, prices or headlines (TradingView licence).
- Force-push or rewrite `main`.
- Delete files permanently: move them to `~/.Trash`.
