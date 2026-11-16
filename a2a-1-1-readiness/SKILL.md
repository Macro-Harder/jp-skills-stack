# A2A 1.1 Readiness

Quick version, written 2026-11-14. Sources: the A2A 1.1 deep dive (Macro-Harder/a2a-tools-design, research/a2a-1.1-deep-dive.md) and the tools and skills catalogue. This is a watching brief with a prototype recipe, not a build guide. Use it when 1.1 comes up in design or planning.

## Standing position

Production stays on A2A 1.0 or 1.0.1 with current SDKs. Spec 1.1 exists only as a release candidate (v1.1.0-rc, tagged 29 October 2026), with no release notes, no changelog entry, and no published date or criteria for a final release. No official SDK implements spec 1.1. Nothing ships on 1.1 by default.

## What 1.1 adds, when it lands

- SendLiveMessage: two-way streaming on a single task, with per-request StreamError rejections that leave the stream open. Needed for mid-task steering, continuous interleaved media, and multi-party live collaboration. Not needed for delegate-and-report work, long-running jobs, or turn-based flows, which 1.0 already covers.
- A task timeline with generation counters: optimistic concurrency on sends, resumable subscriptions from a last-seen generation, and the old history field deprecated in its favour.
- Client-written artifacts, gated by a user_artifacts capability, riding inside send-message requests.
- The agent card media type application/a2a-agent-card+json, and discovery guidance that prefers an AI Catalog at /.well-known/ai-catalog.json, which can show each caller only the agents they may see.

## Known churn and gaps

- An open PR is still revising the RC's live and artifact semantics, including the resume behaviour and artifact identity, so prototype code should expect wire changes.
- The spec has no dedicated security section for two-way streaming or client-written artifacts. Treat client artifacts as untrusted uploads in any prototype.
- The media model debated during the RC's formation was not standardised: live audio conventions are still an open issue, so media semantics are application-defined for now.

## Prototype recipe, when there is a reason

Build against the RC only where both ends are controlled, behind explicit version negotiation (see the a2a-version-negotiation skill), isolated from anything production depends on, with the expectation written down that the wire will move before final release.

## The watch list

Re-check these before repeating any claim about 1.1 status: new tags on the A2A spec repo, a changelog entry for 1.1, the state of the semantics-revision PR, and SDK release notes for first spec 1.1 support. Until a final tag and an SDK land together, the standing position above does not change.
