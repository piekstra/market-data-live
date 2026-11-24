# market-data-live

Real-time streaming market data for equities and ETFs.

> **Status:** Placeholder — not yet implemented.

## Purpose and Principles

This repository will handle **real-time and streaming market data** — the complement to [market-data](https://github.com/piekstra/market-data), which covers historical and recent candle data.

It is part of a modular ecosystem of independent repositories. Each repo has a focused responsibility and can be used on its own or composed with others.

### Intended Scope

- WebSocket-based streaming of live quotes, trades, and/or bars
- Sub-second data delivery for real-time trading systems
- Connection management, reconnection, and heartbeat handling
- A clean Rust API for consumers to subscribe to symbols and receive updates

### What This Repo Is Not

- **Not for historical data.** Use [market-data](https://github.com/piekstra/market-data) for historical and recent candle data.
- **Not for options data.** Use [options-data](https://github.com/piekstra/options-data) for options-specific data.
- **Not a trading engine.** No strategy logic, order management, or execution belongs here.
- **Not provider-specific.** The streaming layer should be an abstraction over providers.

### Relationship to market-data

| Concern | market-data | market-data-live |
|---------|-------------|------------------|
| Data freshness | Historical through today (on-demand fetch) | Real-time streaming |
| Update frequency | 5-minute candles | Sub-second / tick-level |
| Storage | Parquet files on disk | In-memory / ephemeral |
| Access pattern | Read ranges of dates | Subscribe to live updates |
| Protocol | HTTP REST APIs | WebSocket |

## License

Copyright (C) 2026 piekstra. Licensed under the GNU Affero General Public
License, version 3 only (AGPL-3.0-only); see [LICENSE](LICENSE).
