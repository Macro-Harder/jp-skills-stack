# Working Loop Start

## What it is
This skill covers the first two steps of an eval driven working loop, the part that happens before any building. It exists because a weak start poisons everything after it: a loose spec lets builders aim at different targets, and a loose eval cannot tell success from failure.

Step 1 is the spec, written for one behaviour at a time. The spec must pass the two expert test, which means two experts reading it separately reach the same understanding of the behaviour and of what success looks like. Every criterion in the spec names its grader, the method that will judge whether that criterion is met. For a change to existing behaviour, the current performance is measured first as a baseline, so the change can be judged against what already exists.

Step 2 builds the evaluation before the product change. Dataset additions and graders are created, then run against the agent exactly as it stands. The expected pattern is strict: new behaviour cases fail, because the agent cannot do the new thing yet, and protected behaviour cases pass, because that behaviour already works and must survive. When the pattern matches, the eval is trusted and building can start.

## Example
A team wants an agent to decline requests that fall outside a defined scope, with a short reason given. The baseline run shows the current agent accepts most such requests. The spec defines scope, the wording shape of the reason, and three criteria, each with a named grader. Two reviewers read the spec separately and disagree on whether a borderline request counts as in scope, so the spec is tightened until they agree. The eval set is built with new decline cases and older accept cases that must stay intact. Run against the unchanged agent, the decline cases fail and the accept cases pass. That pattern confirms the eval. Building begins.

## How to use it
Place the folder in the custom skills directory. A person supplies the behaviour to work on, access to the current agent, and reviewers who can act as the two experts. The outputs are the spec, the baseline record where one applies, the dataset additions, the graders, and the pre-build eval result showing the required pattern.

## For agents
An agent must resist starting the build early, even when the fix looks obvious. It must also treat a passing new case on the unchanged agent as a fault in the eval, and repair the eval rather than explain the result away. Keep the loop to one behaviour, and keep the spec, baseline, and first eval result filed together so later steps can prove what changed.
