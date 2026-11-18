# Kiro crypto MCP setup for StalkChain Data

Connect Kiro IDE or Kiro CLI to the hosted StalkChain Data MCP for crypto research. The connector can look up public wallet positions, trader activity, and token holders. It uses StalkChain OAuth and account credits for metered calls.

[![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=stalkchain&config=%7B%22url%22%3A%22https%3A%2F%2Fdata.stalkchain.com%2Fmcp%2Fdirectory%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D)

## Connect in Kiro IDE

1. Select **Add to Kiro** and allow the browser to open Kiro.
2. In Kiro, review the `stalkchain` entry and confirm that its Streamable HTTP URL is `https://data.stalkchain.com/mcp/directory`.
3. Connect to the server and sign in to StalkChain in your browser. Approve access and check the MCP servers panel for the connected server.

If the button does not open Kiro, add the entry manually using the user-level MCP configuration at `~/.kiro/settings/mcp.json` or the workspace configuration at `.kiro/settings/mcp.json`. Merge it into your existing `mcpServers` object.

```json
{
  "mcpServers": {
    "stalkchain": {
      "url": "https://data.stalkchain.com/mcp/directory",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

## Connect in Kiro CLI

Use the same manual configuration and open a Kiro CLI chat. Run `/mcp`, select the StalkChain server, and complete browser sign-in. Managed Kiro accounts may require an administrator to allow the connector before it appears.

## Try a wallet lookup

> Use StalkChain to look up this public Solana wallet's current positions and recent PnL. Include the wallet address, data timestamps, and which PnL figures have incomplete cost basis.

Replace “this public Solana wallet” with the wallet's full address. Review the [StalkChain tool reference](https://stalkchain.com/docs/tools) and your account balance before approving a metered call.

[StalkChain privacy policy](https://data.stalkchain.com/privacy) · [StalkChain support](mailto:support@stalkchain.com) · [Kiro MCP configuration](https://kiro.dev/docs/mcp/configuration/)
