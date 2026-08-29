# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This repository contains Pine Script indicators, strategies, and libraries for TradingView. Pine Script files use the `.pine` extension and run directly on TradingView's platform — there is no local build, compile, or test step.

## Development Workflow

Pine Script is developed and tested exclusively in TradingView's built-in Pine Script Editor (tradingview.com → Pine Script Editor). The workflow is:

1. Write/edit `.pine` files in this repo
2. Paste into the TradingView Pine Script Editor
3. Run against chart data to validate behavior
4. Publish or save to TradingView as needed

## Pine Script Conventions

- Always declare the Pine Script version at the top: `//@version=5`
- Scripts must begin with a type declaration: `indicator()`, `strategy()`, or `library()`
- Use `indicator()` for overlays and standalone plots; `strategy()` for backtesting with entries/exits; `library()` for reusable functions shared across scripts
- Pine Script is executed once per bar (historical) and once per real-time tick — avoid side effects that assume sequential execution

## Key Language Notes

- Pine Script is functional and series-based: most values are time series, not scalars
- Use `var` for variables that persist across bars; plain declarations reset each bar
- `na` is the null/missing value; check with `na(x)` before using
- Built-in request functions (`request.security()`, `request.dividends()`, etc.) fetch data from other symbols/timeframes — these count against execution limits
- `ta.*` namespace for technical analysis built-ins (e.g., `ta.sma()`, `ta.rsi()`, `ta.crossover()`)
- `math.*`, `str.*`, `array.*`, `matrix.*` namespaces for utilities
- Input parameters are declared with `input.*()` functions and appear as UI controls in TradingView

## Repository Structure

- `indicators/` — standalone indicator scripts
- `strategies/` — backtesting strategy scripts
- `libraries/` — reusable Pine Script libraries (exportable functions/types)
