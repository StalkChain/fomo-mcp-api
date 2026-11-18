# Connect the StalkChain crypto MCP server to Grok

Use StalkChain Data in Grok to see which tracked traders hold a token and how their positions have changed. The connection uses your StalkChain account. Some lookups use account credits. [StalkChain plans](https://data.stalkchain.com/#plans)

## Add StalkChain as a custom connector

1. Open [Grok Connectors](https://grok.com/connectors) and sign in to Grok.
2. Select **New Connector → Custom**. Enter `https://data.stalkchain.com/mcp` and name the connector **StalkChain Data** if Grok asks for a name.
3. Sign in to StalkChain when prompted and review and approve the request. Confirm the connector appears under **Custom**, then use it in a new chat. [Grok connector documentation](https://docs.x.ai/grok/connectors)

If Grok cannot use the tools, check the connection status in Grok Connectors and finish the StalkChain authorization flow. [Connection troubleshooting](../TROUBLESHOOTING.md)

## Check tracked token holders

Use a Solana mint address or an exact token contract and chain.

> Use StalkChain Data to show which tracked wallets still hold this token. Include the observation time, positions where available, and recent sells with timestamps. Flag any gaps in wallet coverage.

[StalkChain’s Grok guide](https://stalkchain.com/ai/grok) · [Token holder and smart-money workflow](token-holders-smart-money-mcp.md)
