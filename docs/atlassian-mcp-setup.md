# Atlassian MCP connection setup

## 1) Add Atlassian MCP server config

Use `/home/runner/work/EricF-Crt-daily-ops/EricF-Crt-daily-ops/tools/mcp.atlassian.json` as your MCP config snippet:

```json
{
  "mcpServers": {
    "atlassian": {
      "url": "https://mcp.atlassian.com/v1/mcp/authv2"
    }
  }
}
```

Merge this into your MCP client config file as needed.

## 2) Restart/reload MCP client

Restart or reload your MCP client, then start a connection to the `atlassian` server.

## 3) Complete OAuth login

When prompted, complete the browser login and consent flow with your Atlassian account.

## 4) Optional non-interactive auth (bot/CI)

If you need token/key-based auth for automation, ask your Atlassian org admin to enable it first, then configure your MCP client with the approved method.

## 5) Verify connection

Run a simple Atlassian MCP action, such as:
- list Jira projects, or
- list Confluence spaces

If it fails, re-check:
- server URL (`https://mcp.atlassian.com/v1/mcp/authv2`)
- Atlassian account permissions
- org policy that may block token-based auth
