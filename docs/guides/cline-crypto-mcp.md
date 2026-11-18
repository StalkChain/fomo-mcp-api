# Connect the StalkChain crypto MCP to Cline

Use StalkChain Data in Cline to research Solana token holders, public wallet activity and tracked-trader flows. The hosted connector signs you in through your browser. Some queries use StalkChain account credits.

## Add StalkChain to the Cline extension

1. Open **MCP Servers** in the Cline panel, then select **Remote Servers**.
2. Name the server `stalkchain-data` and enter `https://data.stalkchain.com/mcp/directory`.
3. Select **Streamable HTTP**, then click **Add Server**.
4. Follow the authorization prompt to sign in to StalkChain. Check that the server’s tools appear in the MCP Servers panel.

[Official Cline MCP documentation](https://docs.cline.bot/mcp/mcp-overview)

## Add StalkChain to Cline CLI

```sh
cline mcp add stalkchain-data https://data.stalkchain.com/mcp/directory --transport http --yes
cline config mcp
```

Run `cline mcp`, choose **Authorize OAuth**, and select `stalkchain-data`. Sign in to StalkChain in your browser and return to Cline.

If the server appears in the configuration and Cline still asks for authorization, use **Authorize OAuth** again. Leave automatic approval off for metered lookups and email alert changes.

## Look up tracked Solana token holders

> Use StalkChain to look up tracked traders who currently hold this Solana token. Include their attributed wallet addresses, the observation time, and any limits on holder coverage.

Replace “this Solana token” with the token's mint address. Check your account balance and the tool’s price before approving a metered lookup. [Token-holder workflow](token-holders-smart-money-mcp.md) · [StalkChain account](https://data.stalkchain.com/)
