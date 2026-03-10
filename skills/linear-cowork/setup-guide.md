# Linear MCP Setup Guide

This guide covers setting up the Linear MCP server for use with the `linear-cowork` skill.

## Claude Code

```bash
claude mcp add --transport http linear-server https://mcp.linear.app/mcp
```

## Codex

```bash
codex mcp add linear --url https://mcp.linear.app/mcp
```

## Cursor

1. Open Cursor Settings (`Cmd+,` / `Ctrl+,`)
2. Navigate to **Features** → **MCP Servers**
3. Click **Add MCP Server**
4. Configure:
   - **Name:** `linear-server`
   - **Transport:** HTTP
   - **URL:** `https://mcp.linear.app/mcp`
5. Click **Save**

## Verification

After setup, verify the connection by asking Claude to list your Linear teams or issues. The Linear MCP server uses OAuth — you'll be prompted to authenticate on first use.

## Troubleshooting

- **Authentication errors:** Re-run the `mcp add` command to re-authenticate
- **Connection timeouts:** Ensure you have network access to `mcp.linear.app`
- **Missing tools:** Verify the MCP server is listed in your tool configuration with `claude mcp list` (Claude Code) or equivalent
