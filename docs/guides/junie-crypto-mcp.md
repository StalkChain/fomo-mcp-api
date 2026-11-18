# Connect the StalkChain crypto MCP to JetBrains Junie CLI

Use Junie CLI to ask about public Solana wallets, token holders, or tracked-trader flow. StalkChain Data runs as a hosted MCP server and uses browser sign-in. Metered tools draw from your StalkChain credit balance.

## Add StalkChain in Junie CLI

1. Start Junie CLI and enter `/mcp` in the interactive terminal.
2. Open the MCP Installation Assistant and add a server from scratch. Choose user scope to use it across projects, or project scope for this project only.
3. Choose **Remote** and enter `https://data.stalkchain.com/mcp/directory`. Name it `stalkchain`.
4. Return to the server list. When StalkChain shows **Authorization required**, select it and choose **Authorize**. Sign in to StalkChain in the browser and approve the connector.
5. Return to `/mcp` and check that the server shows **Active**.

If you use Junie through an ACP client, open the Junie terminal directly to set up OAuth. The `/mcp` view in ACP clients is read-only. See the [JetBrains MCP configuration guide](https://junie.jetbrains.com/docs/junie-cli-mcp-configuration.html).

## Try a Solana wallet lookup

Replace `<wallet-address>` with the public wallet you want to research.

> Use StalkChain to look up current Solana token holdings for <wallet-address>. Include token mint addresses, balances, and the observation time. Flag any tokens with missing prices.

Check the tool’s current price and your balance before running metered lookups. [Solana wallet tracker guide](solana-wallet-tracker-mcp.md) · [StalkChain Data dashboard](https://data.stalkchain.com/)
