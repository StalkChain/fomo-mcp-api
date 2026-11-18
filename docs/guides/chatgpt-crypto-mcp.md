# Connect the StalkChain crypto MCP server to ChatGPT

Use ChatGPT on the web to check the public trading record and attributed wallets behind a FOMO handle. Custom MCP app access depends on your ChatGPT plan and workspace permissions. Workspaces can also control who can create and use custom apps. [ChatGPT custom MCP documentation](https://help.openai.com/en/articles/12584461)

## Add the app in ChatGPT

1. Open **Settings → Apps → Advanced Settings** and enable **Developer mode** if available. Workspace admins can also create an app from **Workspace settings → Apps → Create**.
2. Select **Create** in Apps. Name the app **StalkChain Data**, enter `https://data.stalkchain.com/mcp/directory`, and select **OAuth** as the authentication method.
3. Select **Scan Tools**. Sign in to StalkChain, review the requested access, and approve the connection. Wait for discovery to finish, then select **Create**.
4. In a new ChatGPT chat, select the StalkChain app from the available apps. Some data calls use StalkChain account credits. [StalkChain plans](https://data.stalkchain.com/#plans)

If **Create** or **Developer mode** is missing, check your plan and workspace permissions. If an existing connection stops working, reconnect through the Apps settings. [Connection troubleshooting](../TROUBLESHOOTING.md)

## Check a public trader

Use the trader's exact handle and ask for evidence from the attributed wallets.

> Use StalkChain Data to check the public trading record for this FOMO handle. Show the wallet attribution, available 30-day closed-trade PnL and the number of closed trades in the sample. Flag missing cost basis and exclude open positions from realized PnL.

[StalkChain’s ChatGPT guide](https://stalkchain.com/ai/chatgpt) · [Solana wallet holdings and PnL](solana-wallet-tracker-mcp.md)
