# Developer guide: hosted MCP and REST

## Choose the right connection

**MCP:** connect `https://data.stalkchain.com/mcp` in a Streamable HTTP client, or use `https://data.stalkchain.com/mcp/directory` for the directory connector. The directory connector exposes research and email alerts. Both endpoints use OAuth 2.1. Follow the [client setup instructions](../README.md#quick-start-mcp), [getting started](https://data.stalkchain.com/docs/guides/getting-started), or [llms.txt](https://data.stalkchain.com/llms.txt).

**REST:** call `https://data.stalkchain.com/api/v1` from a backend service or script. Generate a key in your StalkChain Data dashboard; send it as `Authorization: Bearer <key>`. Do not embed the key in a public website, mobile bundle, screenshot, code example with real values, or Git history.

Use the [public OpenAPI specification](https://data.stalkchain.com/api/v1/openapi.json) to generate typed clients or inspect current per-tool GET/POST input schemas. An authenticated `GET /api/v1/tools` lists tools and schemas; unauthenticated access returns 401. The authenticated `GET /api/v1/me` describes your balance/usage.

## First read-only requests

The public OpenAPI spec can be read without a key:

```sh
curl -fsS https://data.stalkchain.com/api/v1/openapi.json
```

The public reachability check at `/healthz` requires no account. An OAuth client can also check discovery with the directory endpoint. A signed-out request to that endpoint returns HTTP 401 with a `WWW-Authenticate` header that identifies its protected-resource metadata. That response confirms reachability and OAuth discovery. Testing a signed-in tool requires an account.

```sh
curl -fsS https://data.stalkchain.com/healthz
curl -sS -D - -o /dev/null https://data.stalkchain.com/mcp/directory
```

The `stalkchain_health` REST tool costs zero credits and requires a dashboard API key. Keep the key in your backend environment:

```sh
curl -fsS -H "Authorization: Bearer ${STALKCHAIN_API_KEY}" \
  https://data.stalkchain.com/api/v1/tools/stalkchain_health
```

Inspect the returned schema rather than assuming a fixed JSON shape. For paid tools, confirm the current tool name, JSON input shape and credit cost in the OpenAPI, then create an authenticated request in **your own backend**. Never assume a token ticker uniquely identifies an asset; use the immutable mint/contract plus chain wherever supported. Do not turn this repository into a proxy: the hosted API is the canonical execution surface.

## Billing and budgets

- The account balance is shared by the hosted service's MCP and REST calls, according to the [current documentation](https://data.stalkchain.com/docs/credits).
- A natural-language prompt may trigger several tools; composite tools may call multiple upstream endpoints. Record both tool costs and total cycle cost in automated workflows.
- Purchased-pack and promotional-credit balances can have different expiry policies. Check the actual dashboard terms; this repo does not promise a promotional grant.
- A scheduled Claude task, cron job or bot is **your** automation. Bound its time window, runs per day, tools used, concurrency and budget; pause on 402 or repeated errors.
- Cached responses may still incur a documented tool charge; inspect the current live rules rather than assuming cache means free.

## Response interpretation

The published API describes responses with `data`, possible `notes`, `credits` and `meta`. Confirm the current response structure in OpenAPI and inspect `credits`/`meta` in each real call. Preserve the source observation timestamp, chain, token contract, wallet identifiers, coverage notes, and cache age with any stored analysis. Do not collapse an empty observation into proof that an actor sold or a token had no activity.

## Errors and retries

- **401:** missing/expired authorization. For MCP, complete the OAuth flow; for REST, check the backend key. Do not log the bearer value.
- **400:** wrong tool arguments or incompatible input schema. Refresh the live tool schema before retrying.
- **402:** insufficient credits for the tool. Stop automated retries; inspect balance and current costs.
- **502/upstream errors:** distinguish provider failure from “no results”; bounded retry only when safe, without hammering a costly tool.
- **No current signal:** a bounded feed, tracked-wallet registry and chosen time window can legitimately have zero matches. Preserve this coverage context.

## Analytical boundaries

A tracked trader's social handle does not establish sole ownership of a wallet. Flow, activity and PnL estimates may include missing basis, open inventory, historical prices or partial venue coverage. An apparent fast wallet cluster can be related accounts. Before any consequential publication or trading decision, confirm exact transactions, asset identity, price timestamp, liquidity and the executable sell route.

This service exposes research tools; this repo does not sign transactions, place orders or automatically trade.
