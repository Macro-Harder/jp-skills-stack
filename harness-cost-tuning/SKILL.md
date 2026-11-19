---
name: harness-cost-tuning
description: Tune an agent harness for lower cost using its own execution logs while holding the model and benchmark fixed. Load when reducing run cost without hiding a drop in completion.
---

# Harness Cost Tuning

This skill is distilled from entry 45 (@AnnatarXBT) in the ranked X-posts library, voice-to-prompt-per-post-advanced.md, rewritten from the idea in original words.

## Purpose

Cut harness cost with evidence. Keep the model and the task set fixed so any change in result can be credited to the harness alone, and judge cost together with completion and tokens, never on cost alone.

## Procedure

1. Choose a fixed set of tasks that represents real work. Freeze the set, the model, and the scoring method before tuning starts.
2. Run the set on the current harness and record the baseline: completion, total cost, and tokens for each task and in total.
3. Read the execution logs and name where the money actually went. Group spend by cause, such as repeated steps, oversized context, large tool outputs kept in full, or expensive models doing mechanical reading.
4. Set keep and discard gates in advance, covering both quality and cost. Write the gates down before testing any change.
5. Propose exactly one harness change at a time. Candidate changes include fusing actions that always travel together, compacting finished steps out of the context, archiving huge tool outputs behind a handle plus a short excerpt that can be expanded on demand, and sending log reading and other mechanical reading to a cheaper model.
6. Run the full fixed set with that single change. Compare completion, cost, and tokens against the baseline as one result.
7. Keep the change only if it passes the preset gates. Discard it if completion falls, even when cost falls with it.
8. Repeat with the next single change, building on kept changes only.
9. When the fixed set stops yielding gains, freeze the harness and retest on unseen tasks. Call the saving real only if it holds there.

## Edge cases

If logs are incomplete, fix logging first, because tuning without a breakdown is guessing. If a change helps one task type and hurts another, record the split and do not average it away. If cost falls only because tasks end early, treat that as failure, not saving.
