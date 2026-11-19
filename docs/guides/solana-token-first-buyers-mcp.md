# Find the first buyers of a Solana token with MCP

Use StalkChain Data to see which public wallets bought a Solana token first, whether those wallets have sold, and how much supply launch bundles still hold. Sign in through StalkChain OAuth on the [hosted MCP](../../README.md#quick-start-mcp). Start with the exact Solana mint address so the lookup resolves the intended token.

## Check early wallets and current concentration

| Question | Tool | Inputs | Credits |
| --- | --- | --- | ---: |
| Which wallets bought first, and did they sell? | `stalkchain_token_early_buyers` | Required `token` mint. Optional `limit`, default 20. | 500 |
| Who holds the supply now? | `stalkchain_token_onchain` | Required `token` mint. | 250 |

Start with the early-buyer lookup. Read purchase times, reported exit status, and the supply attributed to launch bundles. Add the on-chain snapshot when you need current top-10 concentration, developer holdings, or liquidity. The two calls together use 750 credits at the documented rates. [Solana tool reference](https://stalkchain.com/docs/tools/solana-on-chain)

Wallet addresses identify on-chain accounts. Several wallets buying close together or receiving funding from a common source warrant a closer look. Verify supporting transactions before concluding that they have the same owner. Keep early-buyer results separate from the current holder snapshot and label each observation with its time.

## Example prompt

> For Solana mint [paste mint address], use the early-buyer tool with a limit of 20. Show the first buys in order, the reported exit status and any remaining bundle concentration. Include transaction references where available and mark unknowns. Ask before adding a current holder snapshot, and show the additional credit cost.

For a follow-up, check [tracked holders and smart-money flow](token-holders-smart-money-mcp.md) or inspect [mint authorities and liquidity](token-safety-mcp.md).
