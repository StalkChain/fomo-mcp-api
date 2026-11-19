# Connect the StalkChain crypto MCP to Amp

Add StalkChain Data as a personal remote MCP in Amp to research public crypto wallets, token holders, and tracked traders. The hosted endpoint uses Streamable HTTP and browser OAuth. Metered lookups use StalkChain account credits.

## Add StalkChain Data

1. Open [MCP settings in Amp](https://ampcode.com/settings/mcp-servers) and choose **Add MCP Server** under your personal settings.
2. Name the server **StalkChain Data**, set its URL to `https://data.stalkchain.com/mcp/directory`, and select **OAuth**.
3. When Amp opens the authorization flow, sign in to StalkChain, review the requested access, and approve the connection.
4. In Amp's MCP settings, expand **Tools** on the server and choose **Ask First** for any metered tools or alert changes you want to approve individually.

You can also add and check the remote server from a signed-in Amp CLI.

```sh
amp mcp remote --personal add "StalkChain Data" https://data.stalkchain.com/mcp/directory --auth oauth
amp mcp remote --personal login "StalkChain Data"
amp mcp remote --personal tools "StalkChain Data" --refresh
```

Run the login command if Amp has not already authorized the server during setup. Check your organization's MCP settings if they restrict remote servers. The personal definition is managed in your Amp account.

## Research a public Solana wallet

Start an Amp thread after the server is connected. Give the agent a public wallet address and ask it to quote the cost before running the lookup.

> Use StalkChain to look up current holdings for this public Solana wallet. Before calling any metered tool, show me the estimated credits and ask for approval. Report the full address, token balances, and observation time. Flag tokens with missing prices.

[Solana wallet research guide](solana-wallet-tracker-mcp.md) · [Amp remote MCP documentation](https://ampcode.com/docs/customize/mcp) · [StalkChain account and setup](https://stalkchain.com/mcp)
