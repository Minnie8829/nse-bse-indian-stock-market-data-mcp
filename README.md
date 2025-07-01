<p align="center">
  <a href="https://tapetide.com/mcp">
    <img src="https://assets.tapetide.com/logo-filled-tight.svg" alt="Tapetide — Indian Stock Market MCP Server" width="80" />
  </a>
</p>

<h1 align="center">Indian Stock Market MCP Server — NSE & BSE Data for Claude, ChatGPT & Cursor</h1>

<p align="center">
  <strong>The Indian stock market MCP server for NSE and BSE: 55 tools to search, screen and analyze all 8,200+ listed stocks from Claude, ChatGPT, Cursor, VS Code, Codex, Gemini CLI and any MCP client.</strong>
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/tapetide-mcp"><img src="https://img.shields.io/npm/v/tapetide-mcp?label=npm" alt="npm version" /></a>
  <a href="https://www.npmjs.com/package/tapetide-mcp"><img src="https://img.shields.io/npm/dm/tapetide-mcp" alt="npm downloads" /></a>
  <a href="https://pypi.org/project/tapetide-mcp/"><img src="https://img.shields.io/pypi/v/tapetide-mcp?label=pypi" alt="PyPI version" /></a>
  <a href="https://registry.modelcontextprotocol.io/v0/servers?search=com.tapetide/stock-research-mcp"><img src="https://img.shields.io/badge/MCP%20Registry-com.tapetide%2Fstock--research--mcp-blue" alt="Official MCP Registry" /></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="MIT License" /></a>
  <a href="https://glama.ai/mcp/servers/Tapetide-hq/nse-bse-indian-stock-market-data-mcp"><img src="https://glama.ai/mcp/servers/Tapetide-hq/nse-bse-indian-stock-market-data-mcp/badges/score.svg" alt="nse-bse-indian-stock-market-data-mcp MCP server" /></a>
</p>

<p align="center">
  <a href="https://tapetide.com/mcp">Documentation</a> •
  <a href="#quick-start">Quick Start</a> •
  <a href="#works-with">Client Setup Guides</a> •
  <a href="#tools">55 Tools</a> •
  <a href="#example-prompts">Example Prompts</a> •
  <a href="https://www.npmjs.com/package/tapetide-mcp">npm</a> •
  <a href="https://pypi.org/project/tapetide-mcp/">PyPI</a>
</p>

---

Tapetide is an **Indian stock market MCP server** that gives AI assistants live, structured data on every **NSE** and **BSE** listed company, from Nifty 50 and Sensex heavyweights to SME stocks. Connect it to **Claude**, **ChatGPT**, **Cursor**, **VS Code**, **Codex** or **Gemini CLI** and ask in plain English for share prices, quarterly financials, a 326-ratio stock screener, technical indicators, FII/DII flows, option chains and IV, corporate filings, IPOs, bulk deals and your portfolio P&L.

**One-line install** (Claude Code, with a free token from [tapetide.com/settings/tokens](https://tapetide.com/settings/tokens)):

```bash
claude mcp add tapetide -e TAPETIDE_TOKEN=your_token_here -- npx -y tapetide-mcp
```

Or skip the install entirely and add the remote server URL `https://mcp.tapetide.com/mcp` in claude.ai, ChatGPT, Grok or any client that supports remote MCP. You sign in with Google.

**55 tools** · **8,200+ NSE/BSE stocks** · **Remote (OAuth) or local (npx / uvx)** · **Free tier** · [Setup guides for 16 clients](https://tapetide.com/mcp)

## Works with

Step-by-step setup guides for every major MCP client:

| Chat apps | Code editors & IDEs | Terminal agents |
|---|---|---|
| [Claude.ai](https://tapetide.com/mcp/claude-ai) | [Cursor](https://tapetide.com/mcp/cursor) | [Claude Code](https://tapetide.com/mcp/claude-code) |
| [ChatGPT](https://tapetide.com/mcp/chatgpt) | [VS Code (GitHub Copilot)](https://tapetide.com/mcp/vscode) | [Codex CLI](https://tapetide.com/mcp/codex) |
| [Claude Desktop](https://tapetide.com/mcp/claude-desktop) | [Windsurf](https://tapetide.com/mcp/windsurf) | [Gemini CLI](https://tapetide.com/mcp/gemini-cli) |
| [Grok](https://tapetide.com/mcp/grok) | [Kiro](https://tapetide.com/mcp/kiro) | [OpenCode](https://tapetide.com/mcp/opencode) |
| | [Zed](https://tapetide.com/mcp/zed) | [Command Code](https://tapetide.com/mcp/commandcode) |
| | [Cline](https://tapetide.com/mcp/cline) | |
| | [Antigravity](https://tapetide.com/mcp/antigravity) | |

Any other client that speaks the Model Context Protocol works too, over remote HTTP or local stdio.

## Quick Start

### Option 1: Remote MCP (No install — claude.ai, chatgpt.com, Grok, Gemini)

Add this URL directly in your AI chat app:

```
https://mcp.tapetide.com/mcp
```

Authentication happens automatically via Google OAuth. No token needed.

### Option 2: Remote MCP with Token (Claude Code, VS Code, Kiro, Zed)

For code editors that support URL-based MCP servers with custom headers:

1. Get a free token at [tapetide.com/settings/tokens](https://tapetide.com/settings/tokens)
2. Add to your MCP config:

```json
{
  "mcpServers": {
    "tapetide": {
      "type": "url",
      "url": "https://mcp.tapetide.com/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_TOKEN_HERE"
      }
    }
  }
}
```

### Option 3: Local MCP via npm (Claude Code, Codex, Cursor, Windsurf, VS Code, Gemini CLI, Kiro, OpenCode)

For stdio-based MCP clients. No cloning or building required — runs via `npx`:

1. Get a free token at [tapetide.com/settings/tokens](https://tapetide.com/settings/tokens)
2. Add to your MCP config:

```json
{
  "mcpServers": {
    "tapetide": {
      "command": "npx",
      "args": ["-y", "tapetide-mcp"],
      "env": {
        "TAPETIDE_TOKEN": "your_token_here"
      }
    }
  }
}
```

> **Node.js 18+** required for the local option. Run `node --version` to check.

### Gemini CLI extension

```bash
gemini extensions install https://github.com/Tapetide-hq/nse-bse-indian-stock-market-data-mcp
```

You'll be prompted for your Tapetide token on install.

### Install as a Claude Code plugin

This repo is also a one-plugin Claude Code marketplace. Run these two commands inside Claude Code:

```
/plugin marketplace add Tapetide-hq/nse-bse-indian-stock-market-data-mcp
/plugin install tapetide-indian-stock-market@tapetide
```

On Claude Code 2.1.275 or later, one line does both:

```
/plugin install tapetide-indian-stock-market --marketplace Tapetide-hq/nse-bse-indian-stock-market-data-mcp
```

The plugin connects to the remote server at `https://mcp.tapetide.com/mcp`, so there is nothing to install locally. Run `/mcp` and pick `tapetide` to sign in with Google the first time.

Prefer a local stdio server with a personal token instead? Skip the plugin and add the npm package directly ([get a free token](https://tapetide.com/settings/tokens)):

```bash
claude mcp add tapetide -e TAPETIDE_TOKEN=your_token_here -- npx -y tapetide-mcp
```

### Option 4: Local MCP via Python (uvx / pip)

Same bridge, packaged for Python 3.10+ — [`tapetide-mcp` on PyPI](https://pypi.org/project/tapetide-mcp/) ([source](https://github.com/Tapetide-hq/nse-bse-indian-stock-market-data-mcp-python)):

```json
{
  "mcpServers": {
    "tapetide": {
      "command": "uvx",
      "args": ["tapetide-mcp"],
      "env": {
        "TAPETIDE_TOKEN": "your_token_here"
      }
    }
  }
}
```

## How It Works

```
┌─────────────────┐     stdio (JSON-RPC)     ┌──────────────────┐     HTTPS      ┌─────────────────────┐
│  AI Assistant   │ ◄──────────────────────► │  tapetide-mcp    │ ◄────────────► │  mcp.tapetide.com   │
│  (Claude, etc.) │                           │  (npm package)   │                │  (Cloudflare Worker) │
└─────────────────┘                           └──────────────────┘                └─────────────────────┘
```

The npm package is a lightweight stdio bridge with zero runtime dependencies. It:

- Reads JSON-RPC from stdin, forwards to the remote Tapetide MCP server, writes responses to stdout
- Auto-detects framing: Content-Length (VS Code, Claude Desktop) or newline-delimited JSON (Kiro, Claude Code)
- Exchanges your refresh token for a 1-hour HMAC access token, auto-refreshes before expiry
- Handles SSE responses from the remote server
- Identifies your MCP client to the remote via `User-Agent`, and echoes the negotiated protocol version
- Warns on stderr when the server rate-limits a call, naming the retry delay
- Replays the `Mcp-Session-Id` the server mints at `initialize` on every later request, so the remote can tie a session's calls together
- Forwards MCP Apps traffic untouched — `resources/list`, `resources/read` and the `_meta.ui` hints on `get_price_history`, `market_heatmap` and `screen_stocks` reach your client exactly as the server sends them

All 55 tools and their logic run on the remote server — the npm package is just the transport layer.
Because it forwards JSON-RPC verbatim, tools shipped on the remote are available immediately without
upgrading this package.

## Authentication

| Method | How it works | Best for |
|--------|-------------|----------|
| **Google OAuth** | Browser sign-in, automatic token refresh | AI chat apps (Claude.ai, ChatGPT, Grok, Gemini) |
| **Personal Token (remote)** | `Authorization: Bearer tpt_rt_...` header | Code editors with URL-based MCP (VS Code, Kiro, Zed) |
| **Personal Token (local)** | `TAPETIDE_TOKEN` env var via npx | stdio MCP clients (Cursor, Windsurf, Claude Desktop, Codex) |

Generate a free personal token at [tapetide.com/settings/tokens](https://tapetide.com/settings/tokens). Works for both remote and local MCP.

## Tools

> Tip: ask your assistant to call `read_me` first. It returns the full in-session guide — every
> tool by category, usage patterns, and the rules the server expects clients to follow.
>
> Three tools carry an interactive view for hosts that support [MCP Apps](https://github.com/modelcontextprotocol/ext-apps)
> (Claude, Claude Desktop, VS Code Copilot): `get_price_history` renders the price and volume chart,
> `market_heatmap` the index treemap, and `screen_stocks` the sortable results table. Text-only hosts
> get the same JSON result with nothing missing.

<!-- tools:start — mirrors the server's tool catalog. Checked against the live server's tools/list by
     scripts/check-catalog-parity.mjs (CI: .github/workflows/ci.yml). When the catalog changes,
     regenerate this block; do not hand-edit an individual count. -->

### 🔍 Discovery & Screening (5 tools)

| Tool | Description |
|------|-------------|
| `search_stocks` | Resolve a company to its symbol by name, symbol, BSE code, or ISIN — including brand names and post-rename aliases (`Zomato` → `ETERNAL`). Filter by sector/industry. |
| `screen_stocks` | Fundamental screener over 326 ratios — PE, ROCE, sales growth, debt/equity, Piotroski score. Plain-English query syntax with AND/OR logic and cross-field comparisons. |
| `screen_stocks_technical` | Real-time technical screener — RSI, MACD, SMA/EMA crossovers, Bollinger Bands, ADX, volume, momentum. Supports `crosses_above`/`crosses_below`. |
| `get_screener_ratios` | Search or browse the full 326-ratio catalog to get exact ratio names for a query. |
| `get_trending_stocks` | Today's top gainers, losers, and most-active stocks from the Nifty 500. |

### 📊 Company Analysis (9 tools)

| Tool | Description |
|------|-------------|
| `get_company_profile` | Full overview — sector, business summary, pros/cons, fundamentals, growth metrics, current quote. Optionally add technicals (20+ indicators), analyst ratings, and peers in the same call. |
| `get_stock_quote` | Live price — LTP, change %, volume, market cap, PE, PB, 52-week high/low. |
| `get_batch_quotes` | Up to 20 stock quotes in a single call. |
| `get_price_history` | Daily or weekly OHLCV with delivery %. Up to 2,000 sessions per call, pageable further back. |
| `get_financials` | Quarterly + annual P&L, balance sheet, cash flow, and ratios. Each period is stamped with when it was actually published, so backtests can avoid look-ahead bias. |
| `get_shareholding` | Promoter, FII, DII, and public holdings quarter by quarter. |
| `get_forecasts` | Analyst EPS, revenue, EBITDA, net income, ROA, and ROE estimates against actuals — for spotting earnings surprises. |
| `get_stock_events` | Sentiment-tagged news, corporate actions (dividends, splits, bonuses, AGMs), and filings (results, presentations, concall transcripts, annual reports). |
| `get_stock_ownership` | Dividend history with yields + which mutual fund schemes hold the stock and at what share of AUM. |

### 🏛️ Market-Wide Data (11 tools)

| Tool | Description |
|------|-------------|
| `get_market_pulse` | The at-a-glance daily snapshot — FII/DII net flows, Nifty 50 valuations, and India VIX in one call. |
| `get_fii_dii_detail` | 30 days of daily cash-market flows, F&O participant long/short OI, weekly/monthly/yearly aggregates, buy/sell streaks, cumulative net flows. |
| `get_fii_dii_flows` | Alias of `get_fii_dii_detail`. |
| `get_fpi_sectors` | FPI investment by sector — AUM share, fortnightly change, 1-year cumulative flow. |
| `get_market_news` | Market-wide news across categories with sentiment and related symbols. |
| `get_market_data` | One dispatcher for seven daily feeds via `dataset`: `deals`, `fno_ban`, `deliveries`, `ipo`, `mtf`, `slbm`, `signals`. |
| `market_heatmap` | Every constituent of an index with market cap, PE, PB, returns from 1d to 5y, volume, sector — 16 indices. |
| `market_valuations` | Index PE, PB, and dividend yield over time. Up to 20 years. |
| `get_india_vix` | The India VIX fear gauge — latest level, daily change, recent history. |
| `get_index_performance` | Rank ~140 NSE indices by return over completed weeks or months. Filter to sectoral, broad, thematic, or strategy families — the right answer to "which sector led last month". |
| `get_index_history` | OHLC level series plus PE/PB/dividend yield for a single index. The index counterpart of `get_price_history`. |

### 🎲 Derivatives & Risk (5 tools)

| Tool | Description |
|------|-------------|
| `get_option_chain` | Per-strike index option chain with IV, full Greeks, bid/ask, open interest, max pain, PCR. NIFTY, BANKNIFTY, FINNIFTY, MIDCPNIFTY — a stamped end-of-day snapshot. |
| `get_option_iv_history` | Session-by-session ATM IV, IV rank, IV percentile, realised vol, PCR, max pain, 25-delta skew for ~556 underlyings, individual stocks included. |
| `get_options_analytics` | Latest per-expiry aggregates — ATM IV, IV rank/percentile, realised vol, PCR by OI and volume, max pain, skew, call/put OI. |
| `get_promoter_pledge` | Promoter share-pledge percentage by quarter plus pledge/release events — a standard governance red-flag check. |
| `get_credit_ratings` | Credit-rating actions by agency with rating, action, and outlook over time. |

### 🔬 Research & Scoring (4 tools)

| Tool | Description |
|------|-------------|
| `get_stock_deals` | Bulk, block, insider, and substantial-acquisition (SAST) disclosures per stock, with counterparty, side, quantity, value. |
| `get_tapetide_score` | The deterministic 0-100 Tapetide Score for one stock with its six pillar sub-scores, band, percentile, data confidence, and any governance caps or red flags. |
| `screen_tapetide_scores` | Rank and filter the scored universe by band, size bucket, sector, score window, and confidence, with cursor pagination. |
| `get_earnings_call_summary` | Structured digest of recent earnings-call transcripts and investor presentations — highlights, risks, guidance, headline metrics. |

### 📄 Filing Text (3 tools)

Parsed filings as text — read the annual report or transcript itself, not just a digest.

| Tool | Description |
|------|-------------|
| `list_company_documents` | Index of a company's parsed filings — concall transcripts, annual reports, investor presentations, IPO documents — with `doc_id`, period, page count, what is available for each, and links to the PDF and full Markdown. Call this first. |
| `get_document_summary` | Investor digest of one filing by `doc_id` (or the newest of a `doc_type`): summary, highlights, risks, management guidance, key metrics. Capped at 6k chars; `truncated: true` marks an abridged digest. |
| `read_document` | The Markdown text of a filing by `doc_id` and page range, with `<!-- page N -->` markers to cite from. At most 12 pages / 24k chars per call; the result names the pages returned and the `next_pages` to fetch. |

### ⏳ Point-in-Time & Backtest Safety (5 tools)

| Tool | Description |
|------|-------------|
| `get_adjustment_factors` | Split and bonus adjustment timeline for reconstructing raw prices — plus the rights and demerger events that carry no reliable factor at all. |
| `get_observation_status` | Per-calendar-day reason a price is present or missing: traded, weekend, holiday, pre-listing, delisted, or no print. A missing day is not a zero return. |
| `get_index_membership_asof` | Was a stock in an index on a given date? Answers `present`, `uncertain`, `absent`, or `out_of_coverage` — survivorship-bias-aware universe construction. |
| `resolve_identifier_asof` | Map a historical symbol or ISIN to the company that held it on a date, for old holdings files and recycled tickers. |
| `get_identifiers_asof` | The reverse lookup — which symbol and ISIN a company traded under at a point in time. |

### 💼 Portfolio (4 tools)

Requires a connected Tapetide account.

| Tool | Description |
|------|-------------|
| `get_user_portfolio` | Holdings with live prices, absolute and % P&L, invested value, weight, sector, market-cap class. |
| `add_portfolio_stocks` | Add holdings singly or in bulk, including rows parsed from a broker CSV or screenshot (Zerodha, Groww, Angel One, Dhan, Upstox, 5Paisa, ICICI Direct, Kotak, HDFC Sky, Motilal Oswal). Duplicates merge on a weighted-average price. |
| `update_portfolio_stock` | Update quantity and average price after a top-up or partial sell. |
| `remove_portfolio_stocks` | Remove holdings from the portfolio. |

### 👁️ Watchlist (3 tools)

Requires a connected Tapetide account.

| Tool | Description |
|------|-------------|
| `get_watchlist` | Every followed stock with sector and industry. |
| `add_to_watchlist` | Follow one or many stocks. Idempotent. |
| `remove_from_watchlist` | Unfollow one or many stocks. |

### 📖 Guide & Aliases (6 tools)

| Tool | Description |
|------|-------------|
| `read_me` | The full in-session guide — every tool by category, the SEBI disclaimer rule, portfolio-first behaviour, parallel-call patterns. Assistants should call it first. |
| `scan_movers` | Alias of `get_trending_stocks`. |
| `get_live_quote` | Alias of `get_stock_quote`. |
| `get_stock_news` | Alias of `get_stock_events` with `type: "news"`. |
| `get_corporate_actions` | Alias of `get_stock_events` with `type: "corporate_actions"`. |
| `run_preset_screen` | Redirect that points a preset-screen request at the screener tool that can actually answer it. |

<!-- tools:end -->

### Retired tool names

These names were removed. Calling one returns a message naming its replacement, so a client can
recover in the same turn — but new integrations should use the replacement directly.

| Retired | Replacement |
|---------|-------------|
| `market_deals` | `get_market_data` with `dataset: "deals"` |
| `market_fno_ban` | `get_market_data` with `dataset: "fno_ban"` |
| `market_deliveries` | `get_market_data` with `dataset: "deliveries"` |
| `market_ipo` | `get_market_data` with `dataset: "ipo"` |
| `market_mtf` | `get_market_data` with `dataset: "mtf"` |
| `market_slbm` | `get_market_data` with `dataset: "slbm"` |
| `market_signals` | `get_market_data` with `dataset: "signals"` |
| `get_quant_signal` | `get_tapetide_score` (a different measurement, not a rename) |
| `screen_by_quant_signal` | `screen_tapetide_scores` (a different measurement, not a rename) |

## Example Prompts

### Stock Research

```
"Give me a complete analysis of Reliance Industries — financials, debt trend,
 analyst target price, and what mutual funds are holding it"

"Compare HDFC Bank and ICICI Bank — quarterly profit growth, ROE, shareholding
 changes, and analyst consensus"

"Pull the last 4 quarters of TCS financials — revenue growth, margin trend,
 and cash flow. How does it compare to Infosys?"
```

### Stock Screening

```
"Find mid-cap stocks where FII holding increased last quarter, ROE > 15%,
 and RSI below 40 — accumulation c