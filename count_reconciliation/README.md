# Count and Total Reconciliation

## What it is
This skill covers reconciling a count or total against its counting unit and derivation before reporting it, so totals are not double counted, stale, or built from the wrong kind of item.

The first step is to define the counting unit first: write down in plain words what one counted item is, such as one distinct agent, one spin up event, one tickable checklist unit, or one audit place, and write down what is excluded. The skill stresses checking whether distinct items or every occurrence was asked for, because the two give different totals, and keeping one counting unit for the whole total, restarting the count if the unit changes part way through.

The second step is to derive the total two ways: build it from its parts with the addition shown and each part and subtotal named, and recount by a second route that does not reuse the first, such as counting the underlying list directly. The skill names double count shapes to watch for, including a per loop figure reported as a whole flow figure, a shared item counted in two scopes, and a total copied from an earlier tier or version after the inputs changed. The result is compared against every other place the same total appears, and every copy is fixed when the recount changes it.

The third step is to report the total with its derivation: the total together with its counting unit, its parts, and the source counted from, never as a bare number, labelled as measured, derived, or estimated. A total that could not be recounted is reported as not verified with the missing source named, rather than repeated from an earlier report. The derivation is recorded beside the total in the project record.

## Example
A total for spin ups is about to be reported. The counting unit is defined first as every spin up event, not distinct agents. The total is built from its parts, for example step team spin ups plus approval spin ups plus standing spin ups, and then recounted directly from the underlying list. If the two routes disagree, the discrepancy is resolved before the number is reported, and the reported figure carries its unit, parts, and source.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example when a count or total is to be reported. A person can also ask for the work directly in plain words, such as asking to verify a total, to recount a board figure, or to explain how a number was derived.

Where distinct items and every occurrence are both plausible and the choice changes the decision the total feeds, the skill says to ask the person which counting unit they mean. Otherwise the person needs to point to the total and the source it should be counted from.

## For agents
Agent use is the same as the use described above, with the added option to shrink the claim when a full recount is too large: report the smaller part that was recounted with its unit named, and leave the rest marked unverified.
