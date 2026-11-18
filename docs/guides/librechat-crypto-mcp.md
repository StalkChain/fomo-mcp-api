# LibreChat crypto MCP setup for Solana wallet research

Connect StalkChain Data to LibreChat to look up public Solana wallet activity, token holders, and tracked trader flows. Use a LibreChat release that supports remote MCP over Streamable HTTP and OAuth. StalkChain data calls use your account credits when metered.

## Add StalkChain in LibreChat

1. Open **MCP Settings** and select **Add MCP**. If the button is missing, ask your LibreChat administrator to add the server or grant permission to create MCP servers.
2. Name it **StalkChain Data**. Enter `https://data.stalkchain.com/mcp/directory` as the server URL and choose **Streamable HTTPS**.
3. Choose **None (Auto-detect)**. LibreChat switches to OAuth when StalkChain returns its sign-in challenge. Review the server details, confirm that you trust the application, and choose **Create**.
4. Connect the server in **MCP Settings** or enable it in the chat’s MCP picker. When prompted, select **Continue with OAuth**, sign in to StalkChain, and approve the connection.

[LibreChat MCP settings and OAuth](https://www.librechat.ai/docs/features/mcp)

## Configure a self-hosted deployment

If an administrator manages the server list in `librechat.yaml`, merge this entry into its existing `mcpServers` map and restart LibreChat.

```yaml
mcpServers:
  stalkchain-data:
    type: streamable-http
    url: https://data.stalkchain.com/mcp/directory
    requiresOAuth: true
```

Set `DOMAIN_SERVER` to the base URL where users open LibreChat. For this YAML key, LibreChat returns OAuth users to `/api/mcp/stalkchain-data/oauth/callback` on that base URL. A local install on port 3080 uses `http://localhost:3080/api/mcp/stalkchain-data/oauth/callback`. Servers created in the UI use a generated identifier, so use LibreChat’s displayed redirect URL when troubleshooting. LibreChat can register with StalkChain dynamically using its callback. [LibreChat YAML and callback reference](https://www.librechat.ai/docs/configuration/librechat_yaml/object_structure/mcp_servers)

## Try a Solana wallet lookup

> Use StalkChain Data to look up this public Solana wallet: [paste address]. Show the current token holdings, separate holdings with no current price, and include the observation time when available.

Check that the result identifies the correct address and chain. StalkChain can query public wallet activity without asking you to connect the wallet or sign a transaction. [Solana wallet research workflow](solana-wallet-tracker-mcp.md) · [StalkChain tool reference](https://stalkchain.com/docs/tools)
