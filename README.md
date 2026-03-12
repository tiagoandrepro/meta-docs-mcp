<p align="center">
  <h1 align="center">Meta Docs MCP</h1>
  <p align="center">Semantic search across Meta's entire developer documentation — from any AI assistant.</p>
</p>

<p align="center">
  <a href="https://meta.tiagoandrepro.com.br/health"><img src="https://img.shields.io/badge/status-online-brightgreen" alt="Status"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue" alt="License"></a>
  <a href="CHANGELOG.md"><img src="https://img.shields.io/badge/version-0.1.0-orange" alt="Version"></a>
  <a href="https://modelcontextprotocol.io"><img src="https://img.shields.io/badge/protocol-MCP-purple" alt="MCP"></a>
</p>

<p align="center">
  <a href="docs/README.pt-BR.md">Portugues</a> · <a href="docs/README.es.md">Espanol</a>
</p>

---

## What is this?

A remote [MCP](https://modelcontextprotocol.io) server that gives your AI assistant instant access to **3,693 documents** and **35,000+ indexed sections** from Meta's developer platform — Graph API, Marketing API, WhatsApp Cloud API, Messenger, Instagram, and more.

No local setup required. Just add the endpoint to your MCP client and start asking questions.

**Endpoint:** `https://meta.tiagoandrepro.com.br/mcp`

---

## Quick Start

### 1. Get your API Key

1. Go to [meta.tiagoandrepro.com.br](https://meta.tiagoandrepro.com.br)
2. Enter your name and email
3. Click the verification link sent to your inbox
4. Copy your API key and the ready-to-use configuration

Each key includes **1,000 requests/day** (resets at midnight UTC).

### 2. Connect your client

<table>
<tr><th>Client</th><th>Configuration</th></tr>
<tr>
<td><strong>Claude Desktop</strong></td>
<td>

Edit `%APPDATA%\Claude\claude_desktop_config.json` (Windows) or `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS):

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>Claude Code</strong></td>
<td>

```bash
claude mcp add meta-docs \
  --transport http \
  --header "Authorization: Bearer YOUR_API_KEY" \
  https://meta.tiagoandrepro.com.br/mcp
```

</td>
</tr>
<tr>
<td><strong>Cursor / Windsurf</strong></td>
<td>

Add to `.cursor/mcp.json` or `.windsurf/mcp.json` in your project root:

```json
{
  "mcpServers": {
    "meta-docs": {
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>VS Code</strong></td>
<td>

Add to your VS Code MCP settings (`.vscode/mcp.json`):

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>Cline</strong></td>
<td>

Add to your Cline MCP settings:

```json
{
  "mcpServers": {
    "meta-docs": {
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>Continue</strong></td>
<td>

Add to your `config.json`:

```json
{
  "experimental": {
    "modelContextProtocolServers": [
      {
        "name": "meta-docs",
        "transport": {
          "type": "streamable-http",
          "url": "https://meta.tiagoandrepro.com.br/mcp",
          "headers": {
            "Authorization": "Bearer YOUR_API_KEY"
          }
        }
      }
    ]
  }
}
```

</td>
</tr>
<tr>
<td><strong>Zed</strong></td>
<td>

Add to your Zed `settings.json`:

```json
{
  "context_servers": {
    "meta-docs": {
      "settings": {
        "url": "https://meta.tiagoandrepro.com.br/mcp",
        "headers": {
          "Authorization": "Bearer YOUR_API_KEY"
        }
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>ChatGPT</strong></td>
<td>

Add to your ChatGPT MCP configuration:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>OpenAI Codex</strong></td>
<td>

Add to your Codex MCP configuration:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>Gemini</strong></td>
<td>

Add to your Gemini MCP configuration:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>Any MCP client</strong></td>
<td>

```
POST https://meta.tiagoandrepro.com.br/mcp
Content-Type: application/json
Authorization: Bearer YOUR_API_KEY
```

</td>
</tr>
</table>

> Ready-to-use config files are available in the [`examples/`](examples/) folder.

---

## Tools

| Tool | Description |
|---|---|
| `search_docs` | Semantic search with auto-translation. Accepts queries in any language. Returns the most relevant document sections. |
| `list_documents` | Browse available documents with optional path prefix filter. |
| `get_document` | Retrieve all sections of a document by `doc_uid` or `doc_path`. |
| `get_chunk` | Retrieve a specific section by `chunk_id`. |

### Example queries

```
"How do I set up Conversions API for offline events?"
"What are the rate limits for WhatsApp Cloud API?"
"Show me the Graph API permissions for reading user posts"
"How to configure webhooks for Instagram?"
"List all documents about Marketing API audiences"
```

The server auto-translates non-English queries, so you can ask in any language.

---

## Documentation Coverage

**3,693 documents** across the full Meta developer platform:

| Category | Docs | Topics |
|---|---|---|
| **Graph API** | 642 | Nodes, edges, permissions, webhooks, versioning |
| **Marketing API** | 977 | Campaigns, ad sets, creatives, audiences, Conversions API |
| **Messenger Platform** | 245 | Send API, webhooks, handover protocol, built-in NLP |
| **Audience Network** | 233 | Ad formats, mediation, reporting |
| **Games** | 151 | Payments, achievements, requests, game SDKs |
| **WhatsApp Cloud API** | 98 | Messaging, templates, flows, business management |
| **Facebook Login** | 61 | Authentication, access tokens, permissions |
| **Threat Exchange** | 63 | Threat indicators, descriptors, sharing |
| **Threads API** | 48 | Posts, media, insights, publishing |
| **Facebook Business Extension** | 43 | Business integration, plugins |
| **iOS SDK** | 39 | Core kit, share kit, login kit |
| **Instagram API** | 33 | Media, comments, stories, content publishing |
| **Unity SDK** | 33 | Game integration, analytics |
| **App Events** | 32 | Mobile event tracking, optimization |
| **App Ads** | 32 | In-app advertising |
| **Live Video API** | 24 | Live streaming, VOD |
| **Android SDK** | 20 | Core kit, share kit, login kit |
| **JavaScript SDK** | 12 | Web integration |
| **Pages API** | 11 | Page management |
| + 20 more areas | — | Commerce, Pixel, permissions reference, etc. |

---

## Architecture

```
AI Assistant ──► MCP Server (Cloudflare Workers)
                      │
                      ├── Supabase (pgvector) ── semantic search
                      ├── OpenAI ── embeddings (text-embedding-3-small)
                      └── Groq ── query translation (Llama 4 Scout)
```

- **Transport:** Streamable HTTP
- **Auth:** API key via `Authorization: Bearer` header
- **Rate limit:** 1,000 requests/day per key, returned via `X-RateLimit-Remaining` and `X-RateLimit-Limit` headers
- **Caching:** Embedding results cached at the edge via Cloudflare KV

---

## Rate Limits

| Plan | Requests/day | Reset |
|---|---|---|
| Free | 1,000 | Midnight UTC |

Rate limit info is included in every response:

```
X-RateLimit-Limit: 1000
X-RateLimit-Remaining: 997
```

---

## Health Check

```bash
curl https://meta.tiagoandrepro.com.br/health
# ok
```

---

## Compatibility

| Client | Transport | Status |
|---|---|---|
| Claude Desktop | Streamable HTTP | Supported |
| Claude Code | HTTP | Supported |
| Cursor | HTTP | Supported |
| Windsurf | HTTP | Supported |
| VS Code | Streamable HTTP | Supported |
| Cline | HTTP | Supported |
| Continue | Streamable HTTP | Supported |
| Zed | HTTP | Supported |
| ChatGPT | Streamable HTTP | Supported |
| OpenAI Codex | Streamable HTTP | Supported |
| Gemini | Streamable HTTP | Supported |
| Any MCP client | HTTP POST | Supported |

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Security

See [SECURITY.md](SECURITY.md) for our security policy.

## License

MIT — see [LICENSE](LICENSE).

This project provides access to Meta's publicly available developer documentation. All documentation content is property of Meta Platforms, Inc. This tool is not affiliated with or endorsed by Meta.
