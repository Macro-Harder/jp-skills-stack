---
name: pattern-gate
description: Governs adopting or removing a design pattern at a design step as a formal gate held by the Auditor. Load it when a pattern change is proposed during design and a Go, Hold, or Recycle outcome is needed.
---

# Pattern Gate

This skill distils rule R-223, Pattern gate at the design steps, in LEVEL-2-STEPS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose

A pattern shapes cost, failure, and future change long after the step that chose it. Treating adoption or removal as a casual preference hides that cost. This gate makes the choice a recorded event with evidence, an owner, and a way out.

## Procedure

1. Open a gate record before any outcome is discussed. The Auditor holds the gate.
2. State the problem as a measured or observed fact. A preference is not a problem statement.
3. Name the owner: a team on the build roster that accepts the failure modes of the pattern.
4. Assign the exit class, one of bypassable, refactorable in place, migration to exit, or programme to exit, and record the basis for that class.
5. Write the sunset condition. It must be a condition, not a date alone.
6. Write the consistency consequence. State which per operation contracts the adoption strengthens, weakens, or leaves alone.
7. Record the cheaper alternative that was tried, or the reason none exists, with the trial itself recorded.
8. Name who checked the evidence, and record the complexity charge with the account route taken.
9. Scale the evidence to the exit class. The lowest class needs a named problem and owner. The highest class needs measured evidence, an incremental path, a containment plan, and a rehearsal.
10. Decide only on a complete record. No Go is recorded before the record is complete. On an incomplete record the only outcomes are Hold or Recycle, and the outcome names the missing fields.
11. File the record as decided. Never edit it after the outcome. Corrections are new entries that supersede the old one.

## Edge cases

- If a field cannot be filled, do not soften the outcome. Record Hold or Recycle and list exactly what is missing.
- If the exit class is disputed, resolve the class first, because it sets the evidence required.
- If a correction is needed after filing, add a superseding entry and leave the original intact for the trace.
- Removal of a pattern goes through the same gate as adoption, with the same record fields.
