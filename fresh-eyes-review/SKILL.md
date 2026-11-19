---
name: fresh-eyes-review
description: Review finished work with a fresh agent that has no history in building it, so defects hidden by builder memory surface. Load for large work and always for the final review before calling work done.
---

# Fresh Eyes Review

This skill is distilled from entry 193 (@AnnatarXBT) in the ranked X-posts library, voice-to-prompt-per-post-advanced.md, rewritten from the idea in original words.

## Purpose

Correct for builder blindness. The session that built a thing remembers the spec, the rejected approaches, and every decision, and it reads the work through that history. A reviewer without that history reads only what is actually there.

## Procedure

1. Keep the two roles separate. The builder works in one long session that retains the spec, the rejected approaches, and the decisions, and builds with that memory.
2. When the work is ready for review, select a reviewer with no history in the work at all. Do not use a session that took part in any stage of building it.
3. Give the reviewer only two things: the finished diff or artefact, and the stated requirements. Give nothing else.
4. Do not brief the reviewer, summarise the work for it, explain choices in advance, or answer its likely findings before it reports. Let it review as a stranger.
5. Collect the findings unfiltered. Do not soften, reorder to hide severity, or attach builder commentary before the findings are recorded.
6. Answer each finding on its merits. Fix it, or reject it with a reason that stands on the work and the requirements alone, never on what the builder remembers or intended.
7. After fixes, return the changed parts to a fresh reviewer again if the changes are substantial.
8. Use this split whenever work is large enough that its own history could hide a defect, and always for the final review before a thing is called done.

## Edge cases

If requirements are unclear to the reviewer, that is itself a finding about the requirements, so record it rather than coaching the reviewer privately. If no fully fresh agent is available, use the least involved agent and note the compromise in the record. Small, trivial changes may not need the full split, but the final review of a substantial piece always does.
