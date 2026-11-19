# Hyperliquid MCP for wallet positions, funding rates, and trader PnL

Connect StalkChain Data to Claude, ChatGPT, Codex, Cursor, or another MCP client to research public Hyperliquid accounts and perpetual futures markets. Add the StalkChain HTTP connector and sign in with OAuth. The Claude guide uses the research endpoint at `https://data.stalkchain.com/mcp/directory`. [Claude and Claude Code setup](claude-crypto-mcp.md) · [Other MCP clients](../../README.md#install-and-research-guides)

## Pick the tool for your question

| Question | StalkChain tool | What to check |
| --- | --- | --- |
| What is this wallet long or short right now? | `stalkchain_perps_wallet` | Use a full public `0x` address. Check position size, entry, mark, leverage, and unrealized PnL. The wallet view also has recent fills and closed positions. |
| Who led the Hyperliquid leaderboard this week? | `stalkchain_perps_leaderboard` | Set the ranking window and choose PnL or ROI. Report the minimum account value used and distinguish the account's size from its return. |
| How are profitable Hyperliquid traders positioned on HYPE? | `stalkchain_perps_smart_money` | Set the market, ranking window, and cohort size. Report how many selected traders hold the market, their long and short counts, and their long and short notional. |
| How does SOL funding compare across venues? | `stalkchain_perps_funding` | Compare Hyperliquid, Binance, and Bybit on the same rate basis. Ask for one coin and a day count to include its Hyperliquid funding history. |

## Check one Hyperliquid wallet

Use `stalkchain_perps_wallet` with a public `0x` address. Set `fills` to zero if you only want current positions and recent grouped trades. Set both `fills` and `positions` to zero if you only need the current positions and headline account figures.

```json
{
  "wallet": "REPLACE_WITH_HYPERLIQUID_WALLET_ADDRESS",
  "fills": 0,
  "positions": 5
}
```

Show open positions by market, side, size, entry, mark, and unrealized PnL. Put trades reconstructed from fills in a separate table with realized PnL and fees. If a position opened before the available fill history, flag it as incomplete. If the response includes day, week, month, or all-time PnL, preserve the period label from the source.

> Look up this public Hyperliquid wallet: [paste address]. Show open perpetual futures positions and unrealized PnL. Put up to five recent grouped trades in a separate table with realized PnL and fees. Include the observation time if the source provides one. Mark missing or incomplete figures.

## Compare funding for one market

For current SOL funding across venues and seven days of Hyperliquid funding history, use `stalkchain_perps_funding`.

```json
{
  "coins": ["SOL"],
  "days": 7
}
```

Put venue rates on the same hourly basis. The history covers Hyperliquid when the request includes exactly one coin. Report the timestamps and leave any missing venue rates unknown.

A leaderboard and a sample of top traders describe different populations. If using the smart-money tool, state the ranking window, selected cohort size, and number of traders holding the market. Treat the liquidation value as an estimate tied to the position's margin and account equity.

Check current costs and account access before running multiple lookups. [Tool reference](https://stalkchain.com/docs/tools) · [Live input schemas](https://data.stalkchain.com/api/v1/openapi.json)
