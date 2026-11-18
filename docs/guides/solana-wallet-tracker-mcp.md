# Solana wallet tracker MCP for holdings and PnL

Use StalkChain Data to research a public Solana address. Start with a full wallet address. If you only have a trader handle, verify the wallet attribution first. [Connect the hosted MCP](../../README.md#quick-start-mcp)

## Look up the wallet

| Question | StalkChain tool | What to verify |
| --- | --- | --- |
| Which wallet is associated with this trader? | `stalkchain_fomo_trader_wallets` | Which addresses are attributed, and whether the evidence matches the trader and chain |
| What does this wallet hold now? | `stalkchain_wallet_portfolio` | Observation time, priced holdings, and assets with missing prices |
| How did its Solana trades perform? | `stalkchain_wallet_pnl` | Exact period, whether the result separates realized and open positions, and gaps in cost basis |

Keep attribution and performance as separate steps. A public address can be checked on-chain. A handle-to-wallet attribution can change or be incomplete. Transfers and incomplete entry prices can also distort PnL.

## Example research prompt

> Check this Solana wallet: [paste public wallet address]. Start with current holdings. Then report the past 30 days of trading PnL, stating the time window and which figures are realized or still open. Mark missing cost basis, show transaction references where available, and leave unsupported values unknown.

Use an exact chain and time window when comparing wallets. Check the [tool reference](https://stalkchain.com/docs/tools) for current inputs and credit costs. When the question starts with a token mint, use the [token holder and smart-money flow workflow](token-holders-smart-money-mcp.md).
