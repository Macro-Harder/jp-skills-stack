# Coordinator Succession and Handover

## Checkpoint before any ending

- Append a checkpoint to the build handover or path ledger after every wave, before doing anything else.

- Write the verified state, what finished, what did not finish and the exact next action in that checkpoint.

- Push the checkpoint and verify the push landed through the API before the coordinator ends, whenever a push is part of that build record.

- Mark the top of the handover SUCCESSOR NEEDED when the tour ends at a gate close or the coordinator must end for any reason.

## Seat the successor at the right depth

- Seat every successor directly from the Manager level, never through the outgoing coordinator and never by the outgoing coordinator spawning its own successor.

- Treat a coordinator seated one level deeper as holding no spawn capability until that capability is proven, because a spawn from a coordinator lands one level too deep to staff a step.

- Check spawn capability before assigning staffing work, and stop and record the block when it is absent rather than staffing short or merging seats.

- Brief the successor from the build own records, the handover, the path ledger and the step opening record, not from the outgoing coordinator summary alone.

## Verify claims before passing them on

- Check a coordinator claim about work in progress against the build own record before reporting it to the user.

- Confirm spun up agents from runtime agent records the coordinator cannot edit, and match agent IDs seat for seat against the roster when the user asks whether staffing was real.

- Confirm papers and other outputs on disk by count, size and spot checks such as a reported line count, and name any output the record does not yet cite.

- Correct a report openly when the record contradicts it, and state which source won and why.

## Recover a silent stop without dressing it up

- Treat a coordinator that ended without a successor, without a flag and without starting its recorded next action as a silent stop, and say so plainly.

- Recover from the last verified checkpoint, seat a fresh coordinator at the Manager level on the recorded next action first, and restate the checkpoint and flag orders in its brief.

- Count a backstop catch by a watchdog or estate routine as the safety net working, not as the succession itself working, and keep the two outcomes separate in the report.

- Leave a step suspended with its block and release condition written and pushed when no correctly seated coordinator is available, rather than claiming work that did not happen.

## Available connectors

- [GitHub](~/workspace/custom-connectors/custom.github/CONNECTOR.md) for verifying that a checkpoint, handover or suspended record actually landed in the project design repo.

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Wake a stalled coordinator once with the verified state spelled out when its records show the work is done and only closing seats remain, and replace it when the pulse does not produce work.

- Shrink the successor first task to the single recorded next action when a step opening is in doubt, so resumption is provable before wider work resumes.
