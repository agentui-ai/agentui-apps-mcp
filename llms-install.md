# Installing the AgentUI Apps MCP server

This is a **remote** MCP server. Don't clone, build or install anything from this repository.

1. Check that Node.js 18 or later is installed (`node --version`).
2. Add this entry under `mcpServers` in the Cline MCP settings file:

```json
"agentui-apps": {
  "command": "npx",
  "args": ["-y", "mcp-remote", "https://api.agentui.ai/mcp/apps"]
}
```

3. Save the file. A browser window opens for the AgentUI sign-in. Ask the user to sign in, or to create an account at https://agentui.ai if they don't have one, and approve access.
4. Check that it works by calling the `apps_list` tool. An empty list is normal for a new account.

No API key or environment variables are needed. OAuth handles authentication.
