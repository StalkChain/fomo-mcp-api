# Connect the StalkChain crypto MCP to Mistral Vibe

Use StalkChain Data in Mistral Vibe to look up public crypto wallet holdings, token holders and on-chain activity. The remote server uses browser sign-in. Metered lookups use StalkChain account credits.

## Add StalkChain to Vibe Work

1. As an administrator, open **Connectors** in Vibe Work and select **Add Connector**.
2. Open **Custom MCP Connector**. Name it `stalkchain` and enter `https://data.stalkchain.com/mcp/directory` as the server URL.
3. Select **Connect**, sign in to StalkChain in the browser and approve access.
4. Open **My Connectors** and select StalkChain to inspect its available functions. Keep alert changes on manual approval.

The account owner is the administrator by default on Free, Pro and Student plans. [Mistral Vibe Work connector documentation](https://docs.mistral.ai/vibe/work/web/connectors/mcp-connectors)

## Add StalkChain to Vibe Code CLI

```sh
vibe mcp add stalkchain --url https://data.stalkchain.com/mcp/directory
```

Complete sign-in in the browser. In a Vibe Code session, run `/mcp status` to check the connection or `/mcp login stalkchain` to sign in again. To see the available tools, run `/mcp stalkchain`. [Mistral Vibe Code CLI documentation](https://docs.mistral.ai/vibe/code/cli/mcp-servers)

## Try a public Solana wallet lookup

> Use StalkChain to look up the current holdings of this public Solana wallet. Include token mint addresses, balances and the observation time. Flag tokens with missing prices.

Replace “this public Solana wallet” with a full wallet address. Check your balance and the tool’s price before approving a metered lookup. [Wallet research workflow](solana-wallet-tracker-mcp.md) · [StalkChain Data dashboard](https://data.stalkchain.com/)
