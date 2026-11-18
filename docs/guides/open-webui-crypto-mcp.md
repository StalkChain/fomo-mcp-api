# Connect StalkChain's crypto MCP server to Open WebUI

Add StalkChain Data to a self-hosted Open WebUI instance to research public Solana wallets and token activity. You need an Open WebUI administrator to add the connection, a model that can call tools, and a StalkChain Data account. Individual research calls can use StalkChain credits. [Current plans](https://data.stalkchain.com/#plans)

## Add the hosted MCP connection

1. Open **Settings → Integrations** in the Open WebUI admin section. Under **External Tool Servers**, choose **Add Connection**.
2. Set **Type** to **MCP (Streamable HTTP)** and enter `https://data.stalkchain.com/mcp`. If Open WebUI asks for a server ID, use `stalkchain`.
3. Set **Auth** to **OAuth 2.1**. Keep the discovered scopes and automatic resource setting. The server advertises the `mcp` scope and its own OAuth endpoints. Use **Check OAuth Discovery**, then **Register Client** and **Save**.
4. Start a chat, open **+ → Tools**, and enable StalkChain. Sign in and approve the connection when StalkChain opens. Return to that same Open WebUI browser session. Each user authorizes their own StalkChain account.

On a self-hosted instance, set `WEBUI_URL` to the address users actually open, and keep `WEBUI_SECRET_KEY` stable across restarts so Open WebUI can read its saved sign-ins. If access is limited to a group, have the administrator set the connection's access controls. [Open WebUI's MCP and OAuth instructions](https://docs.openwebui.com/features/extensibility/mcp/)

## Check a public Solana wallet

Try a single wallet lookup first. Replace the bracketed text with a public Solana address.

> Use StalkChain's Solana wallet PnL tool for [public wallet address]. Report realized and unrealized PnL separately. Say what time window the data covers and flag incomplete cost basis or unpriced positions.

Check the tool call in the response. StalkChain's `stalkchain_wallet_pnl` expects a raw Solana address. If you start from a trader's handle, verify the public wallet attribution before checking PnL. [Solana wallet research guide](solana-wallet-tracker-mcp.md) · [Tool reference](https://stalkchain.com/docs/tools)

If OAuth discovery succeeds but tools are missing, enable StalkChain from the chat's Tools menu and finish signing in. Discovery checks the published login metadata. Tool access starts after the account grants consent. [StalkChain troubleshooting](../TROUBLESHOOTING.md)
