# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [0.1.0] - 2026-03-12

### Added

- Semantic search across 3,693 Meta developer documents (35,000+ indexed sections)
- Four MCP tools: `search_docs`, `list_documents`, `get_document`, `get_chunk`
- Auto-translation of non-English queries via Groq (Llama 4 Scout)
- Self-service API key registration with email verification
- Daily rate limiting (1,000 requests/day per key)
- Rate limit headers (`X-RateLimit-Remaining`, `X-RateLimit-Limit`)
- Embedding cache via Cloudflare KV
- Health check endpoint (`GET /health`)
- Support for Claude Desktop, Claude Code, Cursor, and Windsurf
- Multi-language documentation (English, Portuguese, Spanish)
