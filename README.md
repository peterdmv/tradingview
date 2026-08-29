# TradingView Pine Scripts

Pine Script indicators, strategies, and libraries for [TradingView](https://www.tradingview.com/).

## Overview

This repository holds `.pine` source files developed and tested in TradingView's
built-in Pine Script Editor. There is no local build, compile, or test step —
Pine Script only runs on TradingView's platform.

## Repository structure

```
indicators/    standalone indicator scripts
strategies/    backtesting strategy scripts (entries/exits)
libraries/     reusable Pine Script libraries (exportable functions/types)
```

Only `indicators/` currently has content.

## Indicators

| Script | Title on TradingView | Description |
|---|---|---|
| [`MAAT.pine`](indicators/MAAT.pine) | Moving Averages For All Timeframes | Configurable moving-average overlay with independent sets of MAs for intraday, daily, weekly, and monthly timeframes (SMA/EMA/RMA/VWMA/WMA), per-line width and color, optional MA clouds, intraday VWAP, and a weekly-on-daily overlay. |
| [`PowerTrend.pine`](indicators/PowerTrend.pine) | PowerTrend | Trend-start/trend-end detector (a recreation of Webby's Power Trend). Flags an uptrend start when price holds above a rising 21 EMA / 50 SMA stack for a configurable number of days and closes green; flags trend end on an EMA/SMA crossunder or a >10% pullback circuit breaker. |
| [`WebbyPctOff52WkHigh.pine`](indicators/WebbyPctOff52WkHigh.pine) | Webby's ATR Off 52-Week High | Recreation of Webby's ATR-off-52-week-high indicator. Measures distance from the 52-week high in ATR units, color-zoned (green/yellow/red) to gauge how extended or beaten-down a stock is. |
| [`WebbyRSI.pine`](indicators/WebbyRSI.pine) | Webby RSI | Recreation of Mike Webster's (IBD) "Webby RSI" momentum oscillator, built from EMA/ATR/SMA extension, with warning and caution color states. |
| [`StockStats.pine`](indicators/StockStats.pine) | Stock Stats | A single-row "chip" dashboard of key stats: market cap (with Nano/Micro/Small/Mid/Large/Mega cap category), shares float, ADR%, ATR, low-of-day distance, Trend Intensity (65-day), 52-week high, Volume Buzz, and Run Rate — a time-of-day-adjusted projection of full-session volume, with separate models for regular US equity sessions and 24/7 crypto tickers (e.g. BTCUSD). |

## Development workflow

1. Write/edit `.pine` files in this repo.
2. Paste into the TradingView Pine Script Editor (tradingview.com → Pine Script Editor).
3. Run against chart data to validate behavior.
4. Publish or save to TradingView as needed.

See [`CLAUDE.md`](CLAUDE.md) for Pine Script conventions used across this repo.

## License

All scripts are licensed under the [Mozilla Public License 2.0](https://mozilla.org/MPL/2.0/),
per the header in each file.

## Credits

Several indicators here are original recreations of concepts published by other
authors, credited in each file's header:

- **JohnMuchow** — original version of the moving-averages-for-all-timeframes concept (`MAAT.pine`)
- **Mike Webster** (IBD/O'Neil) — original concept behind "Webby's" Power Trend, ATR-off-52-week-high, and RSI indicators
- **ArmerSchlucker** — original version of the stats table indicator (`StockStats.pine`)
- **Qullamaggie / MikeC / TheScrutiniser / GlinckEastwoot** — ADR% formula
- **Stockbee** — Trend Intensity (TI65) indicator ([source](https://stockbee.blogspot.com/2018/03/how-to-setup-trend-intensity-scans-and.html))
