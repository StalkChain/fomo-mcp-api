# Install the StalkChain crypto MCP plugin in Codex

The [StalkChain plugin](https://github.com/StalkC/stalkchain-plugin) combines the hosted research MCP with skills for checking traders, researching tokens, and tracking wallets. Install the plugin when you want the guided workflows as well as tool access.

## Install from the StalkChain GitHub marketplace

With a Codex release that supports plugin commands, run:

```sh
codex plugin marketplace add StalkC/stalkchain-plugin
codex plugin add stalkchain@stalkchain
```

Open the installed plugin in Codex. Connect **StalkChain Data**, sign in with your StalkChain account, and approve access. The plugin connects to `https://data.stalkchain.com/mcp/directory`. Confirm the connection in Codex before running a data lookup. [Source and install reference](https://github.com/StalkC/stalkchain-plugin#install-stalkchain-in-codex)

## Use the trader-check workflow

Start with a handle and ask for the wallets the service attributes to it. Then compare trades within a consistent time window.

> Use the StalkChain trader-check skill for this public trader handle. Show attributed wallet addresses and supporting evidence. Compare their closed trades over 30 days, flag positions that are still open, and mark any missing cost basis.

Account credits cover metered tool calls. The research MCP excludes trading and wallet execution. Alert tools can change your account's alerts and require confirmation.

If the plugin installs but the tools aren't available, open the plugin's MCP connection and finish OAuth. Installing the skill files alone does not authenticate the hosted service. [Wallet verification workflow](solana-wallet-tracker-mcp.md) · [Connection troubleshooting](../TROUBLESHOOTING.md)
