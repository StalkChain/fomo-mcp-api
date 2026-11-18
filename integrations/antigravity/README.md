# StalkChain Data for Google Antigravity

Connect Antigravity to StalkChain Data for public Solana wallet holdings, token-holder research, tracked-trader flows, and Hyperliquid positions and funding. The plugin adds one hosted MCP server using Streamable HTTP. It requires a StalkChain account and browser sign-in. Some research calls use credits.

## Install from source

Clone the public developer repository and run the following from its root with the [Antigravity CLI installed](https://antigravity.google/docs/getting-started?tab=cli).

```sh
agy plugin validate --strict ./integrations/antigravity
agy plugin install ./integrations/antigravity
agy plugin list
```

In Antigravity, open **Settings → Customizations** and select **Authenticate** for the StalkChain server. Follow the browser prompt and return to Antigravity. If Antigravity asks for the authorization code displayed in your browser, paste it into Antigravity’s authentication panel. [Antigravity MCP authentication](https://antigravity.google/docs/ide-mcp#oauth)

For a manual connection in the IDE, open **MCP Servers → Manage MCP Servers → View raw config**. Merge the `stalkchain` entry from [mcp_config.json](mcp_config.json) into the existing `mcpServers` map and authenticate. Choose one installation method to avoid duplicate connections.

## Look up a public wallet

> Show the holdings for this public Solana wallet: [paste address]. Separate priced and unpriced assets and include the observation time when available.

Use an exact wallet address and chain. Research tools query public data. The scoped server cannot place trades or sign transactions. It can manage your StalkChain email price alerts if you ask and approve. The plugin sends MCP requests to `data.stalkchain.com` using your StalkChain authorization.

[StalkChain MCP setup](https://stalkchain.com/mcp) · [Tool reference and credit costs](https://stalkchain.com/docs/tools) · [Privacy](https://data.stalkchain.com/privacy) · [Support](mailto:support@stalkchain.com)
