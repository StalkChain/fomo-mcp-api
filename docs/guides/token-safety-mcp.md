# Token safety MCP for EVM contracts and Solana mints

Use StalkChain Data to inspect a token’s contract permissions, holder concentration, and liquidity. Start with the exact contract or mint and its chain. Connect the [hosted MCP](../../README.md#quick-start-mcp) over HTTP at `https://data.stalkchain.com/mcp` and sign in through StalkChain OAuth.

## Check an EVM token contract

Use `stalkchain_evm_token_check` with the chain and full `0x` contract address. The check reports sell restrictions and taxes, owner controls such as minting, pausing and blacklisting, proxy or verification status, and available holder and liquidity evidence. If you need to confirm the token’s name and ticker first, use `stalkchain_token_info` with the same chain and address.

A sell check reflects the provider’s observation. Use a current quote for the intended amount, and verify the relevant pool, liquidity, and contract settings before relying on it. A verified contract or a liquidity lock gives you one piece of evidence. Keep unknown checks visible.

## Check a Solana token mint

Use `stalkchain_token_onchain` with the mint address. Look for live mint and freeze authorities, top-holder concentration, the developer’s holdings, and available liquidity and LP burn evidence. For the deployer’s recent launches, use `stalkchain_token_deployer` and verify that the attributed wallet matches the mint.

Use the [holder and flow workflow](token-holders-smart-money-mcp.md) when you need to see which tracked wallets still hold a token or recently sold.

## Example research prompt

> Check this exact token on [chain]: [paste contract or mint]. Report control permissions, holder concentration, and liquidity. For an EVM token, include available sell restrictions and tax results. For a Solana mint, include mint and freeze authority. Give observation times and source references where available. Mark unknown checks and separate reported restrictions from an executable quote.

Tool coverage and credit costs vary. Check the [live tool reference](https://stalkchain.com/docs/tools) and the [OpenAPI specification](https://data.stalkchain.com/api/v1/openapi.json) for current inputs.
