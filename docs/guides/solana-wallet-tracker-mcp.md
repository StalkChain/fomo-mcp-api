# Solana wallet tracker MCP for holdings and PnL

Use StalkChain Data to research a public Solana address. Start with a full wallet address. If you only have a trader handle, verify the wallet attribution first. [Connect from Claude or Claude Code](claude-crypto-mcp.md) · [Other MCP clients](../../README.md#install-and-research-guides)

## Look up the wallet

| Question | StalkChain tool | What to verify |
| --- | --- | --- |
| Which wallet is associated with this trader? | `stalkchain_fomo_trader_wallets` | Which addresses are attributed, and whether the evidence matches the trader and chain |
| What does this wallet hold now? | `stalkchain_wallet_portfolio` | Observation time, priced holdings, and assets with missing prices |
| How did its Solana trades perform? | `stalkchain_wallet_pnl` | Reported coverage, realized and unrealized PnL, and gaps in cost basis |

Keep attribution and performance as separate steps. A public address can be checked on-chain. A handle-to-wallet attribution can change or be incomplete. Transfers and incomplete entry prices can also distort PnL.

## Run a Solana-only holdings lookup

Connect the hosted MCP, sign in, and give your assistant the full public wallet address. To keep the lookup on Solana, pass `chains: ["solana"]` to `stalkchain_wallet_portfolio`. The default searches multiple chains.

```json
{
  "wallet": "REPLACE_WITH_SOLANA_WALLET_ADDRESS",
  "chains": ["solana"]
}
```

Ask for the ten largest priced holdings, their amounts and USD values, and the observation time if available. If the response lists Solana in `failedChains`, report that holdings could not be verified. If you add a minimum-value filter, label any displayed total as the value of the filtered holdings.

## Check realized and unrealized PnL

If you already fetched holdings, ask for `stalkchain_wallet_pnl` with `includeHoldings: false` to avoid requesting them again.

```json
{
  "wallet": "REPLACE_WITH_SOLANA_WALLET_ADDRESS",
  "includeHoldings": false
}
```

Read `realizedUsd` and `unrealizedUsd` separately and retain the returned win and loss counts. This lookup has no start-date or end-date input. Use the provider’s reported coverage if available. For a date-bounded investigation, retrieve and verify timestamped fills or on-chain transactions with enough history to establish cost basis. Leave period PnL unknown if the history is incomplete.

> Use StalkChain Data to look up this public Solana address: [paste address]. Show current holdings from Solana only. Then show realized and unrealized PnL from the PnL lookup without fetching holdings again. Include the observation time and reported coverage when available. Mark missing values as unknown.

The two lookups use account credits. Check current costs before running both. For a workflow that starts with a token mint, see the token holder guide. [Tool reference](https://stalkchain.com/docs/tools) · [Live input schemas](https://data.stalkchain.com/api/v1/openapi.json) · [Token holders and smart-money flow](token-holders-smart-money-mcp.md)
