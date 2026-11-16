# A2A Card Signing

Quick version, written 2026-11-14. Sources: the tools and skills catalogue (~/workspace/your_files/protocol-tools-and-skills-2026-11-14.md) and the A2A version research filed in Macro-Harder/a2a-tools-design. Use this skill when producing or verifying signed A2A Agent Cards. Card signing is specified in A2A 1.0, is central to trusting a stranger's agent, and is taught by no other skill and covered by no TCK test, so the checks here are manual by necessity. This is the A2A surface closest to the estate's stranger-agent trust work.

## Producing a signed card

1. Build the card JSON exactly as it will be served, then canonicalize it with RFC 8785 (JSON Canonicalization Scheme) before signing. Any byte-level change after canonicalization, including key order and whitespace, invalidates the signature, so canonicalization is the last step before signing, never an approximation of it.
2. Sign with JWS. The signing key is the agent operator's key, held to the same standard as any estate key: generated for this purpose, never shared across agents or purposes, and rotatable without changing the agent's identity claims.
3. Publish the verification key where a stranger can fetch it without asking: the card's own security material and the well-known location for the domain. A signature nobody can verify is decoration.
4. Where the deployment uses authenticated extended cards, the extended card is fetched over an authenticated channel and its contents are held to the same signing discipline; the public card never carries what only authenticated peers may see.

## Verifying a stranger's card

1. Fetch the card, canonicalize the received JSON yourself, and verify the JWS against the published key. Never trust a signature status reported by the serving side.
2. Check the key's provenance: does the key publication point back to the same domain or identity the card claims? A valid signature under an unrelated key proves nothing about the claimed agent.
3. Apply per-skill security requirements: a card may declare different requirements for different skills. A skill that moves value or grants access demands a verified signature; a read-only informational skill may not. Record which requirement was applied and why.
4. Treat an unsigned card, a failed verification, or an unverifiable key as untrusted input: the agent may still be talked to at the lowest trust level, but nothing it claims about itself is believed.

## Failure modes to name in the report

Canonicalization mismatches (the most common), keys published somewhere the card does not point to, signature valid but identity unbound, and extended-card contents leaking into the public card.
