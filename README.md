# FOMO MCP & API: social-trading data for AI agents

Connect Claude, ChatGPT, Cursor, Claude Code, or another MCP-compatible agent to tracked-trader wallets, token holders, buy/sell flow, trade theses, and on-chain research via **[StalkChain Data](https://data.stalkchain.com)**. Build research agents, trader dashboards, alerts, and token due-diligence workflows against the **hosted** MCP or REST API.

> **This is a developer guide, not an installable MCP server, SDK, mirror, or independent FOMO API.** StalkChain Data is built by StalkChain; this repository is not operated by or officially endorsed by the FOMO app. The hosted service owns authentication, tool availability, billing, and responses.

**[Connect MCP](https://data.stalkchain.com/mcp)** · **[Developer docs](https://data.stalkchain.com/docs)** · **[Tool reference](https://data.stalkchain.com/docs/tools/index)** · **[Live OpenAPI](https://data.stalkchain.com/api/v1/openapi.json)**

## Why connect FOMO data to an AI agent?

A general-purpose AI can explain token concepts, but it cannot infer who holds a token right now, whether a tracked trader sold, or what was written alongside a specific trade without a live source. StalkChain Data exposes social-trading and on-chain research tools through MCP for interactive agents and REST for software you build yourself. You choose the questions and verify significant conclusions against original transactions and current executable liquidity.

| Your question | Research path |
| --- | --- |
| Which tracked traders hold this token? | Resolve its contract, examine attributed holders, positions, and recent sells. |
| Did several traders enter the same token? | Inspect coordinated activity, time windows, independent wallet evidence, and concentration. |
| Why did someone buy? | Read timestamped trade theses and comments; distinguish an opinion from a verified event. |
| Is this trader worth following? | Compare linked wallets, fills, PnL windows, open inventory, and incomplete-basis caveats. |
| Could I exit a position? | Check liquidity and sell-route estimates, then obtain a fresh executable quote before any trade. |

## Quick start: MCP

1. [Create a StalkChain Data account](https://data.stalkchain.com). Connecting is free and does not require a card. Check your dashboard for available balance and the current terms before paid calls.
2. In your AI client's **custom connector / MCP** settings, enter `https://data.stalkchain.com/mcp`. Sign in via the service's OAuth flow and approve access.
3. Ask your agent:

   > Which token contracts had several tracked traders buy recently? Give the precise time window, attributed wallets, timestamps, and source records. Check whether the traders still hold. Do not present this as a buy signal.

For Claude Code, the [current setup reference](https://data.stalkchain.com/llms.txt) gives:

```sh
claude mcp add --transport http stalkchain https://data.stalkchain.com/mcp
```

Client interfaces change: use the [getting-started guide](https://data.stalkchain.com/docs/guides/getting-started) if your UI differs. OAuth clients do not need a pasted REST API key. Never approve unnecessary permissions or commit a credential.

## Quick start: REST API

The [OpenAPI specification](https://data.stalkchain.com/api/v1/openapi.json) describes each tool's input schema and HTTP method. The REST base is `https://data.stalkchain.com/api/v1`; create a key in your dashboard and pass it as `Authorization: Bearer sc_...` to authenticated endpoints. `GET /api/v1/tools` is **authenticated**; an anonymous 401 is expected, not evidence that the API is down. Use the public OpenAPI or [tool reference](https://data.stalkchain.com/docs/tools/index) to inspect available tools before signing in.

Read the [public OpenAPI specification](https://data.stalkchain.com/api/v1/openapi.json) without a key. At verification, even the documented free health REST route returned **401 without authentication**; “free” means zero credits after authentication, not necessarily keyless access. For a non-billable authenticated health check, confirm current entitlement, then use your dashboard-issued key in your own backend—not in browser JavaScript or this repository.

Before a paid tool call, check your account balance, that tool's **current** cost, the number of upstream calls a composite analysis may trigger, and whether your automation repeats. The agent's subscription and the hosted data-service credits are separate charges. See [REST/MCP developer guide](docs/DEVELOPER-GUIDE.md).

## What can you build?

- **Token research desk:** token discovery → attributed holders and flow → developer/early-buyer checks → theses and liquidity caveats.
- **Trader due diligence:** handle resolution → wallet and position history → fills, PnL windows, follower context → evidence-backed watchlist.
- **Convergence scanner:** several tracked wallets entering one token in a defined window, with per-event timestamps and liquidity checks. A scheduled scanner is **your agent or application automation**, not an automatic trading feature of this repository.
- **Read-only dashboard or alert bot:** consume the same documented tools via REST, record observation time and costs, dedupe alerts, and enforce a budget.
- **Launchpad and multi-chain research:** consult the live StonkFun, Solana, Robinhood Chain, cross-chain, DeFi, and price-confidence tools where available. Coverage differs by chain and tool; verify exact inputs first.

[Explore the categorized tools and prompts →](docs/TOOLS-AND-WORKFLOWS.md)

## Costs, safety, and trust boundaries

StalkChain Data uses metered credits. Account setup is free; a paid tool may return an insufficient-balance error. Purchased-pack terms and individual tool prices are maintained on the [live site](https://data.stalkchain.com/#plans) and [tool reference](https://data.stalkchain.com/docs/tools/index). **Do not assume a prompt is one billable call.** Promotional credits, if offered, have separate eligibility and expiry terms; this repository makes no promise that a particular grant is currently active.

This repository contains **documentation only**. It does not collect credentials, proxy requests, execute trades, or offer investment advice. Attributed wallets may be incomplete or misidentified; displayed PnL may have missing cost basis or partial unrealized positions. Token holders, prices, and social activity change. Verify high-stakes claims with current chain transactions, contract identity, and executable routes rather than an attractive historical screenshot.

## Documentation

- [All capability groups and research prompts](docs/TOOLS-AND-WORKFLOWS.md)
- [Developer guide: MCP, REST, costs, error handling](docs/DEVELOPER-GUIDE.md)
- [Troubleshooting](docs/TROUBLESHOOTING.md)
- [Sources of truth and documentation drift](docs/SOURCE-OF-TRUTH.md)

**Start building at [data.stalkchain.com](https://data.stalkchain.com).**
