# MCP Server Security Review

## What it is
This skill audits an MCP server before it is trusted, and again whenever its tools, transport, or auth change. For servers that run inside AgenC, the review is a standing gate, not a one off.

The review has seven parts. Tool annotations are checked against behaviour by reading the implementation, since an annotation is a claim and the code is the evidence. The tool surface is checked, because every tool description and schema is part of the attack surface. Auth on remote servers is checked as an OAuth resource server, including protected resource metadata and audience validation, proved with a wrong audience token rather than by reading config. Elicitation and sampling are checked so secrets never pass through the client in form mode elicitation and sampling stays bounded. Filesystem and process reach is listed exactly and checked against what the tools need. Every tool is exercised with the MCP Inspector CLI using hostile inputs. Version discipline is noted, including the spec revision, the SDK version, and any known fixed vulnerabilities.

The verdict is pass, or fail with findings listed by severity, each naming the tool or surface and the evidence. The review record goes in the owning project private design repo. A server that fails does not get connected to AgenC until the findings are fixed and the failed checks are re run.

## Example
A new MCP server is proposed for connection. The review reads each tool implementation and finds a tool marked read only that can also write, flags a parameter that accepts unbounded paths, and tests auth with a token minted for another server to confirm it is rejected. Each tool is then run through the MCP Inspector CLI with path traversal, oversized payloads, malformed JSON, and injection strings in every text field. The verdict lists each finding by severity with its evidence, and the server stays unconnected until the findings are fixed and re checked.

## How to use it
Place the folder in an agent skills library. The agent loads the skill when a request is to audit an MCP server before it is trusted, or when its tools, transport, or auth have changed. A person can also ask for the review directly in plain words, for example by asking for a security review of a named server before it is connected.

The skill does not name inputs the person must supply beyond the server to be reviewed.

## For agents
Agent use is the same review described above, carried out in the seven parts in order. Record what each tool did under hostile input, name the evidence for each finding, and place the review record in the owning project private design repo.
