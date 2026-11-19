# Connect the StalkChain crypto MCP to Windsurf Cascade

Add StalkChain Data to the Windsurf Cascade plugin for JetBrains to research public crypto wallets, token holders, and tracked trader activity. The hosted directory endpoint uses Streamable HTTP and browser OAuth. Metered lookups use StalkChain account credits.

## Add StalkChain to Cascade

1. Open the **MCP** menu inside Cascade and select **Open MCP config file**. Use the file Cascade opens for your installation.
2. Add the `stalkchain` entry under `mcpServers`, keeping any entries already present.

```json
{
  "mcpServers": {
    "stalkchain": {
      "serverUrl": "https://data.stalkchain.com/mcp/directory"
    }
  }
}
```

3. Save the file and refresh the MCP list in Cascade. When Cascade prompts for authorization, complete sign-in on StalkChain and approve the connection.
4. If your organization controls MCP access, have its administrator enable MCP and allow this exact server configuration. Review the tools you enable and confirm before changing any price alerts.

[Windsurf Cascade MCP configuration](https://docs.devin.ai/windsurf/plugins/cascade/mcp) · [StalkChain account and setup](https://stalkchain.com/mcp)

## Research a public wallet

> Use StalkChain to summarize the current holdings of this public Solana wallet. Include the full address, token mint addresses, balances and the observation time. Flag tokens with missing prices.

Replace “this public Solana wallet” with a full address. Check the tool’s price and your credit balance before approving the lookup. [Solana wallet research guide](solana-wallet-tracker-mcp.md)

For Devin Local or the Devin CLI, use the [Devin setup guide](devin-crypto-mcp.md).
