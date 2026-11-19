# Connect a crypto MCP server to Claude and Claude Code

Use StalkChain Data to look up crypto wallets, token holders, and tracked-trader flow from Claude. This guide uses the hosted research connector. It includes alert tools that ask for confirmation and excludes trading and wallet execution.

## Claude.ai or Claude Desktop

1. In Claude's connector settings, add a custom connector called **StalkChain Data**.
2. Enter `https://data.stalkchain.com/mcp/directory`.
3. Connect the server, sign in to StalkChain, and approve access. If your workspace restricts custom connectors, ask its administrator to enable them.
4. Open a chat with the connector enabled and try a lookup below.

See the [StalkChain Claude connection guide](https://stalkchain.com/docs/guides/connect-claude) for the current menus.

## Claude Code

Add the same remote MCP to your local Claude Code configuration:

```sh
claude mcp add --transport http stalkchain https://data.stalkchain.com/mcp/directory
```

In a Claude Code session, run `/mcp`, select **stalkchain**, and finish the browser sign-in. Return to `/mcp` to check that the connection is active. [Claude Code MCP reference](https://code.claude.com/docs/en/mcp)

## Try a first lookup

> Use StalkChain Data to inspect this exact public wallet address on Solana. Show current holdings and the observation time. If you also report realized PnL, state the coverage returned by the source and flag missing cost basis.

Replace the wallet placeholder with the full address. Begin with holdings alone if you want to limit calls. Some lookups use account credits. [Solana wallet and PnL workflow](solana-wallet-tracker-mcp.md) · [Hyperliquid wallet and funding workflow](hyperliquid-mcp.md)

If the connector asks you to sign in again, reconnect from the client. A direct HTTP request without OAuth receives a 401 challenge. See [connection troubleshooting](../TROUBLESHOOTING.md).
