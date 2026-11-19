# Connect StalkChain Data to Docker MCP Toolkit

Docker MCP Toolkit can route a StalkChain research profile to a compatible client such as Claude Code, Cursor, or VS Code. The profile connects to StalkChain’s hosted Streamable HTTP endpoint at `https://data.stalkchain.com/mcp/directory`. This endpoint supports public wallet, token, and tracked-trader research and excludes trade execution.

## Import a profile while Docker reviews the catalog entry

Run these commands on a machine with Docker Desktop running and MCP Toolkit enabled. This creates a dedicated profile called **StalkChain Research**. If that profile already exists, open it instead of creating it again.

```sh
mkdir -p "$HOME/.docker/mcp/catalogs"
curl -fLsS \
  https://raw.githubusercontent.com/antoinersx/mcp-registry/32afbb6140a03d61456120581156856e428a7a47/servers/stalkchain/server.yaml \
  -o "$HOME/.docker/mcp/catalogs/stalkchain-directory.yaml"

docker mcp profile create \
  --name "StalkChain Research" \
  --id stalkchain-research \
  --server file://stalkchain-directory.yaml

docker mcp profile show stalkchain-research --format json
```

The imported profile should show a remote server named `stalkchain` and the `/mcp/directory` endpoint. Open **MCP Toolkit → Profiles → StalkChain Research**, then use the server’s configuration to start [Docker’s OAuth flow](https://docs.docker.com/ai/mcp-catalog-and-toolkit/toolkit/#authorize-a-server-with-oauth). Sign in on StalkChain and review the requested access. In the profile’s **Clients** section, connect your MCP client. Check your [StalkChain account](https://data.stalkchain.com) for credit balance and current pricing before making metered calls.

For a first lookup, ask your client to summarize the publicly visible holdings of a Solana address you supply. Check that it cites the address and identifies the data timestamp.

## Test status

We verified the dedicated profile import with Docker’s command-line tool. Docker’s OAuth discovery and registration reached StalkChain sign-in for both the official catalog callback and the local callback used by manually imported servers. The signed-in lookup is pending. Follow the [Docker MCP Catalog submission](https://github.com/docker/mcp-registry/pull/7303) for the official listing.
