<img src="logo-400.png" alt="Beheer je WP logo" width="96" height="96">

# Beheer je WP MCP server

**Manage a WordPress site from your AI assistant: read, search, propose edits, Search Console data.**

Remote MCP server: `https://beheerjewp.nl/mcp` (Streamable HTTP) · Website: [beheerjewp.nl](https://beheerjewp.nl/)

## What it does

Beheer je WP connects an AI assistant to one WordPress site you authorize. The assistant reads the site overview, searches posts and pages, and reads their content. When you ask for a change, it prepares a proposal; a WordPress administrator approves or rejects it in wp-admin, so nothing changes without a person saying yes. On the SEO Pro plan it also reads Google Search Console data for the site and points at pages that get impressions but few clicks.

The assistant cannot approve its own proposals. Search Console access is read-only.

## Connect

- **Server URL:** `https://beheerjewp.nl/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Requires a beheerjewp.nl account and the Beheer je WP plugin on the site.

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the server URL.

**Claude Code:**

```bash
claude mcp add --transport http beheerjewp https://beheerjewp.nl/mcp
```

**Cursor, VS Code, Cline, Windsurf and other clients** (`mcp.json` / `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "beheerjewp": {
      "type": "http",
      "url": "https://beheerjewp.nl/mcp"
    }
  }
}
```

Cline uses `"type": "streamableHttp"`; see [llms-install.md](llms-install.md).

## Tools

| Tool | What it does |
|---|---|
| `get_connection_status / get_site_overview` | Which site is linked, plan and site summary. |
| `list_posts / get_post_content` | Search posts and pages, read content. |
| `propose_post_update` | Prepare an edit for approval in wp-admin. |
| `get_search_performance / find_seo_opportunities` | Search Console clicks, impressions, CTR, position; pages to improve. |
| `get_brand_guidance / get_product_capabilities / prepare_seo_service_request` | Brand notes, plan features, SEO help request. |

## Example prompts

- Which pages on my site lost clicks in the last 28 days?
- Find my posts about WordPress backups and summarize them.
- Rewrite the title of draft 7 and put it up for approval.

## Links

- Website: https://beheerjewp.nl/
- Documentation: https://beheerjewp.nl/wordpress-mcp
- Privacy policy: https://beheerjewp.nl/privacy
- Terms: https://beheerjewp.nl/voorwaarden
- Support: mailto:support@beheerjewp.nl

## Keywords

WordPress MCP server, WordPress AI assistant, manage WordPress with AI, WordPress SEO, Google Search Console, content editing with approval, wp-admin.

Nederlands: WordPress beheren met AI, WordPress onderhoud, WordPress SEO, Search Console inzichten, website beheer, WordPress plugin AI, teksten aanpassen WordPress.

## More MCP servers by Samautomation

- [Scamchecker.nl](https://scamchecker.nl/): Check a suspicious email, SMS, WhatsApp message or link for scam signals (Netherlands, Belgium). ([listing](https://github.com/smrht/scamchecker-mcp))
- [Klussenbeheer](https://samdesk.nl/klussenbeheer/): Job management for Dutch service companies: jobs, customers, planning, quotes and invoices. ([listing](https://github.com/smrht/klussenbeheer-mcp))
- [Muziek maken met AI](https://muziekmakenmetai.nl/): Make an original song from a prompt or your own lyrics. Two versions per song, MP3 download. ([listing](https://github.com/smrht/muziekmakenmetai-mcp))
- [UlazAI Media](https://ulazai.com/): Create private AI images with your UlazAI account: pick a model, confirm, generate, download. ([listing](https://github.com/smrht/ulazai-mcp))
- [Backlinkswinkel](https://backlinkswinkel.nl/): Search Dutch websites for backlinks, check metrics and prices, order after confirmation, track. ([listing](https://github.com/smrht/backlinkswinkel-mcp))
- [Backlinksbeheer](https://backlinksbeheer.nl/): Read your stored backlinks, link checks and lost-link alerts per domain. Read-only. ([listing](https://github.com/smrht/backlinksbeheer-mcp))
- [Samautomation Video](https://samautomation.work/): Render an MP4 from your own images, clips, voice-over and timed captions. JSON to video. ([listing](https://github.com/smrht/samautomation-video-mcp))
- [PDF Samenvoegen](https://pdfsamenvoegen.nl/): Merge your own PDFs in a confirmed order and get one downloadable PDF. ([listing](https://github.com/smrht/pdfsamenvoegen-mcp))
- [Diamond Painting Converter](https://diamondpaintingconverter.com/): Find your purchased diamond painting patterns and download the PDF with DMC colour legend. ([listing](https://github.com/smrht/diamondpaintingconverter-mcp))
- [Nummerschilderen.com shop advisor](https://nummerschilderen.com/): Search paint-by-number kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/nummerschilderen-mcp))
- [DiamondPaintingWinkel.nl shop advisor](https://diamondpaintingwinkel.nl/): Search diamond painting kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/diamondpaintingwinkel-mcp))
- [AI Rechtshulp](https://ai-rechtshulp.nl/): Search Dutch and EU case law with ECLI sources and verify quotes against the judgment. ([listing](https://github.com/smrht/ai-rechtshulp-mcp))
- [SamDesk Support](https://samdesk.nl/support/plugin/): Read your SamDesk support inbox, find customer agreements and draft replies. Read-only. ([listing](https://github.com/smrht/samdesk-support-mcp))

## Publisher

Samautomation, Wognum, the Netherlands · https://samautomation.work

This repository holds the public listing (README, `server.json`, install notes). The server itself is hosted by the publisher; there is nothing to install or build.
