# Tool Evaluation Checklist

## What it is

The Tool Evaluation Checklist is a gate that runs before any tool is adopted for eval driven development. Instead of judging a tool by its demo or feature list, it maps the tool against the twelve primitives a working eval harness needs. If a primitive is missing, the mapping shows it before the team builds on the gap.

The twelve primitives cover the full loop. P1 is a behaviour spec. P2 is a dataset store with one example per line and content hashing. P3 is dataset splits handled as tags on examples rather than copies, with the runner enforcing tag access. P4 is a runner with pinned model and temperature and a fresh environment per example. P5 is trace capture across model calls, tool calls and arguments, outputs, tokens, cost, latency, final answer, and end state. P6 is a scorer registry of named, versioned scorers in code, judge, and human families. P7 is an append only experiment log. P8 is comparison that reports per example whether a run improved, regressed, or showed no detectable difference at this n. P9 is a gate as a pipeline exit condition with a documented override path. P10 is a judge validation set, human labelled and blind labelled, with the agreement number recorded per judge version. P11 is a production feedback loop with a promotion path from trace to dataset example behind a promotion gate. P12 is cost and latency accounting per example and per experiment, with caps enforced by the runner.

For each primitive the mapping gives one of four verdicts: the tool provides it natively, partially, by integration, or not at all. The Eval infrastructure owner owns the mapping, writes it into a tool mapping record in the build record, and the adoption decision must cite that record.

## Example

A team proposes a hosted eval platform. The owner maps it and finds P2, P4, P5, and P7 native, P6 and P8 partial because scorers are named but not versioned and comparison is aggregate only, P3 and P11 by integration with the team dataset store, and P9, P10, and P12 not at all. The adoption decision cites the record and adopts the tool for experiment running only, while gating, judge validation, and cost caps stay in the team runner. Without the mapping, the team would have assumed all four missing pieces were covered.

## How to use it

Supply the tool name, version, and documentation, plus access for hands on checks where a claim is unclear. The owner works through P1 to P12 in order and records a verdict and a short note per primitive. File the mapping as a tool mapping record in the build record. Any adoption decision cites that record.

## For agents

An agent must not recommend adoption before the mapping exists, and must not treat a vendor claim as a verdict without checking it. When an agent uses an adopted tool, it should confirm the adoption citation is present in the build record. If the tool version changes, the agent flags the mapping for review before relying on the changed primitive.
