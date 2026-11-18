# Raycast crypto MCP setup for StalkChain Data

Connect Raycast AI to StalkChain Data to research public Solana wallets, token holders, and recent trader activity from AI Chat or Quick AI. You need Raycast Pro for MCP and a StalkChain Data account for OAuth sign-in. Metered lookups use StalkChain account credits.

## Connect StalkChain Data in Raycast

1. On Raycast desktop, open **Install MCP Server** from Root Search.
2. Name it **StalkChain Data**, select **HTTP**, and enter `https://data.stalkchain.com/mcp/directory`.
3. Select **Dynamic** for OAuth and leave HTTP headers empty. Choose **Install MCP Server**.
4. Choose **Sign In**, follow the StalkChain sign-in prompt, and approve access.
5. Open **Manage MCP Servers** and check that StalkChain Data is **Running** and shows a tool list. If it shows **Stopped** or **Error**, open its details for the connection output.

## Look up a public Solana wallet

In AI Chat or Quick AI, type `@` and select **StalkChain Data** to direct the prompt to that server.

> Look up the portfolio of this public Solana wallet: [wallet address]. Give the observation time, the largest holdings reported, and any pricing or coverage gaps.

Replace the placeholder with the full public address. Check current credit costs in the tool reference before metered calls.

[Raycast MCP manual](https://manual.raycast.com/ai/model-context-protocol) · [StalkChain MCP setup](https://stalkchain.com/mcp) · [StalkChain tool reference](https://stalkchain.com/docs/tools)
