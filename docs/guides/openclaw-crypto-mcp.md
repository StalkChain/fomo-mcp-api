# Connect the StalkChain crypto MCP to OpenClaw

Connect OpenClaw to StalkChain Data to research public Solana wallets, tracked traders, and token holders. This guide uses the hosted directory connector over Streamable HTTP with browser OAuth. Metered lookups use StalkChain account credits.

## Add StalkChain on your OpenClaw Gateway host

Check the existing MCP names with `openclaw mcp list`. If you already have a connection named `stalkchain`, check its URL with `openclaw mcp show stalkchain`. Use a separate name such as `stalkchain-research` in the commands below if you want to keep that connection and add the directory connector alongside it.

```sh
openclaw mcp add stalkchain --url https://data.stalkchain.com/mcp/directory \
  --transport streamable-http --auth oauth
openclaw mcp login stalkchain
openclaw mcp probe stalkchain
```

Complete sign-in and review the permissions on StalkChain when OpenClaw prompts you. Run the probe after approval to check that OpenClaw can discover tools. If you manage the Gateway remotely and the browser cannot reach its callback, follow the [OpenClaw OAuth instructions](https://docs.openclaw.ai/cli/mcp/transports). Keep the authorization code private.

You can also install the optional [StalkChain research skill on ClawHub](https://clawhub.ai/assistant-design/skills/stalkchain) for research instructions. Read the [skill source](../../integrations/openclaw/stalkchain/SKILL.md) before installing. The MCP connection handles authentication and tool access.

## Research a public Solana wallet

Start a thread with the connected agent and replace the placeholder with a full public Solana wallet address.

> Use StalkChain to check holdings for this public Solana wallet. Show me the planned lookup and estimated credits first. After I approve, report the full address, token balances, and observation time. Flag positions without a current price.

The directory connector supports research and email alerts. The example only reads public holdings. [Solana wallet research guide](solana-wallet-tracker-mcp.md) · [OpenClaw MCP documentation](https://docs.openclaw.ai/tools/mcp) · [StalkChain OpenClaw setup](https://stalkchain.com/ai/openclaw)
