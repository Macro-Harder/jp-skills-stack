---
name: document-checking
description: Check a brief, plan, or specification as a document in two separate passes, verification and validation, each with its own record. Load when a specification artefact needs checking, or when a stage opens on a brief or plan.
---

# Document Checking

This skill distils rule R-59, Document checking, in LEVEL-2-STEPS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose
A specification can fail in two different ways. It can be badly written, so readers cannot tell what it requires. Or it can be well written but say the wrong thing, drifting from the decisions it was meant to carry. This skill checks both faults separately, so a document that passes one test is not mistaken for passing the other.

## Procedure
1. Identify the document, its version, and the decisions register it derives from. If there is no register to trace to, record that gap before starting.
2. Run pass one, verification. Go statement by statement. For each statement ask: is it well formed, unambiguous, internally consistent with the rest of the document, and checkable by some concrete means.
3. Record pass one on its own record. List every defect with the statement, the pass name, and what is wrong.
4. Run pass two, validation. Go statement by statement again. For each statement ask: does it express the need or decision it came from, as shown in the decisions register.
5. Record pass two on its own separate record, in the same defect format. Do not merge the two records.
6. State the outcome of each pass only in its own record. A pass in verification says nothing about validation, and the reverse also holds.
7. Return defects to the author for correction. Re-check corrected statements in the pass that flagged them, and also in the other pass if the wording changed.
8. When a stage opens on a brief or plan, use this check to name the paired verifying activity for that stage, its level, and the evidence it will produce. Record all three before work proceeds.

## Edge cases
- If a statement has no source decision to trace to, that is a validation defect, not a reason to skip the statement.
- If wording is clear but contradicts another statement, that is a verification defect under internal consistency.
- Do not combine the passes to save time. Merged records hide which kind of fault remains.
- A document with zero defects in one pass and defects in the other is not approved. It is approved only when both records support it.
