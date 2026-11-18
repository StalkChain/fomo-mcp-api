# StalkChain Data Postman collection

Import this collection to test account access and make read-only StalkChain Data requests from Postman.

1. Download the [Postman collection](stalkchain-readonly.postman_collection.json) and open it in **Import** in Postman. You can also paste the [raw collection URL](https://raw.githubusercontent.com/StalkChain/fomo-mcp-api/main/integrations/postman/stalkchain-readonly.postman_collection.json).
2. Create your own REST API key in the [StalkChain Data dashboard](https://data.stalkchain.com/dashboard). Save it in [Postman Local Vault](https://learning.postman.com/docs/use/postman-vault/manage-vault-secrets/) as `stalkchain-api-key`, with `data.stalkchain.com` as its allowed domain. In a private Postman environment, add `api_key` with the local value `{{vault:stalkchain-api-key}}` and select that environment.
3. Open **Check account** and select **Send**. With a valid key, this returns the account and balance. **Check service health** also uses zero credits after authentication.
4. Send individual research requests after reviewing their inputs and current credit costs.

| Request | Use |
| --- | --- |
| Check account | Confirm authentication and available credits |
| Check service health | Check the API and data-source status |
| Search traders and tokens | Find tracked traders or tokens by query |
| Get trader positions | Inspect a tracked trader's current positions |
| Get Solana token prices | Request prices for specific Solana mints |
| Get EVM token information | Inspect a token by chain and contract address |

A `401` means you should check the selected environment and API key. A `402` means the account has insufficient credits. A `429` means the request was rate limited. Keep API keys and account responses out of public collections and examples. [Live OpenAPI](https://data.stalkchain.com/api/v1/openapi.json) · [Tool reference and costs](https://stalkchain.com/docs/tools)
