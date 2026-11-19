---
name: arbitration-protocol
description: Settle a disputed eval case through a fixed seven step protocol, from freezing the case to recording the ruling and tracking the eval-wrong ratio. Load when an eval result is contested or a release is blocked by a disputed case.
---

# Arbitration Protocol

This skill distils rule R-186, Arbitration protocol, in LEVEL-2-STEPS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose
When an eval case is disputed, teams can drift into editing examples, arguing from memory, or quietly overriding results. This protocol replaces that drift with a fixed order: freeze the evidence, read it properly, classify the fault, fix it at its owner, and record the ruling. It is adopted before the first blocked release, not invented during one.

## Procedure
1. Freeze. Freeze the disputed case and the suite state. From this point, no one deletes or edits a passing example outside a ruling.
2. Transcript first. Read the run transcript with the reference solution beside it. Judge from the record, not from recollection.
3. Classify. Assign the failure to exactly one of five classes: agent, task, grader, environment, or spec-wrong. Pick the class that owns the root cause.
4. Fix at the owner. The owner for that class makes the fix. After any eval fix, re-run the baseline before judging new results.
5. Record the ruling. Write the ruling on the case itself: the class, the fix, and who ruled.
6. Handle overrides by the rule. An override happens only when a named person accepts the risk in writing, with an expiry date. Report the override count on every verdict summary. Renewal after expiry needs authority one level above whoever granted or last renewed it.
7. Track the eval-wrong ratio. Count cases where the eval, not the agent, was at fault, as a share of disputed cases. Review the ratio on each cycle.

## Edge cases
- If a case fits two classes, rule on the root cause and note the second factor in the ruling. Do not split the case into two classes.
- An expired override has no force. A result that relied on it returns to disputed status until it is renewed at the higher authority or resolved on the merits.
- A rising eval-wrong ratio means the suite is the problem, not the agent. Shift effort to fixing the suite and say so in the summary.
- Pressure to release is not a classification. A blocked release stays blocked until a step in this protocol unblocks it.
