---
name: context-fork-handoff
description: Choose how to hand work to another agent without losing information in a summary. Load before delegating work that depends on prior context or that splits into parts.
---

# Context Fork Handoff

This skill is distilled from entry 108 (@Alezander9) in the ranked X-posts library, voice-to-prompt-per-post-advanced.md, rewritten from the idea in original words.

## Purpose

Avoid the double loss of summary based handoff, where detail is lost once when the summary is written and again when the receiver rebuilds understanding from it. Pick a handoff shape that fits the dependency structure of the work.

## Procedure

1. Before delegating, map the dependency. Ask what the next worker needs: everything established so far, only selected facts from the record, or nothing from prior work at all.
2. Choose one of three shapes. Fork: the subagent starts as a checkpoint of the current session with full context intact. Use this when the work branches but depends on everything already established. Series with retrieval: work stays in one line and the next worker retrieves what it needs from the record as it goes. Use this when the job is sequential and the record is complete. Fresh parallel: split the job into independent sessions from the start, each with its own clean context. Use this when the parts genuinely do not depend on each other.
3. State the choice and its reason in the delegation itself, so the receiver and any reviewer can see why that shape was picked.
4. For a fork, create the checkpoint at a clean point, with the current goal, decisions, and open items present in context.
5. For series with retrieval, confirm the record is complete and point to exactly where the needed material lives. Do not assume the receiver will find it unaided.
6. For fresh parallel work, write each brief so it stands alone, with no hidden reliance on another part.
7. Compare context growth and cost against the summary route. Forking carries more context and can cost more, so note the tradeoff.
8. If a summary brief is truly enough for a job, say why the loss does not matter in that case, and then use the summary.

## Edge cases

If parts look independent but share a decision, they are not independent: fork or sequence them. If the record is patchy, retrieval will fail silently, so choose a fork instead. If context is already very large, a fork may be impractical: clean and checkpoint first, or split the work so a smaller fork suffices.
