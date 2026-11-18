# Connect the StalkChain crypto MCP server to GitHub Copilot in VS Code

Connect StalkChain Data to GitHub Copilot Chat in VS Code to research Solana wallet holdings. You'll need VS Code with access to Copilot Chat and a free StalkChain Data account. Some lookups use account credits. [StalkChain plans](https://data.stalkchain.com/#plans)

## Install in VS Code

**[Add StalkChain to VS Code](https://vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522stalkchain%2522%252C%2522type%2522%253A%2522http%2522%252C%2522url%2522%253A%2522https%253A%252F%252Fdata.stalkchain.com%252Fmcp%252Fdirectory%2522%257D)**

Allow the browser to open VS Code. Review the proposed `stalkchain` server and install it. Sign in to StalkChain when VS Code prompts you to connect. [VS Code install link documentation](https://code.visualstudio.com/api/extension-guides/ai/mcp#create-an-mcp-installation-or-lookup-url)

### Add it manually

If the browser cannot open VS Code, select Copilot and run **Chat: Open Customizations** from the Command Palette. Under **MCP Servers**, select **Add Server** in the **User** group. Choose HTTP, enter `https://data.stalkchain.com/mcp/directory`, and name the server `stalkchain`. To use it across workspaces, select **Global**, then **Copilot Global**. A managed Copilot account may need its administrator to allow MCP servers. [VS Code MCP setup](https://code.visualstudio.com/docs/agent-customization/mcp-servers)

## Check a Solana wallet in Copilot Chat

Open Copilot Chat and use a public wallet address in your prompt. Expand the tool call to confirm Copilot used StalkChain.

> Use StalkChain to look up this Solana wallet's current holdings. Include the observation time and mint addresses. Flag balances that have no reliable price and be explicit about any missing coverage.

If Copilot cannot see the tools, check the server status in VS Code and finish OAuth sign-in. [Connection troubleshooting](../TROUBLESHOOTING.md) · [Solana wallet research workflow](solana-wallet-tracker-mcp.md)
