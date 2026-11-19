# Skill Retirement Test

## What it is

Skills and harness rules are written against the model of their day. They encode workarounds, extra steps, and steering that the model once needed. As models improve, some of that scaffolding becomes unnecessary. The skill still loads on every run, still spends tokens, and still steers behaviour, but the bare model now handles the task just as well alone. At that point the skill is dead weight, and it can even hurt, by forcing an older pattern over a better native one.

This test settles the question with runs, not opinions. You take real tasks the skill claims to serve, run each one with the skill and without it under identical conditions, and compare success and cost. The decision rule is strict. Keep only clear wins. Revise mixed results by narrowing the skill to the task types where it helps. Delete ties and losses, because equal quality at higher cost is a loss in practice.

Reviews happen on model upgrades and on a regular cadence between upgrades, and each result is recorded with its task set, so later reviews can see whether a skill is gaining or fading over time.

## Example

A formatting skill written for an older model is tested on twenty real documents. With the skill, nineteen succeed at an average cost of 0.31 dollars. Without it, nineteen also succeed at 0.22 dollars. That is a tie on quality and a loss on cost, so the skill is deleted. Another skill, for handling malformed data files, wins on four of six task types and loses on two. It is revised, and its trigger is narrowed to the four winning types.

## How to use it

Supply the skill under review and a set of real tasks it claims to serve, with a way to judge success. Run both conditions, record the comparison, and file the decision with the evidence. Schedule the next review at the same time.

## For agents

An agent must run the bare model condition honestly, with no hidden help from the skill text. Do not defend a familiar skill against the data. Report ties as losses, and keep the per task record, not only the final verdict.
