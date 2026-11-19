# Arbitration Protocol

## What it is
This is the standing method for settling a disputed evaluation case. A dispute usually sounds simple: the agent failed a case, and someone believes the failure is unfair. Without a method, the argument is settled by whoever edits the suite, argues longest, or needs the release most. This protocol settles it by evidence and by ownership instead.

It runs in seven steps. First the case and the suite are frozen, so evidence cannot shift during the argument, and passing examples cannot be deleted or edited outside a ruling. Second, the run transcript is read alongside the reference solution. Third, the failure is classified into one of five classes: agent, task, grader, environment, or spec-wrong. Fourth, the owner of that class fixes the fault, and any eval fix triggers a fresh baseline run. Fifth, the ruling is written on the case. Sixth, overrides are controlled: only a named person can grant one, in writing, accepting the risk, with an expiry, and the count of live overrides appears on every verdict summary. Renewal after expiry requires authority one level higher than the last grant. Seventh, the eval-wrong ratio is tracked over time.

That last measure matters beyond the single case. If more and more disputes turn out to be faults in the eval itself, the suite is degrading, and fixing the agent will not help.

## Example
An agent fails a case that requires a two part answer. The suite is frozen. The transcript, read beside the reference, shows the agent gave both parts but the grader checked only for an exact string match on the first part. The failure is classified as grader. The grader owner fixes the matching rule and the baseline is re-run to confirm no other case shifted. The ruling is recorded on the case with the class and the fix. No override is needed. The case joins the count for the eval-wrong ratio, which is reported in the verdict summary for that release.

## How to use it
Place the folder in the custom skills directory and adopt the protocol before a release is blocked, while it can still be agreed calmly. A person supplies the disputed case, the run transcript, the reference solution, and the names of the owners for each class. The outputs are the classification, the fix, the ruling on the case, and the updated override count and eval-wrong ratio.

## For agents
An agent must follow the steps in order and must not skip the freeze or the transcript reading to save time. It must classify into exactly one class, refuse informal overrides, and check expiry before honouring any override. Every verdict summary an agent produces carries the override count, and a rising eval-wrong ratio must be flagged as a suite problem, not buried in case level detail.
