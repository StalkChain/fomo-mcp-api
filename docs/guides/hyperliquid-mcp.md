# Hyperliquid MCP for wallet positions, funding rates, and trader PnL

Connect StalkChain Data to Claude, ChatGPT, Codex, Cursor, or another MCP client to research public Hyperliquid accounts and perpetual futures markets. Add `https://data.stalkchain.com/mcp` as an HTTP connector and sign in with StalkChain OAuth. [Client setup guides](../../README.md#install-and-research-guides)

## Pick the tool for your question

| Question | StalkChain tool | What to check |
| --- | --- | --- |
| What is this wallet long or short right now? | `stalkchain_perps_wallet` | Use a full public `0x` address. Check position size, entry, mark, leverage, and unrealized PnL. The wallet view also has recent fills and closed positions. |
| Who led the Hyperliquid leaderboard this week? | `stalkchain_perps_leaderboard` | Set the ranking window and choose PnL or ROI. Report the minimum account value used and distinguish the account's size from its return. |
| How are profitable Hyperliquid traders positioned on HYPE? | `stalkchain_perps_smart_money` | Set the market, ranking window, and cohort size. Report how many selected traders hold the market, their long and short counts, and their long and short notional. |
| How does SOL funding compare across venues? | `stalkchain_perps_funding` | Compare Hyperliquid, Binance, and Bybit on the same rate basis. Ask for one coin and a day count to include its Hyperliquid funding history. |

## Example research prompt

> Look up this public Hyperliquid wallet: [paste address]. Show its open perpetual futures positions with side, mark, and unrealized PnL. Show recent closed trades separately, with realized PnL and fees when available. Include the observation time if the source returns one. Leave missing values unknown.

A leaderboard and its sample of top traders describe different populations. When you use the smart-money tool, report the selected cohort and the number of matching traders so readers can interpret the exposure. A reported liquidation price is a position estimate and can change with account equity and margin.

Check the [live tool reference](https://stalkchain.com/docs/tools) for credit costs and the [OpenAPI specification](https://data.stalkchain.com/api/v1/openapi.json) for current tool inputs. Account access and tool availability depend on the StalkChain endpoint and client.
