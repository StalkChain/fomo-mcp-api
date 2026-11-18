# StalkChain MCP in n8n

Import [`stalkchain-mcp-health.json`](stalkchain-mcp-health.json) into n8n to test the hosted StalkChain connector with one manual, zero-credit health call. The workflow is configured for the MCP Client node in n8n 2.48.5.

1. Open **StalkChain health** in the imported workflow.
2. Under **Authentication**, select **MCP OAuth2** and create a credential for the endpoint `https://data.stalkchain.com/mcp/directory`.
3. Keep **Register Client Automatically** enabled. If prompted for a **Resource URL**, use the same scoped endpoint. Follow the browser prompt to sign in and approve StalkChain access.
4. Save the credential and run the workflow manually. The **StalkChain health** node calls `stalkchain_health` with empty arguments and returns the API's health response. The response may report that an individual source is degraded even when the API is reachable.

The JSON contains no credential, API key, wallet address or schedule. Leave it inactive while setting it up. If you replace the health tool with a metered lookup, check the tool price and account balance before running or scheduling it.

[n8n MCP Client documentation](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-langchain.mcpClient/) · [StalkChain tool reference](https://stalkchain.com/docs/tools)
