# Harness Cost Tuning

## What it is

This is a method for making an agent harness cheaper to run without quietly making it worse. A harness is everything around the model: how steps are grouped, what stays in context, how tool outputs are stored, and which model handles each kind of work.

The method holds two things fixed, the model and a benchmark set of tasks, so the harness is the only variable. You record a baseline first, with completion, cost, and tokens together. Then you read the logs to find where spend actually concentrates, instead of cutting at random. Each idea is tested alone, against gates you set before seeing results. A run that costs less because it finishes fewer tasks is a failure, not a saving.

Common levers include joining actions that always occur together into one call, removing finished steps from active context, storing large tool outputs outside the context with a short excerpt and a way to fetch the rest, and giving mechanical reading work, such as scanning logs, to a cheaper model. The final check matters most: once tuning on the known set ends, you freeze the harness and test on tasks it has not seen. Only savings that survive that test are real.

## Example

A support agent costs 4.20 dollars per task set and completes 46 of 50 tasks. Logs show that full web pages stay in context long after use. One change is made: pages are archived, and context keeps a short excerpt plus a handle. The rerun completes 47 tasks at 3.10 dollars. The preset gates pass, so the change is kept. A second change, routing summaries to a cheaper model, drops cost to 2.80 dollars but completion falls to 39. That change is discarded.

## How to use it

Supply a fixed task set, access to execution logs, and the current harness configuration. State your quality and cost gates up front. Expect one tested change per cycle and a final holdout run before any saving is reported.

## For agents

An agent must never report cost without completion and tokens alongside it. Do not stack several changes into one test, because then no one can tell which change helped. Keep discarded changes in the record with their results.
