# StalkChain Data for Microsoft 365 Copilot

The declarative agent connects to the [StalkChain directory MCP endpoint](https://data.stalkchain.com/mcp/directory) with OAuth. Copilot discovers the available tools after sign-in. StalkChain account credits apply to lookups.

## Provision a personal test in the company tenant

1. Copy `env/.env.example` to `env/.env.dev`.
2. Obtain a confidential client from StalkChain’s [registration endpoint](https://data.stalkchain.com/oauth/register). Register the Microsoft Teams callback `https://teams.microsoft.com/api/platform/v1.0/oAuthRedirect` with `client_secret_post`, scopes `mcp`, and grants `authorization_code` and `refresh_token`.
3. Put the issued client ID and secret in `env/.env.dev.user` under `STALKCHAIN_MCP_CLIENT_ID` and `SECRET_STALKCHAIN_MCP_CLIENT_SECRET`. Keep this file local. The Toolkit registers the Microsoft OAuth configuration and supplies the Microsoft app ID and auth reference during provisioning.
4. From this directory, sign in to the intended company tenant and provision the personal test build.

   ```sh
   npx --package @microsoft/m365agentstoolkit-cli@1.1.19 atk auth login m365
   npx --package @microsoft/m365agentstoolkit-cli@1.1.19 atk provision --env dev
   ```

   This installs the agent for the signed-in tester. Reuse the resulting app ID for subsequent builds.
5. In Copilot, open the installed agent, complete StalkChain sign-in, and test one authorized public lookup. Confirm OAuth refresh before preparing the store submission.

The Toolkit writes the provisioned package to `appPackage/build/StalkChain-Data.dev.zip`. Public store review is a separate step in the company Partner Center account. See [Microsoft’s publishing guide](https://microsoft.github.io/wiqd/getting-started/publish-to-partner-center/).

[Microsoft’s MCP action guide](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/build-mcp-plugins) covers the Teams callback and supported authentication options.
