# MCP Era Migration

## What it is
This skill covers moving an MCP server from the handshake era, spec revision 2025-11-25 and earlier, toward the stateless revision dated 2026-07-28, and deciding whether a server needs to move at all.

The decision comes first. Local stdio tools can stay on 2025-11-25. New remote servers target 2026-07-28 and serve both eras, 2026-07-28 plus 2025-11-25, because current clients are mixed. A claim that a server supports 2026-07-28 never means it defaults to that revision, because SDK postures differ, so the built server actual negotiation is checked rather than its dependency list.

The migration walk audits for session assumptions and for server initiated requests, moves long running work to the Tasks extension, sets the new routing and cache headers on HTTP transports, and verifies both eras with the MCP Inspector CLI. The walk closes by recording what the server now negotiates by default, per SDK, in the project records.

## Example
A remote MCP server built on the handshake era needs to prepare for the stateless revision. The skill audits it for stored per connection state, for anything read once at initialize time and trusted later, and for reliance on the session id as identity, since the stateless core has no sessions and no initialize handshake. Flows that used sampling, roots, or logging are replaced with the multi round trip request pattern, and work that outlives one request becomes a task with polling. The server is then tested tool by tool at 2026-07-28 and again pinned to 2025-11-25, and both eras must pass before the migration is called done.

## How to use it
Place the folder in an agent skills library. The agent loads the skill when a request is about moving an MCP server between spec eras or deciding whether it needs to move. A person can also ask for the work directly in plain words, for example by asking whether a local stdio server needs to migrate or by asking for a remote server to be made dual era.

The skill does not name inputs the person must supply beyond the server being assessed or migrated.

## For agents
When this skill loads, decide first whether migration is needed, then work the six step walk in order. Confirm that HTTP with SSE and Dynamic Client Registration are not load bearing, since both are formally deprecated. Verify with the MCP Inspector CLI by running the full tool list and a call per tool in each era, and record the default negotiation per SDK so the next reader does not have to derive it again.
