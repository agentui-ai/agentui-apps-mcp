# AgentUI Apps MCP

A hosted MCP server for [AgentUI](https://agentui.ai). Your AI assistant can create data apps, define tables, read and write records, and run programs on your data.

- **URL:** `https://api.agentui.ai/mcp/apps`
- **Transport:** Streamable HTTP
- **Auth:** OAuth. Your client opens a browser window the first time so you can sign in to AgentUI.
- **Registry:** `ai.agentui/apps` in the official MCP registry

There's nothing to install or run on your machine. It's a remote server.

## Tools

| Area | Tools |
|---|---|
| Apps | `apps_list`, `app_create`, `app_open` |
| Tables | `table_create`, `table_update`, `table_delete` |
| Records | `records_query`, `records_count`, `record_get`, `record_create`, `record_update`, `record_delete`, `records_bulk_create`, `records_bulk_update` |
| Programs | `programs_list`, `program_get`, `program_create`, `program_update`, `program_run`, `program_runs`, `program_set_trigger` |

## Setup

### Cline

Add this to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "agentui-apps": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://api.agentui.ai/mcp/apps"]
    }
  }
}
```

`mcp-remote` handles the OAuth sign-in in your browser. You need Node.js 18 or later.

### Claude Code

```bash
claude mcp add --transport http agentui-apps https://api.agentui.ai/mcp/apps
```

### Cursor, VS Code and other clients

Add a remote (Streamable HTTP) server with the URL `https://api.agentui.ai/mcp/apps`. If your client doesn't support OAuth for remote servers, use the `mcp-remote` command from the Cline example.

## Account

You need an AgentUI account. You can sign up at https://agentui.ai.

## Help

- Docs: https://help.agentui.ai
- Support and security issues: support@agentui.ai
