# Perplexity Computer crypto MCP setup for Solana wallet research

Connect StalkChain Data to Perplexity Computer to research public Solana wallets, token holders, and tracked trader activity. Perplexity offers custom remote connectors on eligible plans, including Pro, Max, and Enterprise. In an organization, an administrator may need to allow personal connectors. Metered StalkChain calls use your StalkChain account credits.

## Add StalkChain Data as a remote connector

1. Open [Plugins](https://www.perplexity.ai/computer/plugins) in Perplexity. Select **Add custom**, then **Add MCP connector**, and choose **Remote**.
2. Name it **StalkChain Data** and enter `https://data.stalkchain.com/mcp/directory`.
3. Under **Advanced**, choose **OAuth**, **Streamable HTTP**, and **Public** network access. Leave the client ID and secret empty so the connector can register dynamically.
4. Review the custom connector acknowledgement and select **Add**. Open the new connector card, sign in to StalkChain, and approve the requested access.
5. In a Computer task, name **StalkChain Data** when you ask it to use the connector. In an organization, an administrator can also add it under **Organization settings → Connectors** and enable it for members.

[Perplexity remote connector documentation](https://www.perplexity.ai/help-center/en/articles/13915507-adding-custom-remote-connectors)

## Import the StalkChain plugin from GitHub

For Perplexity Computer plans that support custom plugins with skills, open **Plugins → Add custom → Import plugin from GitHub**. Enter `https://github.com/StalkC/stalkchain-plugin`. On the plugin page, confirm that the StalkChain connector appears alongside the included skills. Open the connector to sign in.

The public repository already contains the portable plugin manifest and remote MCP configuration. If the connector does not appear after import, check your organization's custom connector permissions, then use the direct setup above. [StalkChain plugin repository](https://github.com/StalkC/stalkchain-plugin) · [Perplexity plugin import documentation](https://www.perplexity.ai/help-center/en/articles/2026100802-create-or-upload-a-custom-plugin)

## Try a Solana wallet lookup

> Use StalkChain Data to look up this public Solana wallet: [paste address]. Show its current token holdings, flag holdings without a current price, and include the observation time if available.

Check that the result matches the address and chain. A public wallet lookup does not require connecting that wallet or signing a transaction. If an answer contains only web results, check that the StalkChain Data connector is enabled and signed in. [Wallet research workflow](solana-wallet-tracker-mcp.md) · [Tool reference](https://stalkchain.com/docs/tools)
