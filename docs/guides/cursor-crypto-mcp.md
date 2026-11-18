# Connect the StalkChain crypto MCP server to Cursor

Connect StalkChain Data to Cursor to check which tracked traders hold a token and how their positions have changed. You'll need Cursor and a free StalkChain Data account. Some lookups use account credits. [StalkChain plans](https://data.stalkchain.com/#plans)

## Install in Cursor

**[Add StalkChain to Cursor](https://cursor.com/install-mcp?name=stalkchain&config=eyJ1cmwiOiJodHRwczovL2RhdGEuc3RhbGtjaGFpbi5jb20vbWNwL2RpcmVjdG9yeSJ9)**

Allow the browser to open Cursor, then review and install the server. Open the `stalkchain` MCP connection in Cursor and sign in to StalkChain when prompted. The connection uses OAuth. [Cursor MCP documentation](https://cursor.com/docs/mcp)

### Add it manually

If the install link cannot open Cursor, add the `stalkchain` entry under `mcpServers` in `~/.cursor/mcp.json` for your user account or `.cursor/mcp.json` for the current workspace. Keep any existing server entries.

```json
{
  "mcpServers": {
    "stalkchain": {
      "url": "https://data.stalkchain.com/mcp/directory"
    }
  }
}
```

## Look up tracked token holders

In Cursor chat, use a Solana mint address to identify the exact token.

> Use StalkChain to find the tracked traders holding this Solana token. Show when the holdings were observed and any recent sells with timestamps. Include wallet addresses when available and flag missing data.

If Cursor shows the server but offers no StalkChain tools, check whether the connection is enabled and whether sign-in finished. [Connection troubleshooting](../TROUBLESHOOTING.md) · [Token holders and smart-money workflow](token-holders-smart-money-mcp.md)
