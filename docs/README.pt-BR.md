<p align="center">
  <h1 align="center">Meta Docs MCP</h1>
  <p align="center">Busca semantica em toda a documentacao de desenvolvedores do Meta — direto do seu assistente de IA.</p>
</p>

<p align="center">
  <a href="https://meta.tiagoandrepro.com.br/health"><img src="https://img.shields.io/badge/status-online-brightgreen" alt="Status"></a>
  <a href="../LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue" alt="Licenca"></a>
  <a href="../CHANGELOG.md"><img src="https://img.shields.io/badge/version-0.1.0-orange" alt="Versao"></a>
  <a href="https://modelcontextprotocol.io"><img src="https://img.shields.io/badge/protocol-MCP-purple" alt="MCP"></a>
</p>

<p align="center">
  <a href="../README.md">English</a> · <a href="README.es.md">Espanol</a>
</p>

---

## O que e isso?

Um servidor [MCP](https://modelcontextprotocol.io) remoto que da ao seu assistente de IA acesso instantaneo a **3.693 documentos** e **mais de 35.000 secoes indexadas** da plataforma de desenvolvedores do Meta — Graph API, Marketing API, WhatsApp Cloud API, Messenger, Instagram e muito mais.

Nenhuma configuracao local necessaria. Basta adicionar o endpoint ao seu cliente MCP e comecar a fazer perguntas.

**Endpoint:** `https://meta.tiagoandrepro.com.br/mcp`

---

## Inicio Rapido

### 1. Obtenha sua API Key

1. Acesse [meta.tiagoandrepro.com.br](https://meta.tiagoandrepro.com.br)
2. Informe seu nome e email
3. Clique no link de verificacao enviado para seu email
4. Copie sua API key e a configuracao pronta para uso

Cada chave inclui **1.000 requisicoes/dia** (reseta a meia-noite UTC).

### 2. Conecte seu cliente

<table>
<tr><th>Cliente</th><th>Configuracao</th></tr>
<tr>
<td><strong>Claude Desktop</strong></td>
<td>

Edite `%APPDATA%\Claude\claude_desktop_config.json` (Windows) ou `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS):

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer SUA_API_KEY"
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
  --header "Authorization: Bearer SUA_API_KEY" \
  https://meta.tiagoandrepro.com.br/mcp
```

</td>
</tr>
<tr>
<td><strong>Cursor / Windsurf</strong></td>
<td>

Adicione ao `.cursor/mcp.json` ou `.windsurf/mcp.json` na raiz do seu projeto:

```json
{
  "mcpServers": {
    "meta-docs": {
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer SUA_API_KEY"
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

Adicione nas configuracoes MCP do VS Code (`.vscode/mcp.json`):

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer SUA_API_KEY"
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

Adicione nas configuracoes MCP do Cline:

```json
{
  "mcpServers": {
    "meta-docs": {
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer SUA_API_KEY"
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

Adicione ao seu `config.json`:

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
            "Authorization": "Bearer SUA_API_KEY"
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

Adicione ao `settings.json` do Zed:

```json
{
  "context_servers": {
    "meta-docs": {
      "settings": {
        "url": "https://meta.tiagoandrepro.com.br/mcp",
        "headers": {
          "Authorization": "Bearer SUA_API_KEY"
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

Adicione na configuracao MCP do ChatGPT:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer SUA_API_KEY"
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

Adicione na configuracao MCP do Codex:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer SUA_API_KEY"
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

Adicione na configuracao MCP do Gemini:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer SUA_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>Qualquer cliente MCP</strong></td>
<td>

```
POST https://meta.tiagoandrepro.com.br/mcp
Content-Type: application/json
Authorization: Bearer SUA_API_KEY
```

</td>
</tr>
</table>

> Arquivos de configuracao prontos para uso estao disponiveis na pasta [`examples/`](../examples/).

---

## Ferramentas

| Ferramenta | Descricao |
|---|---|
| `search_docs` | Busca semantica com traducao automatica. Aceita queries em qualquer idioma. Retorna as secoes mais relevantes. |
| `list_documents` | Navega pelos documentos disponiveis com filtro opcional por prefixo de path. |
| `get_document` | Recupera todas as secoes de um documento por `doc_uid` ou `doc_path`. |
| `get_chunk` | Recupera uma secao especifica por `chunk_id`. |

### Exemplos de consultas

```
"Como configurar o Conversions API para eventos offline?"
"Quais sao os limites de rate limit da WhatsApp Cloud API?"
"Mostra as permissoes do Graph API para ler posts de usuarios"
"Como configurar webhooks para o Instagram?"
"Lista todos os documentos sobre audiencias da Marketing API"
```

O servidor traduz automaticamente queries em outros idiomas, entao voce pode perguntar em qualquer lingua.

---

## Cobertura da Documentacao

**3.693 documentos** de toda a plataforma de desenvolvedores do Meta:

| Categoria | Docs | Topicos |
|---|---|---|
| **Graph API** | 642 | Nodes, edges, permissoes, webhooks, versionamento |
| **Marketing API** | 977 | Campanhas, ad sets, criativos, audiencias, Conversions API |
| **Messenger Platform** | 245 | Send API, webhooks, handover protocol, NLP integrado |
| **Audience Network** | 233 | Formatos de anuncio, mediacao, relatorios |
| **Games** | 151 | Pagamentos, conquistas, requests, SDKs de jogos |
| **WhatsApp Cloud API** | 98 | Mensagens, templates, flows, gerenciamento de negocios |
| **Facebook Login** | 61 | Autenticacao, access tokens, permissoes |
| **Threat Exchange** | 63 | Indicadores de ameacas, descritores, compartilhamento |
| **Threads API** | 48 | Posts, midia, insights, publicacao |
| **Facebook Business Extension** | 43 | Integracao empresarial, plugins |
| **iOS SDK** | 39 | Core kit, share kit, login kit |
| **Instagram API** | 33 | Midia, comentarios, stories, publicacao de conteudo |
| **Unity SDK** | 33 | Integracao de jogos, analytics |
| **App Events** | 32 | Rastreamento de eventos mobile, otimizacao |
| **App Ads** | 32 | Publicidade in-app |
| **Live Video API** | 24 | Transmissao ao vivo, VOD |
| **Android SDK** | 20 | Core kit, share kit, login kit |
| **JavaScript SDK** | 12 | Integracao web |
| **Pages API** | 11 | Gerenciamento de paginas |
| + 20 areas adicionais | — | Commerce, Pixel, referencia de permissoes, etc. |

---

## Arquitetura

```
Assistente IA ──► Servidor MCP (Cloudflare Workers)
                      │
                      ├── Supabase (pgvector) ── busca semantica
                      ├── OpenAI ── embeddings (text-embedding-3-small)
                      └── Groq ── traducao de queries (Llama 4 Scout)
```

- **Transporte:** Streamable HTTP
- **Autenticacao:** API key via header `Authorization: Bearer`
- **Rate limit:** 1.000 requisicoes/dia por chave, retornado via headers `X-RateLimit-Remaining` e `X-RateLimit-Limit`
- **Cache:** Resultados de embeddings cacheados na edge via Cloudflare KV

---

## Rate Limits

| Plano | Requisicoes/dia | Reset |
|---|---|---|
| Gratuito | 1.000 | Meia-noite UTC |

Informacoes de rate limit sao incluidas em cada resposta:

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

## Compatibilidade

| Cliente | Transporte | Status |
|---|---|---|
| Claude Desktop | Streamable HTTP | Suportado |
| Claude Code | HTTP | Suportado |
| Cursor | HTTP | Suportado |
| Windsurf | HTTP | Suportado |
| VS Code | Streamable HTTP | Suportado |
| Cline | HTTP | Suportado |
| Continue | Streamable HTTP | Suportado |
| Zed | HTTP | Suportado |
| ChatGPT | Streamable HTTP | Suportado |
| OpenAI Codex | Streamable HTTP | Suportado |
| Gemini | Streamable HTTP | Suportado |
| Qualquer cliente MCP | HTTP POST | Suportado |

---

## Contribuindo

Veja [CONTRIBUTING.md](../CONTRIBUTING.md) para diretrizes.

## Seguranca

Veja [SECURITY.md](../SECURITY.md) para nossa politica de seguranca.

## Licenca

MIT — veja [LICENSE](../LICENSE).

Este projeto fornece acesso a documentacao publica do Meta para desenvolvedores. Todo o conteudo da documentacao e propriedade da Meta Platforms, Inc. Esta ferramenta nao e afiliada nem endossada pelo Meta.
