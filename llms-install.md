# Installing Beheer je WP in Cline

This is a hosted remote MCP server. There is nothing to clone, build or install.

Add this entry to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "beheerjewp": {
      "type": "streamableHttp",
      "url": "https://beheerjewp.nl/mcp",
      "disabled": false
    }
  }
}
```

Authentication: OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Requires a beheerjewp.nl account and the Beheer je WP plugin on the site.

With OAuth, Cline opens the sign-in page the first time a tool is used; approve access and return to Cline.

Check the connection by asking: "Which pages on my site lost clicks in the last 28 days?"
