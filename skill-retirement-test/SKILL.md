---
name: skill-retirement-test
description: Test whether an existing skill still beats the bare model, and keep, revise, or delete it on that evidence. Load on a model upgrade or at a regular skill review.
---

# Skill Retirement Test

This skill is distilled from entry 184 (@garrytan) in the ranked X-posts library, voice-to-prompt-per-post-advanced.md, rewritten from the idea in original words.

## Purpose

Catch skills that have become dead weight. A skill written for an older model costs tokens and steering on every run. If the current model now does the same work alone, keeping the skill makes runs slower and more expensive for no gain.

## Procedure

1. Trigger the test on a model upgrade, and also on a fixed review cadence even without an upgrade.
2. For the skill under review, assemble a fixed set of real tasks that the skill claims to serve. Use tasks drawn from actual use, not tasks invented to flatter the skill.
3. Run each task twice under the same conditions: once with the skill loaded, and once with no skill at all.
4. Compare the two runs on success and on cost per run. Record both measures for every task.
5. Decide by the pattern. Keep the skill where it still wins clearly. Revise it where it wins on some tasks and loses on others, and narrow its trigger to the tasks where it wins. Delete it where it ties or loses, because a tie at a higher cost is a loss.
6. Record the result per skill, with the task set used, the scores, and the decision, so the next review starts from evidence rather than memory.
7. After a revision, retest the narrowed skill on its retained task types before returning it to normal use.

## Edge cases

If the task set is too small to separate the runs, enlarge it before deciding, and mark the result provisional. If a skill serves rare but high risk tasks, include those tasks explicitly, since average performance can hide its real value. This test gates keeping a skill. Creating a new skill uses a different gate, so do not use a retirement pass as approval to create one.
