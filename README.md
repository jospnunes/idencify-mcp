# Idencify MCP Server

**Whole-repo code intelligence for AI agents, served over [MCP](https://modelcontextprotocol.io).**

AI coding agents are great at the file they're looking at and blind to the other 2,000. [Idencify](https://idencify.com) gives them the whole-repo picture: connect a GitHub repository and it builds a cross-language call graph with semantic search — served through 14 MCP tools to Claude Code, Cursor, and any MCP client.

> This is the public documentation repository for the hosted server at `https://mcp.idencify.com/mcp`. Sign up at [idencify.com](https://idencify.com) — free tier included.

## Quickstart (Claude Code)

```bash
claude mcp add --transport http idencify https://mcp.idencify.com/mcp
```

Authentication is OAuth 2.1 — your MCP client opens the browser, you approve, done. API-key access (REST) is also available from the dashboard.

## Tools

| Tool | What it answers |
|---|---|
| `analyze_impact` | "What breaks if I change this symbol?" — transitive blast radius |
| `expand_call_graph` | Callers/callees N levels deep, cross-file and cross-language |
| `get_definition` | Definition + dependency context for a symbol |
| `get_context` | Assembled, ranked context pack for a task |
| `symbol_search` | Hybrid semantic + keyword + identifier search |
| `find_pattern` | Structural pattern occurrences across the repo |
| `detect_cycles` | Dependency cycles, ranked by severity |
| `check_boundaries` | Architecture boundary violations |
| `health_score` | Repo/module health grade with hotspots |
| `graph_diff` | Exact graph diff between two commits (adds/removes/breaking) |
| `semantic_changelog` | Human-readable changelog from graph changes |
| `search_history` | Query indexed git history |
| `summarize_file` | File summary with symbols and relations |
| `rate_context` | Feedback loop — rate retrieved context to improve ranking |

## Language support

Rust, TypeScript, JavaScript, Python, Go, Java and C++ — all indexed into one unified graph, with enhanced compiler-level precision for Rust, TypeScript, Python and Go. Re-indexing never loses relations: the graph can only get better over time.

## How it works

1. Connect a repository (GitHub App with read-only access, or REST API for public repos).
2. Idencify indexes it into a whole-repo graph: symbols, calls, imports, containment and implementation relations, plus semantic search — updated automatically on every push.
3. Your agent queries the graph over MCP — every answer is backed by the indexed graph, not guesses.

## Links

- Website / signup: **[idencify.com](https://idencify.com)**
- Dashboard: [app.idencify.com](https://app.idencify.com)
- MCP endpoint: `https://mcp.idencify.com/mcp` (Streamable HTTP; SSE at `/mcp/sse`)
- Contact: hello@idencify.com

## Pricing

Free ($0) · Plus ($9/mo) · Pro ($29/mo) — see [idencify.com](https://idencify.com) for limits.
