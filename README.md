# VPS Scouter MCP

Compare VPS hosting plans by price, specs, and server location. See renewal rates and find a plan that fits your budget.

[VPS Scouter](https://vpsscouter.com) offers a public, read-only Model Context Protocol server for its [open VPS price data](https://vpsscouter.com/data). Use **`https://vpsscouter.com/mcp`** with **Streamable HTTP**. The server requires no API key or login.

## Tools

| Tool | What it returns |
| --- | --- |
| `find_cheapest_vps` | Plans filtered by RAM, vCPU, storage, budget, location, or billing term. |
| `get_provider_plans` | Plans from a provider. |
| `price_changes` | Changes in advertised plans and prices. |
| `vps_price_index` | VPS price index data. |

## Claude Desktop

Open **Customize → Connectors → Add → Add custom connector**. Name it `VPS Scouter` and enter `https://vpsscouter.com/mcp` as the remote server URL. Continue through the connection dialog, then enable the connector in the conversation. Managed workspaces may require an owner to add it first.

[Claude custom connector documentation](https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp)

## Claude Code

```bash
claude mcp add --transport http vpsscouter https://vpsscouter.com/mcp
claude mcp list
```

In an interactive session, `/mcp` shows the configured servers and their status.

[Claude Code MCP documentation](https://code.claude.com/docs/en/mcp)

## Cursor

Merge this server into `.cursor/mcp.json` for the current project or `~/.cursor/mcp.json` for your user.

```json
{
  "mcpServers": {
    "vpsscouter": {
      "url": "https://vpsscouter.com/mcp"
    }
  }
}
```

[Cursor MCP documentation](https://cursor.com/docs/mcp)

## ChatGPT

Open [ChatGPT Plugins](https://chatgpt.com/plugins), select **+ → Add custom MCP server**, and enter `VPS Scouter` for the name and `https://vpsscouter.com/mcp` for the server URL. Select **No authentication**, review the connection prompt, and choose **Create as a plugin**. Select the plugin when composing a chat. Access depends on your plan and workspace permissions.

[ChatGPT custom MCP documentation](https://developers.openai.com/api/docs/guides/custom-mcp-server)

## Windsurf

In versions that use the Windsurf Cascade MCP configuration, open the raw MCP configuration from Cascade settings and merge this entry into `~/.codeium/windsurf/mcp_config.json`.

```json
{
  "mcpServers": {
    "vpsscouter": {
      "serverUrl": "https://vpsscouter.com/mcp"
    }
  }
}
```

For Devin Local, use the Cursor JSON shape above with `url` in `.devin/mcp_config.json` for the project or `~/.config/devin/mcp_config.json` for your user.

[Devin Local MCP configuration](https://docs.devin.ai/cli/extensibility/mcp/configuration)

## Try it

> Find VPS plans with at least 4 GB RAM and 2 vCPUs. Include the advertised billing term, renewal price when available, and provider source link.

Check the source date before comparing prices. The [CSV and JSON mirror](https://github.com/vpsscouter/vps-price-data) provides downloadable copies under CC BY 4.0.
