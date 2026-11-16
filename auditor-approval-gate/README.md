# Auditor Approval Gate

## What it is
This skill runs the Auditor approval gate on a finished build flow step, from packet to recorded ruling. Without the gate, the next step does not open. It is not for an audit round as such, and it does not govern the Step 22 release gate sitting.

The gate applies in defined cases, including a finished step waiting on approval, a review board sitting on a finished step, a gate ruling being recorded, a step closure being tested, a broken rule with sound work case being decided at its gate, the Step 23 review of recorded gate outcomes for the whole build, and, at Plaid, independent re verification of closure evidence before the Auditor rules. Inside the gate, a companion skill handles flag naming, and that naming block must stand inside the gate record itself.

Inputs are a fixed set: the board charge, the entrance record, and inside it the step packet and the drawn checklist. The packet has four parts: a step snapshot, a skip summary, an Estate Keeper step check report, and a gate policy entry. Other inputs include the finished step record and its evidence artefacts as a named list, roster evidence and spawn records, the fold trace, attested closure links, the next step plan, the tier recorded for the step, and, at Plaid, the independent verification record. An input counts only where a record identifies it as that input. Missing parts have stated consequences, for example a missing Estate Keeper report bars the sitting and unchecked policy status bars recording a Go.

The procedure runs in order: two preconditions on the step finishing and the checklist being drawn, then acts covering parts delivered, completeness checked, policy status stated, Plaid re verification where it applies, the judging act with its three subchecks, board seating and form verification, packet presentation and verdict, verdict recording, gate completion, and opening and discharge. The judging act audits the step as actually staffed, runs the flag check, and performs attested closure checks.

Rulings use a closed vocabulary. The board may approve, approve with required expansion of the next step plan, or not approve. Outcomes are recorded only as Go, Kill, Hold, or Recycle, with recorded states such as CLOSED-PASS or CLOSED-QUALIFIED where they apply. A Go requires a commitment naming that passes a stated test, with every required role carrying a named seat or a named spawn intention and every committed resource identified. The skill also covers bars and blocks, the two bounded exception routes for broken rule cases and for a trace short of 100 percent LANDED, the form for a gate not held event, the Step 22 exception, and the Step 23 review line.

The output of one gate is one record on one page, with a core block and an annex block where every annex line is marked not triggered, owed, or complete. Where a gate is not held, the only output is a gate event in the step record, with no outcome word and no closed state.

## Example
A build step finishes and the team wants to start the next step. The gate checks that the evidence artefacts stand as a named list and that a checklist was drawn from the stated preconditions. The packet parts are delivered and checked, the Auditor judges the step against its roster and trace, and a board of at least three distinct members including a chair who was not on the producing team reaches a verdict. If the verdict is approved and the commitment naming for the next step passes its test, the ruling is recorded as Go and the next step opens on the correct plan. If the checklist was not drawn, the gate is recorded as not held and the step does not advance.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example when a finished step is waiting on its approval gate. A person can also ask for the work directly in plain words, such as asking to hold the gate on a named step or to record its ruling.

The gate needs the records named under Inputs to be present and identified in the step records. In practice that means the step record, its evidence artefacts, the packet parts, the drawn checklist, roster and spawn records, the fold trace, and the next step plan must be available for the step under gate. Where a part is missing, the skill states whether the sitting is barred or whether the gap is recorded and the board may Hold or Recycle.

## For agents
Agent use differs in role. The Auditor checks completeness, judges the step, and presents the packet. The board decides the ruling. The Manager makes the commitment naming for a Go. An agent loading this skill must load the flag naming companion before naming any flag, must not treat a coordinator report as closing a stage, must not rule on work the Auditor commissioned, and must follow the never do list in the skill, including never recording a Go without a passing commitment naming and never opening the next step without approval.
