# Prototype testing

## Local automated checks run during delivery

Using Chromium/Playwright in a sandboxed inline-document environment with `__COINSCOPE_DEMO_MODE__=true`:

- Dashboard renders with 12 clearly labeled illustrative assets.
- Global search filters listings to a specific matching coin.
- Clicking a coin opens individual coin details and chart.
- Toggling a watchlist star changes the saved asset set.
- Watchlist displays the saved coins after switching views.
- Trade calculator updates when an amount is entered.
- Theme toggle switches appearance.
- Mobile layout renders at 390px width with no document-level horizontal overflow.
- Mobile navigation menu opens and switches to Markets.
- No JavaScript page errors observed during these interaction checks.

Browser market-network access was not available in the sandbox, so live CoinGecko network success has **not** been independently verified; production cross-browser tests, error monitoring, and load testing are still required. The UI includes a sample-data fallback for offline / rate-limit situations.

## Manual review before giving to client

1. Open `/?demo=1` on GitHub Pages and verify sample-data label and responsive layout.
2. Open the base URL without `?demo=1` and verify the **Live market data** badge or the explicitly labeled **Sample data** fallback.
3. Test all navigation items, search, gainers/losers filtering, coin details and timeframe buttons.
4. Save a coin in the watchlist, refresh the browser, and ensure it remains saved.
5. Toggle light/dark mode and refresh.
6. Check the simulator and its non-transactional disclaimer.
7. Test on actual Android/iOS devices and in all target browsers before client delivery.
8. Review the client's original design/source files before proposing actual refactoring or preserved functionality.