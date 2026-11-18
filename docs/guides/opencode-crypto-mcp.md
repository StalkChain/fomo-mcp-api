# Connect the StalkChain crypto MCP to OpenCode

Use StalkChain Data in OpenCode to research Solana token holders, public wallet activity and tracked-trader flows. OpenCode connects to the hosted server over Streamable HTTP and opens StalkChain sign-in in your browser. Some queries use StalkChain account credits.

## Add StalkChain to OpenCode v2

From the project where you want to use StalkChain, run:

```sh
opencode mcp add stalkchain --url https://data.stalkchain.com/mcp/directory
opencode mcp auth stalkchain
opencode mcp list
```

Sign in to StalkChain in the browser and approve access. You can also enter `/mcps` in OpenCode and choose `stalkchain` to start sign-in. [OpenCode v2 MCP documentation](https://opencode.ai/docs/mcp-servers/)

## Add StalkChain to OpenCode v1

Run `opencode --version` to check your version. In v1, entries sit directly under `mcp`. Add the `stalkchain` entry to your project's existing `opencode.json` or create the file if needed:

```json
{
  "mcp": {
    "stalkchain": {
      "type": "remote",
      "url": "https://data.stalkchain.com/mcp/directory",
      "enabled": true
    }
  }
}
```

From that project, run `opencode mcp auth stalkchain` and complete StalkChain sign-in in the browser. Run `opencode mcp list` to check the connection. [OpenCode v1 MCP documentation](https://opencode.ai/v1/docs/mcp-servers/)

## Check tracked holders of a Solana token

> Use StalkChain to look up tracked traders who currently hold this Solana token. Include their attributed wallet addresses, the observation time, and any limits on holder coverage.

Replace “this Solana token” with the token's mint address. Tracked wallets are a subset of all holders. Check the tool price and your credit balance before a metered query. [Token-holder workflow](token-holders-smart-money-mcp.md) · [StalkChain account](https://data.stalkchain.com/)
