---
name: failed-node-retry
description: Run a multi agent job as a graph so only the failed node is retried instead of the whole job. Load when planning or debugging work split across several agents or steps.
---

# Failed Node Retry

This skill is distilled from entry 160 (@0xkvro) in the ranked X-posts library, voice-to-prompt-per-post-advanced.md, rewritten from the idea in original words.

## Purpose

Treat failure as a property of one node, not of the whole job. Structure multi agent work as a graph so a failure can be located, retried in isolation, and recorded where it happened.

## Procedure

1. Before running anything, draw the job as a graph. Each node names an explicit owner, its tooling, its inputs, and the check that verifies its output.
2. Set a retry cap for each node, or one cap for the graph, and write it into the graph before the run starts.
3. Run the graph and mark each node pass or fail on its own check. Do not collapse the result into a single job level verdict.
4. On failure, retry only the failed node. Reduce its context to what that node needs: its inputs, its spec, and the failure evidence. Never rerun the whole batch for one node.
5. Keep downstream nodes paused until the retried node passes its check, then release them with the corrected output.
6. Where production data exists, verify the retried node against production data, not only against test fixtures.
7. Record the failure in the graph itself: which node failed, how many retries it took, and what changed between attempts.
8. If a node reaches the retry cap, stop retrying and escalate it as a finding about that node, its spec, or its owner. Report what the repeated failure suggests.

## Edge cases

If two nodes fail for a shared cause, such as a bad upstream input, fix the shared cause once and note it on both nodes, rather than retrying each blindly. If a node has no clear check, write one before running, because an unverifiable node cannot be marked pass or fail honestly. If a retry changes shared state, warn downstream owners before release.
