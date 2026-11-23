# Local Quant Lab — Free Edition

**A crypto backtester that refuses to flatter you.**

One HTML file. Double-click it and you have a research workbench for crypto perpetual futures: import candles, run strategies, and look at the equity curve with an out-of-sample split staring back at you.

No account. No API key. No install. No cloud. Runs offline in your browser — your candles never leave the page.

**[▶ Try the live demo](https://hymzh945-hash.github.io/local-quant-lab/)** (loads with demo data in one click)

![Backtest view](screenshots/01-backtest.png)

---

## Why another backtester?

Most free backtesters answer one question: *how much would this have made?* That is the least useful question in the file, because with enough parameter combinations you can always make the past look profitable.

This one is built around the two questions that actually matter:

1. **Is this result robust, or did I fit the noise?**
2. **Did I test the parameters on data the strategy never saw?**

The free edition gives you the core engine and the equity curve. The Standard edition gives you the tools that answer those two questions properly — parameter heatmaps and walk-forward validation.

---

## What is in the free edition

- Backtest engine over OHLC candles, long/short, with fee + slippage modelling
- **4 strategies** — SMA cross, Donchian breakout, RSI mean reversion, buy-and-hold benchmark
- CSV import — any exchange export works, the loader guesses columns and tells you what it mapped
- OKX public data fetch (no key, no account)
- Equity curve vs 1x buy-and-hold, headline metrics (CAGR, max drawdown, Sharpe, win rate, trade count)
- In-sample / out-of-sample split shown on the result card
- Bilingual UI (English / 中文)

## What the Standard edition adds

- **14 strategies** — channel breakout, ATR breakout, regime filter, Keltner, Supertrend, momentum, multi-timeframe, Bollinger, VWAP deviation, MACD, and more
- **Parameter sensitivity heatmap** — brute-force fast × slow into a grid. A broad green block means the edge survives parameter choice. One isolated bright cell means you found a coincidence.
- **Walk-forward validation** — pick parameters on earlier data, evaluate on the window immediately after, roll forward, report out-of-sample win rate per fold
- **Cross-asset replay** — the same parameter set across BTC / ETH / SOL, so you can see whether the edge is in the strategy or in the asset
- **One-click research report** — standalone HTML with every chart embedded, ready to send to someone
- **Method handbook** — six chapters: look-ahead bias, why Sharpe lies, overfitting, funding costs, leverage and liquidation

![Parameter heatmap](screenshots/03-heatmap.png)

---

## Quick start

1. Download `index.html` (or clone the repo)
2. Double-click it — it opens in any modern browser, offline
3. Click **Load demo data** to see the whole workflow in about 20 seconds
4. Or click **Choose CSV file** and pick `sample-data/BTC_perp_1D.csv`

CSV needs a timestamp column plus open/high/low/close. Volume is optional.

---

## Cost model, stated plainly

Fees and slippage are applied per side, funding is settled against real funding history when you import it, and maintenance margin plus forced liquidation are modelled on the position. If you turn the cost model off, the equity curve will look better — that is the point of having the switch visible.

---

## Honest limits

- This is a historical analysis tool. It does not connect to accounts, does not place orders, and does not emit signals.
- It does not tell you what will happen next. Nothing does.
- Results are only as good as your data. Gaps and exchange downtime in the CSV will show up as fake edges.
- Free edition only ships 4 strategies and no heatmap / walk-forward. That is a deliberate line, not an accident.

---

## Links

- **Free sample + Standard edition:** https://hymz.gumroad.com/l/local-quant-lab
- **Live demo:** https://hymzh945-hash.github.io/local-quant-lab/

## License

Free Edition — evaluation copy, personal use. Not for resale or redistribution. See `LICENSE.txt`.

---

Built by Zihan Ma. Questions or bugs: open an issue here.
