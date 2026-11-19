# Pattern Skip Test

## What it is

This skill is a short screen that runs before the pattern gate. A proposal must answer six fields in full before it is allowed to go further. If any field fails, the proposal is skipped for now, and the skip is recorded with its reason and the trigger that would bring it back.

The six fields are simple on purpose. First, the problem in one sentence with a metric, so vague discomfort does not pass. Second, a cheaper fix that was tried, drawn from ordinary options such as an index, a bigger instance, a replica, a cache, or a clearer module boundary. Third, the owning team, named. Fourth, the new failure modes the pattern introduces, each one rehearsable. Fifth, the consistency consequence, written down. Sixth, an exit or reversal path, or a revisit trigger.

The test also absorbs the wider questions a reviewer might want to ask separately, such as complexity budget, team size, measured load, per operation consistency, and reversibility. Those concerns are checked inside the six fields. There is no second checklist running alongside, because a second list is how proposals pass one screen and fail in practice on a point nobody owned.

Two outcomes only are available: the proposal passes to its gate, or it is skipped for now. There is no middle outcome for a proposal that looks promising but leaves a field blank.

## Example

A proposal suggests a message queue between two modules to handle load spikes. Field one states the problem with a metric: a named call times out at a measured rate during peak load. Field two records that a bigger instance and a cache were tried and the timeout rate barely moved. Field three names the backend team as owner. Field four lists queue backlog, duplicate delivery, and ordering loss as new failure modes, each with a rehearsal. Field five notes that one read path becomes eventually consistent. Field six gives a reversal path: the direct call stays behind a switch for one release. All six fields pass, so the proposal proceeds to its gate.

If the same proposal had no metric and no cheaper fix tried, it would be skipped, with the return trigger recorded as a measured timeout rate and a completed trial of the cheaper options.

## How to use it

Supply the proposal and the answer to each of the six fields. A person or agent using the folder runs the fields in order, marks each one complete or not, and files the result. Nothing else is needed to use the test, and no extra criteria should be added on the side.

## For agents

An agent must not waive a field, invent a metric, or treat a missing cheaper fix trial as a minor concern. The agent records a search for cheaper alternatives when none was tried, treats an unrehearsable failure mode as an incomplete field, and files the skip reason and return trigger whenever the outcome is skip.
