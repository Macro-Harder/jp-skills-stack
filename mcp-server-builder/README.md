# MCP Server Builder

## What it is
This skill is a procedure for designing and building a new MCP server from scratch. MCP, the Model Context Protocol, is the way a client application exposes tools, resources, and prompts to a model so the model can take actions and read data through a defined interface.

A good server is narrow. It starts from one capability an agent needs, then offers the smallest set of tools that covers that capability well. Each tool does one job, has a clear name, takes typed input, and returns structured output. Errors come back as results the model can read and correct, not as failures that stop the session.

The skill also covers the choices that shape a server for its whole life: which transport to use, whether to keep state, how to separate tools from resources, and how to test the server before any real client depends on it. It does not cover auditing a server someone else built, and it does not cover migrating an older server to a newer form of the protocol. Those are separate skills with separate checks.

## Example
Suppose an agent needs to look up orders and add notes to them, and no server for that system exists yet.

The work starts with the job sentence: this server lets an agent find an order and record a note on it. That gives two tools, not one. The first tool, get_order, takes an order identifier and returns the order fields as structured data. The second tool, add_order_note, takes an order identifier and note text, and returns a confirmation with the note identifier.

Because the server will run on the same machine as the client, stdio is the transport, and the server keeps no state between calls. Both tools validate their inputs, and get_order is marked read only. Testing uses the Inspector first, including a call with no identifier and a call with a malformed identifier, then a real client runs a full lookup and note task before the server is treated as done.

## How to use it
Place this folder in the skills directory so an agent can load the SKILL.md file when a new server is needed. A person or agent supplies the job the server must do, the system it connects to, and any limits on what data it may touch. The procedure in SKILL.md then drives the design, build, and test pass in order.

No code template is bundled. The server is written in whatever language and SDK fit the host system, following the tool designs produced in the first steps.

## For agents
An agent using this skill follows the procedure in order and does not skip the hostile input tests. The agent keeps the tool set minimal, refuses to add a general purpose tool as a shortcut, and never returns secrets or out of scope data in a result. When the task is really an audit of an existing server or a migration of one, the agent loads the matching skill instead of this one.
