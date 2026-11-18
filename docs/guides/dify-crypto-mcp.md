# Connect the StalkChain crypto MCP to Dify

Use StalkChain Data in Dify workflows to look up Solana wallet activity, token holders, and tracked-trader flows. The hosted connector uses OAuth. Some queries use StalkChain account credits.

## Add StalkChain as a Dify tool

1. Open **Integrations → Tools → MCP** in a workspace where you can manage tools. Select **Add MCP Server**.
2. Name it **StalkChain Data**. Use `stalkchain-data` as the server identifier and `https://data.stalkchain.com/mcp/directory` as the server URL.
3. Leave **Dynamic Client Registration** enabled. Save the server and follow the prompt to sign in to StalkChain in your browser.
4. Return to Dify and confirm the server's tools appear. Keep the server identifier stable if you export or share a workflow that references it.

[Official Dify MCP setup](https://docs.dify.ai/en/cloud/use-dify/workspace/tools#connect-an-mcp-server)

## Try a private Solana wallet workflow

1. Create a private workflow with a text input for a public Solana wallet address.
2. Add a **Tool** node and pick the StalkChain wallet lookup you need. Map the wallet input to the tool's wallet-address field.
3. Run the full workflow with one known public address. Check the returned wallet address, balances, observation time where available, and any missing prices.

Check the tool price and account balance before a metered run. Before sharing the workflow or enabling a schedule, confirm whose StalkChain authorization it will use and who will pay for the calls. [Wallet research workflow](solana-wallet-tracker-mcp.md) · [StalkChain account](https://data.stalkchain.com/)
