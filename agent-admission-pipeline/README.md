# Agent Admission Pipeline

## What it is

This skill covers how a new agent, model, or harness version earns a place in live work. Admission is not a single test and it is not a vote of confidence. It is a sequence of six stages, and the candidate must clear each one before it moves to the next.

The stages are application, shadow shift, supervised practice, licence, re-licensing, and retirement of the incumbent. In application the candidate is measured on set evals. In shadow shift it watches live work and proposes actions that are scored but never run. In supervised practice it acts, but a person or a senior agent approves every action that changes state. Only after that record is strong enough does it receive a licence, and the licence is scoped behaviour by behaviour, not granted as a blanket trust.

Admission does not end at licensing. A change in the underlying substrate, a drift alarm, or a set cadence triggers re-licensing through a shorter version of the early stages. When a candidate finally replaces an incumbent, the incumbent leaves through retirement, which checks that the replacement covers the full regression record and names any strength that will be lost.

Depth scales with risk. A low tier candidate for low risk work may need only the application stage. A candidate that will take state changing actions at a higher tier runs the whole pipeline.

## Example

A new model version is proposed for a triage role that can close tickets. It first runs the dev and gate eval sets while the current model runs them as control, and it matches or beats the baseline. It then shadows live triage for a set period: its proposed closures are logged and scored against the actions the incumbent took, with a human reviewing a sample. Next it works supervised, closing tickets only when a senior agent approves each closure. Once its approval record reaches the agreed standard, it is licensed for ticket closure only, not for refunds or account changes, which would need their own licences.

## How to use it

Supply the candidate identity, the incumbent it is compared with, the behaviours in scope, the tier, and the eval sets and regression record to use. The agent running the pipeline files a verdict for each stage before the next stage opens, and keeps the paired results together so the comparison can be checked later.

## For agents

An agent must not advance a candidate on its own impression. Each exit needs the paired, same window comparison and a recorded verdict. If a deadline is used to justify early admission, the agent records the override, names it, and sets its expiry instead of quietly skipping stages.
