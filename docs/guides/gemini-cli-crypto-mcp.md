# Connect the StalkChain crypto MCP server to Gemini CLI

Install the StalkChain Data extension to look up Solana wallet holdings, token holders, and tracked trader activity from Gemini CLI. You’ll need Gemini CLI and a StalkChain Data account. Some lookups use credits. [Gemini CLI installation](https://geminicli.com/docs/get-started/installation/) · [StalkChain plans](https://data.stalkchain.com/#plans)

## Install and sign in

1. In your terminal, install the extension from this repository:

   ```sh
   gemini extensions install https://github.com/StalkChain/fomo-mcp-api
   ```

2. Start a new Gemini CLI session and run `/extensions list`. Look for **stalkchain-data**.
3. Run `/mcp auth stalkchain`. Sign in to StalkChain in the browser and approve access.
4. Return to Gemini CLI and run `/mcp list`. Look for **stalkchain** and its discovered tools. The extension connects to the OAuth-protected endpoint at `https://data.stalkchain.com/mcp/directory`. [Gemini CLI MCP authentication](https://geminicli.com/docs/tools/mcp-server/)

If the browser sign-in doesn’t finish, run `/mcp auth stalkchain` again and complete authorization before retrying. If the extension is missing from the list, restart Gemini CLI and check the installed extensions again. [Connection troubleshooting](../TROUBLESHOOTING.md)

## Look up a Solana wallet

Use a full public Solana address. Check the current credit cost in the [StalkChain tool reference](https://stalkchain.com/docs/tools) before running a lookup.

> Use StalkChain Data to list this Solana wallet’s current holdings: [public wallet address]. Include the observation time, token amounts, and which holdings lack a price. Ask before running any additional tools.

For historical trades and PnL, use the [Solana wallet tracker guide](solana-wallet-tracker-mcp.md).
