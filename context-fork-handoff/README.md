# Context Fork Handoff

## What it is

This skill covers how work passes from one agent session to another. The default habit, writing a summary brief for the next worker, loses information twice. The writer leaves things out, often the very details that seemed too obvious to mention, and the reader then rebuilds a mental model from the shortened text, filling gaps with guesses. For work that depends on nuance, that loss causes rework or quiet errors.

Instead, you choose a shape based on how the work depends on what came before. A fork copies the current session at a checkpoint, so the subagent begins with the full context intact. This suits branching work that still rests on everything established. Series with retrieval keeps one line of work, and each next worker pulls what it needs from a complete record as it goes. This suits sequential jobs with good records. Fresh parallel work splits a job into independent sessions from the start, each with clean context and no shared history. This suits parts that truly do not affect each other.

The choice is not free. Forks carry large contexts and cost more. Retrieval depends on record quality. Parallel splits fail if a hidden dependency exists. The skill asks you to name the choice and its reason in the delegation, and to justify any return to a plain summary.

## Example

A design session has settled twenty decisions over a long discussion. Two follow up builds branch from it, one for storage and one for the interface, and both need the full reasoning. Summaries would drop tradeoffs. The lead forks the session twice, so each builder starts with the complete history. By contrast, a weekly report job runs in series: each week the worker retrieves the prior reports from the archive and continues, because the record is complete and only recent entries matter.

## How to use it

Before delegating, supply an honest dependency picture: what is already decided, where the record lives, and whether the parts interact. Then pick the shape, state it in the brief, and set up the checkpoint, the record pointers, or the standalone briefs as the shape requires.

## For agents

An agent must not default to a summary out of habit. Make the shape decision explicitly, write it into the delegation, and check that a retrieval based handoff points to a record that actually exists and is complete.
