---
name: tool-evaluation-checklist
description: Maps a candidate tool against the twelve primitives of the eval harness before adoption. Load it whenever a tool for eval driven development is proposed.
---

# Tool Evaluation Checklist

This skill distils rule R-139, Tool evaluation checklist, in LEVEL-3-TEAMS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose

Tools for eval driven development vary widely in what they cover. This checklist prevents adoption on partial coverage by mapping a tool against all twelve primitives of the eval harness first. Adoption without the mapping does not proceed.

## Procedure

1. Name the candidate tool and the adoption decision it feeds. The Eval infrastructure owner owns the mapping.
2. Map the tool against each primitive and give one verdict per primitive: provides it natively, partially, by integration, or not at all.
3. P1 behaviour spec.
4. P2 dataset store, one example per line, content hashed.
5. P3 dataset splits as tags on examples, not copies, with the runner enforcing tag access.
6. P4 a runner or harness with pinned model and temperature and a fresh environment per example.
7. P5 trace capture covering model calls, tool calls and arguments, outputs, tokens, cost, latency, final answer, and end state.
8. P6 a scorer registry of named, versioned scorer functions in code, judge, and human families.
9. P7 an append only experiment log.
10. P8 comparison that reports per example improved, regressed, or no detectable difference at this n.
11. P9 a gate as a pipeline exit condition with a documented override path.
12. P10 a judge validation set, human labelled and blind labelled, with the agreement number recorded per judge version.
13. P11 a production feedback loop with a promotion path from trace to dataset example behind a promotion gate.
14. P12 cost and latency accounting per example and per experiment, with caps enforced by the runner.
15. Write the mapping into a tool mapping record in the build record.
16. Cite that record in the adoption decision. No tool is adopted, and no adopted tool is used, without the citation.

## Edge cases

A verdict of partially or by integration must name the gap or the integration. A bare label without that detail is not a mapping.

If a primitive is missing and no integration covers it, say so plainly. The decision can still be made, but it must be made with the gap cited, not hidden.

When a tool version changes in a way that affects a primitive, update the mapping and the citation before further use.
