# Troubleshooting

## “How do I install this repository?”

You do not. It is **documentation for an existing hosted service**, not a package or a local MCP implementation. Use the endpoint `https://data.stalkchain.com/mcp` in your MCP client. See the [official setup guide](https://data.stalkchain.com/docs/guides/getting-started).

## My MCP client cannot connect

Confirm that it supports remote **Streamable HTTP** MCP, that the endpoint is exactly `https://data.stalkchain.com/mcp`, and that the browser OAuth sign-in/approval completed. Refresh the connection or start a new chat after authorizing. A normal browser GET to `/mcp` is not a complete MCP protocol test.

## My REST request returns 401

The `/api/v1/tools` catalog requires authentication. Generate a REST key in your dashboard and pass it server-side in an `Authorization: Bearer` header; do not paste it into GitHub or browser JavaScript. For public discovery use [OpenAPI](https://data.stalkchain.com/api/v1/openapi.json) instead.

## A tool returns 400

Check the exact current input JSON schema, method and required fields in OpenAPI. Confirm chain plus token contract or immutable wallet ID rather than guessing from a ticker or mutable social handle.

## A tool returns 402

Your account may lack sufficient credits for that tool. Stop the loop, inspect your balance and [current pricing](https://data.stalkchain.com/#plans); do not retry a paid call indefinitely. Connecting the MCP is free, but paid research tools are metered.

## The service returns 502 or a result is empty

Check service status or an authenticated zero-credit `stalkchain_health` call; the REST health route returned 401 anonymously even though an older spec describes it as keyless. A 502 indicates an upstream/tool issue, not necessarily absence of token activity. Empty results can reflect time window, coverage, registry state, or filters. Preserve the exact query and observation time for support.

## Why did one question use multiple credits?

An AI may use multiple tools to answer one question, and a composite analysis may use multiple upstream data sources. Check the tool's documented credit cost and the response's usage block. Bound calls per scheduled run, and ask the agent to state its proposed tool plan before expensive research.

## Why are the README and tool catalog counts different?

The hosted site's landing page, documentation introduction and OpenAPI description have shown different counts. This repository intentionally avoids a frozen total and points to the current registry/schema. See [source-of-truth notes](SOURCE-OF-TRUTH.md).

## Can it place trades automatically?

Not through this repository. StalkChain Data's documented tools provide research data. A separate execution system would require its own authorization, risk limits, fee/slippage checks and transaction reconciliation. Never mistake an alert for an executable recommendation.

## Reporting a documentation problem

Open a GitHub issue with the exact page, conflicting official URL, observed date, and expected behavior. Do not post API keys, private addresses or account data. For service/account support, use the contacts on [StalkChain Data](https://data.stalkchain.com).
