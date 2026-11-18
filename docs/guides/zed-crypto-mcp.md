# Zed crypto MCP setup for StalkChain Data

Connect the Zed Agent to the hosted StalkChain Data MCP for on-chain research. Look up public trader wallets, compare wallet PnL, or examine holders and recent token activity. Connect with StalkChain OAuth. Metered tool calls use your StalkChain account credits.

## Add the remote MCP server

1. In Zed, open **Settings → AI → MCP Servers**.
2. Select **Add Server → Add Remote Server**. Name the server `stalkchain` and use `https://data.stalkchain.com/mcp/directory`.
3. Follow Zed's OAuth prompt to sign in to StalkChain and approve access. Return to **MCP Servers** and check that the indicator beside `stalkchain` is green.

To configure manually, open the Command Palette and run `zed: open settings file`. Add the `stalkchain` entry to the existing `context_servers` object.

```json
{
  "context_servers": {
    "stalkchain": {
      "url": "https://data.stalkchain.com/mcp/directory"
    }
  }
}
```

## Try a token research prompt

> Use the StalkChain MCP to inspect the holders and recent buys or sells for this Solana token contract. Show the observation time, attributed wallets, and any missing coverage.

Replace “this Solana token contract” with the token's complete contract address. Verify time-sensitive findings against on-chain activity before relying on them. Check the [tool reference](https://stalkchain.com/docs/tools) and your account balance before metered calls.

[Official Zed MCP setup](https://zed.dev/docs/ai/mcp) · [StalkChain Data developer docs](https://data.stalkchain.com/docs)
