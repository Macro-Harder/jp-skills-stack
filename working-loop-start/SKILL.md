---
name: working-loop-start
description: Start an eval driven working loop for one behaviour, writing the spec first and proving the eval fails and passes in the right places before any building. Load at the start of work on a new or changed behaviour.
---

# Working Loop Start

This skill distils rule R-160, Working loop steps 1 and 2, in LEVEL-2-STEPS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose
Work that starts with building tends to bake in a vague target. This skill fixes the target first. Step 1 writes a precise spec for a single behaviour. Step 2 builds the evaluation for that spec and proves the evaluation is sound by running it against the current, unchanged agent. Only a sound eval earns the right to guide the build that follows.

## Procedure
1. Pick one behaviour only. If the request covers several behaviours, split it and take the first one.
2. For an existing behaviour, run the baseline first and record the result. Then spec the change against that baseline.
3. Step 1, spec: write or amend the spec for that one behaviour. State what the behaviour is and what counts as success for each criterion.
4. Apply the two expert test. Have two experts read the spec independently. If they arrive at different readings of the behaviour or of success, rewrite the spec until they agree.
5. Name the grader for every criterion in the spec. A criterion with no named grader is not ready.
6. Step 2, eval first: build the dataset additions and the graders named in the spec. Do not change the agent yet.
7. Run the eval against the current, unchanged agent.
8. Check the pattern. Cases for the new behaviour must fail. Cases for behaviour that must stay intact must pass.
9. If the pattern is wrong, fix the eval or the grader, then re-run. Do not adjust the report to hide a wrong pattern.
10. Begin building only when the eval fails and passes in the right places. Record the spec, the baseline where relevant, and the pre-build eval result together.

## Edge cases
- An eval that passes against the unbuilt or broken version is a wrong eval. Fix the eval, never the report.
- If experts keep disagreeing, the behaviour itself may be split or ill defined. Narrow the behaviour and spec again.
- If intact behaviour cases fail on the current agent, record that as a pre-existing fault. Decide with the owner whether it belongs in this loop or a separate one.
- Do not spec two behaviours to save a cycle. Mixed specs produce mixed evals that cannot show which change worked.
