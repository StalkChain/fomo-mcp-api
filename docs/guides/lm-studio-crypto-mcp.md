# Connect the StalkChain crypto MCP to LM Studio

Use StalkChain Data in LM Studio to check public Solana wallet holdings, token holders, and tracked-trader flows. Run a model that supports tool calls and use a current LM Studio release with MCP OAuth support. StalkChain runs the data connection remotely. Some lookups use account credits.

## Add StalkChain to LM Studio

With LM Studio installed, paste this link into your browser’s address bar and allow it to open LM Studio. Review and accept the configuration in the app.

```text
lmstudio://add_mcp?name=stalkchain-data&config=eyJ1cmwiOiJodHRwczovL2RhdGEuc3RhbGtjaGFpbi5jb20vbWNwL2RpcmVjdG9yeSJ9
```

You can also open the **Program** tab in LM Studio’s right sidebar and choose **Install → Edit mcp.json**. Merge the `stalkchain-data` entry into the existing `mcpServers` map and save.

```json
{
  "mcpServers": {
    "stalkchain-data": {
      "url": "https://data.stalkchain.com/mcp/directory"
    }
  }
}
```

When LM Studio opens the StalkChain authorization page, sign in and approve the connection. Return to LM Studio and check that the server is enabled. LM Studio uses a browser callback on this computer. If sign-in stalls, keep the desktop app open and complete the browser flow on the same computer. [LM Studio MCP setup](https://lmstudio.ai/docs/app/mcp) · [LM Studio OAuth](https://lmstudio.ai/docs/integrations/mcp-remote)

## Check a public Solana wallet

> Use StalkChain to show the current holdings of this public Solana wallet: [paste address]. Separate priced and unpriced assets, and include the observation time when available.

Verify the chain and address returned with the holdings. The hosted connector queries public data and cannot place trades or sign transactions. [Solana wallet research workflow](solana-wallet-tracker-mcp.md) · [StalkChain tool reference](https://stalkchain.com/docs/tools)
