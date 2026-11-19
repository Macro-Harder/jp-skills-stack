---
name: pattern-skip-test
description: Screens a pattern proposal through six required fields before it is allowed to reach its gate. Load it when a pattern is first proposed and a quick, complete skip or pass decision is needed.
---

# Pattern Skip Test

This skill distils rule R-226, Pattern skip test, in LEVEL-2-STEPS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose

Many patterns solve a real problem at a cost larger than the problem. This test forces a proposal to answer the basic questions in full before it consumes gate time. A proposal that cannot answer them is skipped for now, with a clear path back.

## Procedure

1. Field one: state the problem in one sentence, with a metric.
2. Field two: name a cheaper fix that was tried, such as an index, a bigger instance, a replica, a cache, or a module boundary, as applicable. A recorded search showing no cheaper alternative exists satisfies this field.
3. Field three: name the owning team.
4. Field four: list the new failure modes the pattern brings. Each one must be rehearsable.
5. Field five: write down the consistency consequence.
6. Field six: give an exit or reversal path, or a revisit trigger.
7. Judge the six fields as a whole. Any field answered no means skip for now.
8. Record the skip with its reason and its return trigger. Do not let an incomplete proposal proceed to adoption.
9. Check the wider concerns inside these fields only. Complexity budget, team size, measured load, per operation consistency, and reversibility are covered within the six fields. There is no second checklist.

## Edge cases

- A recorded search that finds no cheaper alternative is a pass on field two, not a failure. Record the search so it can be checked.
- Approved with concerns is not an available outcome. The result is pass to the gate, or skip for now.
- If a failure mode cannot be rehearsed, field four is not complete, so the proposal is skipped until it can be.
- A skip is not a permanent rejection. When the return trigger fires, the proposal may be tested again on a fresh record.
