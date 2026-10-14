# CoinScope — Crypto Market Dashboard Prototype

A modern, dependency-free frontend prototype for a cryptocurrency market website. Built to demonstrate user interface quality, responsive layout, dynamic markets, and safe integration patterns before reviewing a client's existing source files.

## Features

- Responsive desktop and mobile interface, collapsible navigation, accessible controls
- Live market listings from CoinGecko's public `/coins/markets` endpoint (best effort)
- Client-side search, sortable listings, gainers/losers filters
- Individual coin details and 7-day sparklines, with attempts to load 24-hour / 30-day chart data from `/coins/{id}/market_chart`
- Watchlist saved in `localStorage`
- Non-transactional trade calculator (no accounts, wallets, funds, or orders)
- Light/dark theme, status of data source, manual refresh
- Session cache (1 minute) to limit unnecessary requests
- Explicit illustrative sample data fallback when public API is unavailable or rate limited
- No private API credentials in frontend code

## Local preview

Run a local static server, for example:

```bash
python -m http.server 5173
```

Open http://localhost:5173

To force the sample-data mode (works offline), open http://localhost:5173/?demo=1.

## GitHub Pages

Upload the folder's contents **to the root of a new public GitHub repository** (`index.html`, `styles.css`, `app.js`, `assets/`). Then select **Settings → Pages → Deploy from a branch → main → /(root)**. Open the published URL once the deployment finishes.

There is no build step and no environment variable to set for the read-only demonstration.

## Production API credential handling

This proof of concept uses CoinGecko's public API without a private key. If a paid API is required, store the key **only on a trusted backend** or serverless endpoint and call that endpoint from the browser. Never put API secrets inside JavaScript bundles, `VITE_*` variables, or public Git history. Add backend caching, request limits, and rate-limit/error handling. The browser prototype alone is not a secure production trading system.

## Scope disclaimer

This is an independent demo—not an update to the client's original project files, which have not been supplied for review. API availability is not guaranteed; the interface clearly labels **Sample data** when market requests fail. The sample prices and charts are illustrative and must never be presented as live market quotes. There is no order execution, exchange API, deposit, or wallet support.

Market data powered by CoinGecko when online: https://www.coingecko.com/