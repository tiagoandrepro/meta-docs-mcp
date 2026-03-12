<p align="center">
  <h1 align="center">Meta Docs MCP</h1>
  <p align="center">Busqueda semantica en toda la documentacion de desarrolladores de Meta — desde cualquier asistente de IA.</p>
</p>

<p align="center">
  <a href="https://meta.tiagoandrepro.com.br/health"><img src="https://img.shields.io/badge/status-online-brightgreen" alt="Estado"></a>
  <a href="../LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue" alt="Licencia"></a>
  <a href="../CHANGELOG.md"><img src="https://img.shields.io/badge/version-0.1.0-orange" alt="Version"></a>
  <a href="https://modelcontextprotocol.io"><img src="https://img.shields.io/badge/protocol-MCP-purple" alt="MCP"></a>
</p>

<p align="center">
  <a href="../README.md">English</a> · <a href="README.pt-BR.md">Portugues</a>
</p>

---

## Que es esto?

Un servidor [MCP](https://modelcontextprotocol.io) remoto que le da a tu asistente de IA acceso instantaneo a **3.693 documentos** y **mas de 35.000 secciones indexadas** de la plataforma de desarrolladores de Meta — Graph API, Marketing API, WhatsApp Cloud API, Messenger, Instagram y mas.

No requiere configuracion local. Solo agrega el endpoint a tu cliente MCP y comienza a hacer preguntas.

**Endpoint:** `https://meta.tiagoandrepro.com.br/mcp`

---

## Inicio Rapido

### 1. Obtener tu API Key

1. Visita [meta.tiagoandrepro.com.br](https://meta.tiagoandrepro.com.br)
2. Ingresa tu nombre y correo electronico
3. Haz clic en el enlace de verificacion enviado a tu correo
4. Copia tu API key y la configuracion lista para usar

Cada clave incluye **1.000 solicitudes/dia** (se reinicia a medianoche UTC).

### 2. Conectar tu cliente

<table>
<tr><th>Cliente</th><th>Configuracion</th></tr>
<tr>
<td><strong>Claude Desktop</strong></td>
<td>

Edita `%APPDATA%\Claude\claude_desktop_config.json` (Windows) o `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS):

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer TU_API_KEY"
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
  --header "Authorization: Bearer TU_API_KEY" \
  https://meta.tiagoandrepro.com.br/mcp
```

</td>
</tr>
<tr>
<td><strong>Cursor / Windsurf</strong></td>
<td>

Agrega al `.cursor/mcp.json` o `.windsurf/mcp.json` en la raiz de tu proyecto:

```json
{
  "mcpServers": {
    "meta-docs": {
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer TU_API_KEY"
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

Agrega a la configuracion MCP de VS Code (`.vscode/mcp.json`):

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer TU_API_KEY"
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

Agrega a la configuracion MCP de Cline:

```json
{
  "mcpServers": {
    "meta-docs": {
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer TU_API_KEY"
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

Agrega a tu `config.json`:

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
            "Authorization": "Bearer TU_API_KEY"
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

Agrega al `settings.json` de Zed:

```json
{
  "context_servers": {
    "meta-docs": {
      "settings": {
        "url": "https://meta.tiagoandrepro.com.br/mcp",
        "headers": {
          "Authorization": "Bearer TU_API_KEY"
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

Agrega a la configuracion MCP de ChatGPT:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer TU_API_KEY"
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

Agrega a la configuracion MCP de Codex:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer TU_API_KEY"
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

Agrega a la configuracion MCP de Gemini:

```json
{
  "mcpServers": {
    "meta-docs": {
      "type": "streamable-http",
      "url": "https://meta.tiagoandrepro.com.br/mcp",
      "headers": {
        "Authorization": "Bearer TU_API_KEY"
      }
    }
  }
}
```

</td>
</tr>
<tr>
<td><strong>Cualquier cliente MCP</strong></td>
<td>

```
POST https://meta.tiagoandrepro.com.br/mcp
Content-Type: application/json
Authorization: Bearer TU_API_KEY
```

</td>
</tr>
</table>

> Archivos de configuracion listos para usar estan disponibles en la carpeta [`examples/`](../examples/).

---

## Herramientas

| Herramienta | Descripcion |
|---|---|
| `search_docs` | Busqueda semantica con traduccion automatica. Acepta consultas en cualquier idioma. Devuelve las secciones mas relevantes. |
| `list_documents` | Explora los documentos disponibles con filtro opcional por prefijo de ruta. |
| `get_document` | Recupera todas las secciones de un documento por `doc_uid` o `doc_path`. |
| `get_chunk` | Recupera una seccion especifica por `chunk_id`. |

### Ejemplos de consultas

```
"Como configuro el Conversions API para eventos offline?"
"Cuales son los limites de rate limit de WhatsApp Cloud API?"
"Muestrame los permisos de Graph API para leer posts de usuarios"
"Como configurar webhooks para Instagram?"
"Lista todos los documentos sobre audiencias de Marketing API"
```

El servidor traduce automaticamente las consultas en otros idiomas, asi que puedes preguntar en cualquier lengua.

---

## Cobertura de Documentacion

**3.693 documentos** de toda la plataforma de desarrolladores de Meta:

| Categoria | Docs | Temas |
|---|---|---|
| **Graph API** | 642 | Nodos, edges, permisos, webhooks, versionado |
| **Marketing API** | 977 | Campanas, ad sets, creativos, audiencias, Conversions API |
| **Messenger Platform** | 245 | Send API, webhooks, handover protocol, NLP integrado |
| **Audience Network** | 233 | Formatos de anuncios, mediacion, reportes |
| **Games** | 151 | Pagos, logros, solicitudes, SDKs de juegos |
| **WhatsApp Cloud API** | 98 | Mensajes, plantillas, flows, gestion empresarial |
| **Facebook Login** | 61 | Autenticacion, access tokens, permisos |
| **Threat Exchange** | 63 | Indicadores de amenazas, descriptores, comparticion |
| **Threads API** | 48 | Posts, media, insights, publicacion |
| **Facebook Business Extension** | 43 | Integracion empresarial, plugins |
| **iOS SDK** | 39 | Core kit, share kit, login kit |
| **Instagram API** | 33 | Media, comentarios, stories, publicacion de contenido |
| **Unity SDK** | 33 | Integracion de juegos, analytics |
| **App Events** | 32 | Seguimiento de eventos moviles, optimizacion |
| **App Ads** | 32 | Publicidad in-app |
| **Live Video API** | 24 | Transmision en vivo, VOD |
| **Android SDK** | 20 | Core kit, share kit, login kit |
| **JavaScript SDK** | 12 | Integracion web |
| **Pages API** | 11 | Gestion de paginas |
| + 20 areas adicionales | — | Commerce, Pixel, referencia de permisos, etc. |

---

## Arquitectura

```
Asistente IA ──► Servidor MCP (Cloudflare Workers)
                      │
                      ├── Supabase (pgvector) ── busqueda semantica
                      ├── OpenAI ── embeddings (text-embedding-3-small)
                      └── Groq ── traduccion de consultas (Llama 4 Scout)
```

- **Transporte:** Streamable HTTP
- **Autenticacion:** API key via header `Authorization: Bearer`
- **Rate limit:** 1.000 solicitudes/dia por clave, retornado via headers `X-RateLimit-Remaining` y `X-RateLimit-Limit`
- **Cache:** Resultados de embeddings cacheados en el edge via Cloudflare KV

---

## Rate Limits

| Plan | Solicitudes/dia | Reset |
|---|---|---|
| Gratuito | 1.000 | Medianoche UTC |

Informacion de rate limit se incluye en cada respuesta:

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

## Compatibilidad

| Cliente | Transporte | Estado |
|---|---|---|
| Claude Desktop | Streamable HTTP | Soportado |
| Claude Code | HTTP | Soportado |
| Cursor | HTTP | Soportado |
| Windsurf | HTTP | Soportado |
| VS Code | Streamable HTTP | Soportado |
| Cline | HTTP | Soportado |
| Continue | Streamable HTTP | Soportado |
| Zed | HTTP | Soportado |
| ChatGPT | Streamable HTTP | Soportado |
| OpenAI Codex | Streamable HTTP | Soportado |
| Gemini | Streamable HTTP | Soportado |
| Cualquier cliente MCP | HTTP POST | Soportado |

---

## Contribuir

Consulta [CONTRIBUTING.md](../CONTRIBUTING.md) para directrices.

## Seguridad

Consulta [SECURITY.md](../SECURITY.md) para nuestra politica de seguridad.

## Licencia

MIT — ver [LICENSE](../LICENSE).

Este proyecto proporciona acceso a la documentacion publica de Meta para desarrolladores. Todo el contenido de la documentacion es propiedad de Meta Platforms, Inc. Esta herramienta no esta afiliada ni respaldada por Meta.
