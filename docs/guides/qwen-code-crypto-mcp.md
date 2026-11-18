# Connect the StalkChain crypto MCP to Qwen Code

Use StalkChain Data in Qwen Code to research public Solana wallets, token holders, and trader activity. The hosted MCP uses Streamable HTTP and browser sign-in. Metered lookups use your StalkChain account credits.

## Install from GitHub

With Qwen Code and your browser on the same computer, run:

```sh
qwen extensions install https://github.com/StalkChain/fomo-mcp-api
```

Review the extension details and confirm installation. Run `qwen extensions list` to check for **stalkchain-data** v1.0.1 or later. If you already installed v1.0.0, run `qwen extensions update stalkchain-data` so Qwen Code uses Streamable HTTP.

## Add only the hosted server

If you prefer to skip the extension, add the server directly:

```sh
qwen mcp add --scope user --transport http stalkchain https://data.stalkchain.com/mcp/directory
```

This adds the server for your user account. Use `--scope project` to configure only the current project. For a manual setup, merge this entry into your Qwen Code settings:

```json
{
  "mcpServers": {
    "stalkchain": {
      "httpUrl": "https://data.stalkchain.com/mcp/directory"
    }
  }
}
```

## Sign in to StalkChain

1. Start or restart Qwen Code and enter `/mcp`.
2. Select `stalkchain`, choose **Authenticate**, and complete the StalkChain consent flow in your browser.
3. Return to Qwen Code and inspect the tools in `/mcp`. On a fresh setup, `qwen mcp list` can report **Disconnected** until you authenticate.

Qwen Code uses `http://localhost:7777/oauth/callback` by default. If Qwen Code runs on a remote machine, follow its documented remote callback setup. [Qwen Code MCP configuration](https://qwenlm.github.io/qwen-code-docs/en/users/features/mcp/)

## Try a public Solana wallet lookup

> Use StalkChain to summarize the current holdings for this public Solana wallet: <wallet address>. Include token mint addresses, balances, and when the data was observed. Flag assets with missing prices.

Replace `<wallet address>` with a full public address. This lookup uses `stalkchain_wallet_portfolio`. Check tool costs before approving metered requests, and keep account-changing tools on manual approval. [Wallet research workflow](solana-wallet-tracker-mcp.md) · [StalkChain Data setup](https://stalkchain.com/mcp)
