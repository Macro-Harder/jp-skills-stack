# MCP Server Security Review

Quick version, written 2026-11-14. Sources: the protocol tools and skills catalogue (~/workspace/your_files/protocol-tools-and-skills-2026-11-14.md) and the MCP version research filed in Macro-Harder/mcp-tools-design. Use this skill to audit an MCP server before it is trusted, and again whenever its tools, transport, or auth change. The estate runs MCP servers inside AgenC, so this review is a standing gate for them, not a one-off.

## The review

1. Tool annotations, checked against behaviour: a tool marked read-only must not write, delete, or send anything. A tool marked destructive must actually be gated the way its annotation promises. Read the implementation, not the description: an annotation is a claim, and the code is the evidence.
2. Tool surface: every tool's description and schema is part of the attack surface, because a model reads them as instructions. Flag descriptions that smuggle directives, tools whose parameters accept unbounded paths, URLs, or commands, and outputs that echo secrets or full file contents the caller did not need.
3. Auth on remote servers: the server acts as an OAuth resource server, publishes protected resource metadata, and validates that tokens were issued for its own audience (RFC 8707 resource indicators). A token minted for another server must be rejected, and the review proves it with a wrong-audience token, not by reading the config.
4. Elicitation and sampling: secrets never pass through the client in form-mode elicitation. If the server asks the user for sensitive input, it does so out of band or not at all. Server-initiated sampling requests are bounded: the server cannot use them to make the client spend unbounded tokens or to exfiltrate context the user did not offer.
5. Filesystem and process reach: a local stdio server runs with the user's full privileges. List exactly which directories, commands, and network endpoints the server can touch, and check that list against what its tools need. Anything reachable but unneeded is a finding.
6. Hostile-input pass: exercise every tool with the MCP Inspector CLI using hostile inputs: path traversal, oversized payloads, malformed JSON, injection strings in every text field. Record what each tool did. A tool that fails open is a finding.
7. Version discipline: note the spec revision and SDK version the server runs, and whether either has known fixed vulnerabilities (the Inspector's own history, CVE-2025-49596 fixed in 0.14.1, is the standing example of why this matters). An unpinned or stale dependency is a finding.

## Verdict

Pass, or fail with findings listed by severity, each naming the tool or surface and the evidence. The review record goes in the owning project's private design repo. A server that fails does not get connected to AgenC until the findings are fixed and the failed checks re-run.
