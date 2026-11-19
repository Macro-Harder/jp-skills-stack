---
name: mcp-server-builder
description: Build a new MCP server from scratch, from tool design through transport choice and live testing. Load when starting a server that does not exist yet.
---

# MCP Server Builder

## Purpose
This skill covers building a new Model Context Protocol server that gives an agent a clear, bounded capability. It is for green field work only. Auditing an existing server before it is trusted belongs to the mcp-server-security-review skill. Moving an existing server to the newer stateless specification belongs to the mcp-era-migration skill.

## Procedure
1. Start from the job. Write one sentence for the capability the server gives an agent, then list the smallest set of tools that covers that job. Give each tool one job. Do not build a single tool that does everything.
2. Choose the transport. Use stdio when the client starts the server locally on the same machine. Use streamable HTTP when the server is shared, remote, or run by more than one client.
3. Decide state early. Prefer a stateless server that keeps nothing between calls. If state is unavoidable, write down exactly what is kept, where it lives, and how long it is retained, then build to that limit.
4. Design each tool. Pick a name that states the action in plain words. Define a typed input schema with JSON Schema and keep required fields few. Return structured output that a model can parse without guessing. Return errors as readable tool results the model can act on, not as crashes or stack traces. Mark read only tools as read only where the protocol supports annotations.
5. Add resources for data an agent reads rather than changes. Give each resource a stable URI that will not shift between sessions. Add prompts only for genuine user driven workflows. Do not hide instructions inside prompts.
6. Validate every input at the boundary. Reject missing, malformed, or out of range values with a clear error result. Never place secrets, tokens, credentials, or file contents outside the server scope in any tool result, error, or log line.
7. Test before shipping. Connect with the MCP Inspector, list the tools, and call each tool three ways: with a good input, with a required input missing, and with a hostile input. Read the raw results each time.
8. Connect a real client and run one real task end to end using only the new server. Fix what the real run exposes, then repeat the Inspector pass.

## Edge cases
- If two tools would overlap, merge them or split the job more cleanly. Overlap confuses tool choice.
- If a tool needs a secret to do its work, keep the secret on the server side and never echo it back.
- If a caller asks for data outside the stated scope, refuse in the tool result and say what scope is allowed.
- Never ship a server that was only tested with good inputs.
- Never add a catch all tool to save design time.
- Never return raw exceptions to the client.
