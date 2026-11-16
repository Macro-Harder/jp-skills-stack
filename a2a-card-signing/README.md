# A2A Card Signing

## What it is
This skill covers producing and verifying signed A2A Agent Cards. Card signing is specified in A2A 1.0 and is central to trusting an agent operated by someone else. The checks in the skill are manual.

For producing a signed card, the skill sets out four steps. Build the card JSON exactly as it will be served, canonicalize it with RFC 8785 before signing, sign with JWS using a dedicated operator key, and publish the verification key where a stranger can fetch it without asking. It also covers authenticated extended cards, which are fetched over an authenticated channel and held to the same signing discipline, with no private contents in the public card.

For verifying a card from another agent, the skill sets out four checks. Fetch the card and canonicalize and verify it yourself, check that the key publication points back to the domain or identity the card claims, apply per skill security requirements, and treat an unsigned card or a failed verification as untrusted input.

The skill names failure modes to report, including canonicalization mismatches, keys published somewhere the card does not point to, a valid signature with identity unbound, and extended card contents leaking into the public card.

## Example
A person wants to connect to an agent run by another operator and needs to know whether its card can be trusted. The agent fetches the card, canonicalizes the received JSON itself, verifies the JWS against the published key, and checks that the key belongs to the claimed domain. If verification fails, the agent reports the card as untrusted and treats the other agent at the lowest trust level.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example when producing or verifying a signed A2A Agent Card. A person can also ask for the work directly in plain words, such as asking to sign a card or to verify a card before trusting it.

To sign a card, the person needs to supply the card contents as they will be served and access to the operator signing key for that agent. To verify a card, the person needs to supply or point to the card to be checked.

## For agents
Agent use is the same as the use described above, with one added duty: the agent never trusts a signature status reported by the serving side, and it records which per skill security requirement was applied and why.
