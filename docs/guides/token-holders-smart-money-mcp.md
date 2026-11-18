# Token holders and smart-money flow with an MCP server

Use StalkChain Data to check which tracked wallets hold a token and whether those wallets recently entered or exited. Start with the token's full mint or contract address and its chain. Symbols alone can refer to several assets. [Connect the hosted MCP](../../README.md#quick-start-mcp)

## Separate holdings from flow

| Look up | StalkChain tool | What the evidence tells you |
| --- | --- | --- |
| Token holders and their positions | `stalkchain_fomo_token_holders` | Which holders the tool returned for the token and observation time |
| Exposure among tracked traders | `stalkchain_fomo_kol_holders` | Which tracked wallets still hold it and how concentrated their positions are |
| Several tracked traders entering around the same time | `stalkchain_fomo_multi_trader_entries` | Which assets saw clustered entries during the window |
| Selling by tracked holders | `stalkchain_fomo_kol_sell_pressure` | Whether tracked positions fell or holders sold in the window |

A tracked-wallet list covers a subset of the market. Count distinct wallets as wallets, and flag possible common ownership before counting them as independent traders. Compare holdings with sells over the same period. Check liquidity separately before treating reported activity as actionable.

## Example research prompt

> Research this exact token: [paste mint or contract], on [chain]. Show tracked holders, position concentration, and the past 24 hours of tracked-wallet inflows and sells. Give the observation times and wallet or transaction links where available. Flag uncertain attribution, missing coverage, and thin liquidity.

Check the [tool reference](https://stalkchain.com/docs/tools) for available chains, inputs, and credit costs. For an individual holder, continue with the [Solana wallet tracker workflow](solana-wallet-tracker-mcp.md).
