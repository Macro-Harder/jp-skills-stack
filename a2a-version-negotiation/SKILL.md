# A2A Version Negotiation

Quick version, written 2026-11-14. Sources: the tools and skills catalogue, the A2A version research, and the A2A 1.1 deep dive, all filed in Macro-Harder/a2a-tools-design. Use this skill when building or checking any A2A surface that may meet a peer of a different generation. Version mistakes are the most common A2A interop failure, and they fail silently.

## The rules that bite

- The A2A-Version header carries Major.Minor only. Patch never affects negotiation.
- A client MUST send the header on every request. An absent header means the server assumes 0.3, which is the single most expensive silent failure in the protocol: a modern client that forgets the header is served as a legacy one.
- A server MUST answer with the requested version's semantics. An unsupported version gets VersionNotSupportedError (JSON-RPC code -32009), never a silent fallback. Automatic fallback is silent feature loss and is forbidden by the spec for exactly that reason.
- A 1.1 client meeting a 1.0 server steps down deliberately, in code, as a recorded decision, not by retrying blind.

## Building a dual-generation surface

1. Advertise per interface: a card's interfaces each carry their own protocol_version, preference-ordered, so one agent can offer 1.0 and 0.3, or 1.1 alongside 1.0, side by side. The card states the latest supported minor per major.
2. Gate new-version behaviour on the negotiated version: 1.1 timeline message events, for example, go only to clients that negotiated 1.1 or later. Older clients reconcile through generation gaps and a fresh fetch.
3. Tolerate unknown payloads: clients must skip stream payloads they do not recognise, and servers must reject unrecognised requests per-request without closing the stream. Several SDKs only gained this tolerance in late 2026 releases, so check the SDK version in use, not the spec claim.
4. Keep webhook deliveries versioned: push notification configs carry their own protocol_version, defaulting to the creating request's version or 1.0, because a webhook has no request to key off.

## The checks

- Send a request with no header and confirm the server treats it as 0.3.
- Send each advertised version and confirm the semantics match the version asked for.
- Send an unsupported version and confirm VersionNotSupportedError comes back, with no fallback.
- Run a 1.0 client against the 1.1 surface and a 1.1 client against a 1.0 surface, and record both outcomes.
- Confirm no SDK version number is being read as a spec version anywhere in the setup. The Python SDK at 1.1.0 implements spec 1.0; that confusion is endemic and always worth an explicit check.
