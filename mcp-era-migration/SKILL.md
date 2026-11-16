# MCP Era Migration

Quick version, written 2026-11-14. Sources: the MCP version research filed in Macro-Harder/mcp-tools-design (research/protocol-versions.md) and the tools and skills catalogue. Use this skill when moving an MCP server from the handshake era (2025-11-25 and earlier) toward the stateless revision (2026-07-28), or when deciding whether a server needs to move at all.

## Decide first

- Local stdio tools can stay on 2025-11-25. The estate's servers are local today, so migration is preparation, not urgency.
- New remote servers target 2026-07-28 and serve dual-era: 2026-07-28 plus 2025-11-25, because today's clients are mixed.
- "Supports 2026-07-28" never means "defaults to it". SDK postures differ: the TypeScript SDK v2 negotiates legacy-first, the Python SDK v2 modern-first, and Go needs Stateless set explicitly. Check the built server's actual negotiation, not its dependency list.

## The migration walk

1. Audit for session assumptions: stored per-connection state, anything read once at initialize time and trusted later, reliance on the session id as identity. The stateless core has no sessions and no initialize handshake, so each of these is a break point.
2. Audit for server-initiated requests: sampling, roots, and logging are deprecated in the new revision. Replace flows that needed them with the multi round-trip request pattern, where the server asks through the response and the client answers on the next call.
3. Move long-running work to the Tasks extension: anything that outlives one request becomes a task with polling, not a held-open call.
4. Set the new routing and cache headers on HTTP transports, and confirm HTTP with SSE and Dynamic Client Registration are not load-bearing: both are formally deprecated under the 12-month deprecation policy.
5. Verify dual-era with the MCP Inspector CLI: run the full tool list and a call per tool against the server negotiated at 2026-07-28, then again pinned to 2025-11-25. Both eras pass before the migration is called done.
6. Record what the server now negotiates by default, per SDK, in the project's records, so the next reader does not have to re-derive it.
