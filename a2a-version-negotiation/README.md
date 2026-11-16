# A2A Version Negotiation

## What it is
This skill covers version negotiation for A2A surfaces that may meet a peer of a different generation. It explains the rules that cause silent interop failures and how to build and check a dual generation surface.

The core rules are that the A2A-Version header carries Major and Minor only, a client must send the header on every request, and an absent header means the server assumes version 0.3. A server must answer with the requested version semantics. An unsupported version returns VersionNotSupportedError with JSON-RPC code -32009, with no silent fallback. A newer client meeting an older server steps down deliberately in code as a recorded decision.

For building, the skill covers advertising a protocol version per interface in preference order, gating new version behaviour on the negotiated version, tolerating unknown payloads without closing the stream, and keeping webhook deliveries versioned because a webhook has no request to key off.

For checking, it lists tests such as sending a request with no header, sending each advertised version, sending an unsupported version, running clients and servers of different generations against each other, and confirming that no SDK version number is being read as a spec version.

## Example
A client built for A2A 1.0 talks to a server but receives legacy behaviour. The skill points to the most common cause: the client did not send the A2A-Version header, so the server treated it as version 0.3. The fix is to send the header on every request and to record any deliberate step down when versions differ.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example when building or checking an A2A surface. A person can also ask for the work directly in plain words, such as asking to check version handling between a 1.0 client and a 1.1 surface.

The person needs to point to the surface, client, or server to be built or checked, and to the versions it is expected to support. The skill itself does not require other inputs.

## For agents
Agent use is the same as the use described above. When the skill loads, the agent applies the header and error rules, follows the dual generation building steps where relevant, and runs the listed checks and records both outcomes for cross generation tests.
