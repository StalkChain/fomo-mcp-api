# Devin Local crypto MCP setup for StalkChain Data

Connect Devin Desktop or Devin CLI to the hosted StalkChain Data MCP. Use it to inspect public wallet holdings, compare trader PnL, or research token holders. StalkChain uses OAuth sign-in and account credits for metered lookups.

## Connect from Devin CLI

From your project directory, add the remote server and sign in:

```sh
devin mcp add stalkchain https://data.stalkchain.com/mcp/directory
devin mcp login stalkchain
devin mcp list
```

Devin stores the entry in the project's local MCP configuration by default. Follow the sign-in prompt in your browser, approve access, then check that StalkChain appears in the list.

## Connect from Devin Desktop

Add the following entry to `mcpServers` in `.devin/mcp_config.local.json` for this project or `~/.config/devin/mcp_config.json` for your user account. If the file already has other servers, merge this entry into it.

```json
{
  "mcpServers": {
    "stalkchain": {
      "url": "https://data.stalkchain.com/mcp/directory",
      "transport": "http"
    }
  }
}
```

Open **Customize → MCPs** in the Agents window. Refresh **This computer** if the entry is missing, then select **Authenticate** if Devin shows **Needs authentication**. Your team may need to allow the connector before you can use it.

## Try a wallet PnL lookup

> Use StalkChain to look up the holdings and recent PnL for this public Solana wallet. Include the address, observation time and any incomplete cost-basis data.

Replace “this public Solana wallet” with the full address. Check the [StalkChain tool reference](https://stalkchain.com/docs/tools) and your balance before approving metered calls.

[Devin CLI MCP setup](https://docs.devin.ai/cli/extensibility/mcp/configuration.md) · [Devin Desktop MCP setup](https://docs.devin.ai/desktop/devin-local/customizations.md#mcp-servers)
