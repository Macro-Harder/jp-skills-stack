---
name: judge-validation
description: Validates whether an automated judge can be trusted to grade outputs against human labels. Load it before admitting a judge and whenever a judge, rubric, or task changes.
---

# Judge Validation

This skill distils rule R-122, Judge validation protocol, in LEVEL-3-TEAMS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose

An automated judge is useful only if its grades track human judgement on the same task. This protocol tests that tracking in the open, with blind labels, computed agreement, and a bias check, before the judge is trusted and on a regular cycle after.

## Procedure

1. Run blind human labelling. Humans label a sample without seeing any judge output. Where two or more humans label the same items, record their agreement. That agreement is the realistic ceiling for any judge on this task. Do not proceed to admission without that ceiling on record.
2. Run blind judging. The judge grades the same sample without provenance. It must not know which system produced which output.
3. Compute the comparison by code. Report Cohen kappa and per class agreement between judge and human labels, plus judge recall on the fail class.
4. For pairwise judges, run a position bias swap test. Run both orders. Accept only a verdict that survives the swap. Record the other outcome as a tie.
5. Review every disagreement. Classify each one as rubric ambiguity, judge error, or human error.
6. Iterate the rubric on a fresh sample. Never tune the judge prompt to one individual grader.
7. Revalidate monthly, and immediately on any change to the judge model, the rubric, or the task family.
8. If kappa falls below 0.6, suspect the spec or the rubric wording first, not the size of the judge.

## Edge cases

If human agreement is low, the ceiling is low. Fix the rubric or the task definition before blaming the judge.

If fail class recall is weak while overall agreement looks fine, the judge is still not safe for gating. Missed failures matter more than average agreement.

If swap test ties are frequent, treat the pair as too close to call by this judge and route those cases to human review.
