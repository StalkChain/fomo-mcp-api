# Connect the StalkChain crypto MCP to Qoder CLI

Use StalkChain Data to research public Solana wallets, token holders, and tracked trader activity in Qoder CLI. The hosted server uses Streamable HTTP and StalkChain OAuth. Data lookups use StalkChain credits.

## Add the server to your project

Install [Qoder CLI](https://docs.qoder.com/cli/installation) and open a trusted project on the same computer as your browser. Run the following from the project directory.

```sh
qoder mcp add -t http -s local stalkchain-data https://data.stalkchain.com/mcp/directory
qoder mcp list
```

The `local` scope saves the connection in `.qoder/settings.local.json` for the current project on this machine. For a manual setup, merge the entry into the file's `mcpServers` object.

```json
{
  "mcpServers": {
    "stalkchain-data": {
      "type": "http",
      "url": "https://data.stalkchain.com/mcp/directory"
    }
  }
}
```

## Connect your account

Before authorization, the CLI lists the endpoint as **Needs authentication**. Start an interactive Qoder session, open `/mcp`, and select the StalkChain server. Follow the browser sign-in prompt and approve the requested access. Return to Qoder and check the server status in `/mcp`. Use `/mcp reload` if you added it while the session was already running. [Qoder MCP commands](https://docs.qoder.com/cli/mcp-reference)

## Try a public Solana wallet lookup

> Use StalkChain to check the current holdings of this public Solana wallet: <wallet address>. Give the token mint, balance, and time of observation. Ask before running a metered lookup and flag any missing prices.

Replace the placeholder with a full public wallet address. The lookup uses `stalkchain_wallet_portfolio`. Review the lookup cost before approving the call. [Wallet research workflow](solana-wallet-tracker-mcp.md) · [StalkChain setup](https://stalkchain.com/mcp)

Qoder CLI 1.1.92 saved the configuration above and detected that the server requires authentication. Signed-in lookup behavior has yet to be verified.
