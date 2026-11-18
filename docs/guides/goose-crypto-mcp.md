# Connect the StalkChain crypto MCP to Goose

Use StalkChain Data in Goose Desktop or CLI to look up public Solana wallet holdings, trading PnL, and token holders. The hosted connector uses StalkChain OAuth. Some queries use account credits.

## Add the remote extension in Goose Desktop

1. Open **Extensions** from the sidebar, then choose **Add custom extension**.
2. Name it **StalkChain Data**. Choose the remote Streamable HTTP type and enter `https://data.stalkchain.com/mcp/directory`.
3. Save the extension and use the browser prompt to sign in to StalkChain and approve access. Check that the extension is enabled and tools are available before running a research prompt.

## Connect from Goose CLI

For one session, run the following command from a Goose installation with a model provider configured.

```sh
goose session --with-streamable-http-extension https://data.stalkchain.com/mcp/directory
```

For a connection you can reuse, run `goose configure`, choose **Add Extension**, and select **Remote Extension (Streamable HTTP)**. Enter the same name and URL. Follow Goose's browser sign-in prompt when the extension connects. [Official Goose extension setup](https://goose-docs.ai/docs/getting-started/using-extensions/)

## Look up a public Solana wallet

> Show the current holdings of this public Solana wallet: [paste address]. Report priced holdings and unpriced assets separately, and include the observation time when available.

Check the returned chain, wallet address, and observation time before comparing results. Account setup is free. Check the account balance before a metered lookup. [Wallet research workflow](solana-wallet-tracker-mcp.md) · [StalkChain tool reference](https://stalkchain.com/docs/tools)

If sign-in loops, verify that the extension still points to the exact URL above and that your browser can return to Goose's local callback. For a CLI session on a remote machine, run the sign-in from the machine hosting Goose or use Goose's supported callback setup. [OAuth troubleshooting](../TROUBLESHOOTING.md)
