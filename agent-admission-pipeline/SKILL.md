---
name: agent-admission-pipeline
description: Runs the staged admission process for a new agent, model, or harness version before it earns scoped autonomy. Load it when a candidate is proposed to replace or join an incumbent in live work.
---

# Agent Admission Pipeline

This skill distils rule R-220, Agent admission pipeline, in LEVEL-2-STEPS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose

No candidate takes over work on promise alone. It earns its place stage by stage, each stage judged against the incumbent in the same window, with the same inputs, so the comparison is fair and recorded.

## Procedure

1. Set the depth first. Match the pipeline depth to the tier and to the risk of the behaviours involved. The lowest tier may stop at application. State changing behaviours at higher tiers run the full pipeline.
2. Stage one, Application. Run the candidate on the dev and gate eval sets. Run the incumbent as baseline and control in the same window. Record a paired verdict.
3. Stage two, Shadow shift. Feed the candidate live inputs. Record and score its proposed actions, but execute none of them. Score against the incumbent actions, and on a sample add human judgement.
4. Stage three, Supervised practice. Let the candidate execute. Route every state changing action through a human or senior agent approval flow. Continue until its behaviour record reaches the recorded standard.
5. Stage four, Licence. Grant scoped autonomy behaviour by behaviour. Each behaviour gets its own licence scope. Nothing outside the scope is permitted.
6. Stage five, Re-licensing. Trigger a shortened rerun on a substrate change, a drift alarm, or the fixed cadence. The rerun is application plus a shortened shadow shift.
7. Stage six, Retirement. Before cutover, run the replacement against the full regression record of the incumbent. Name any incumbent strength left uncovered in the cutover record, either as an accepted loss or as cases to build.
8. Handle deadline pressure openly. If a deadline forces admission early, use the override machinery. Name the override and give it an expiry. Never bypass the pipeline in silence.

## Edge cases

- If a stage fails its paired verdict, the candidate does not advance. Record the gap and what would need to change for a rerun.
- If no incumbent exists, state that fact in the record and name the baseline used instead, rather than inventing a comparison.
- If drift appears after licensing, do not wait for the cadence. Trigger re-licensing at once.
- If retirement uncovers a strength with no cover, the cutover cannot proceed silently. The loss must be accepted in writing or turned into new cases first.
