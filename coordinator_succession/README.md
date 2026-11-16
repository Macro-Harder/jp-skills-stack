# Coordinator Succession and Handover

## What it is
This skill covers handing over a multi agent build between coordinators without a silent stop, a depth trapped successor, or an unverified claim, so work resumes from verified records at the next wave or step.

It has four parts. First, checkpoint before any ending: after every wave, append a checkpoint to the build handover or path ledger before doing anything else, write the verified state, what finished, what did not finish, and the exact next action, push and verify the push where a push is part of the record, and mark the top of the handover SUCCESSOR NEEDED when a tour ends.

Second, seat the successor at the right depth: every successor is seated directly from the Manager level, never through the outgoing coordinator and never by the outgoing coordinator spawning its own successor. A coordinator seated one level deeper is treated as holding no spawn capability until that capability is proven. Spawn capability is checked before staffing work is assigned, and the block is recorded rather than staffing short or merging seats. The successor is briefed from the build own records, not from the outgoing coordinator summary alone.

Third, verify claims before passing them on: check a coordinator claim about work in progress against the build own record, confirm spun up agents from runtime agent records and match agent IDs seat for seat against the roster, confirm papers and outputs on disk by count, size, and spot checks, and correct a report openly when the record contradicts it.

Fourth, recover a silent stop without dressing it up: a coordinator that ended without a successor, without a flag, and without starting its recorded next action is treated as a silent stop and named as such. Recovery starts from the last verified checkpoint, seats a fresh coordinator at the Manager level on the recorded next action first, and restates the checkpoint and flag orders in its brief. Where no correctly seated coordinator is available, the step is left suspended with its block and release condition written and pushed.

## Example
A coordinator finishes a wave and its tour ends at a gate close. It first appends a checkpoint stating what finished and the exact next action, pushes and verifies it, and marks SUCCESSOR NEEDED at the top of the handover. The successor is then seated directly at the Manager level, briefed from the handover and path ledger, and its spawn capability is checked before it is given staffing work.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example when a coordinator tour is ending or a successor needs to be seated. A person can also ask for the work directly in plain words, such as asking to hand over a build, to check whether a successor was seated correctly, or to recover a build whose coordinator stopped.

The skill works from the build own records: the handover or path ledger, the step opening record, the roster, and, where a push is part of the record, the project design repo where the checkpoint must land.

## For agents
Agent use differs by role. An outgoing coordinator checkpoints, pushes and verifies, and flags SUCCESSOR NEEDED, and does not spawn its own successor. The Manager seats the successor directly and proves spawn capability before assigning staffing. Any agent reporting coordinator claims checks them against records the coordinator cannot edit, such as runtime agent records and files on disk, before passing them on.
