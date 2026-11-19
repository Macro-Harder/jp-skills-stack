# Pattern Gate

## What it is

This skill treats the adoption or removal of a design pattern at a design step as a gate event. The Auditor holds the gate. It is not a working preference that a team can adopt in passing and revisit later without a record.

At the centre is the gate record, completed and filed before any outcome is decided. The record states the problem as a measured or observed fact, names an owning team from the build roster that accepts the failure modes of the pattern, and assigns an exit class that describes how hard the pattern will be to leave later. The classes run from bypassable at the easy end to programme to exit at the hard end. The record also gives a sunset condition, the effect on per operation consistency contracts, the cheaper alternative that was tried or the reason none exists, who checked the evidence, and the complexity charge with its account route.

Evidence scales with the exit class. A pattern that is easy to bypass needs less proof than one that would take a programme of work to exit. The hardest class calls for measured evidence, an incremental path in, a containment plan, and a rehearsal.

Once an outcome is recorded, the record is fixed. It is never edited. A correction is a new entry that supersedes it, so the history of what was known at decision time stays intact.

## Example

A team proposes adding a shared cache layer across services at a design step. The gate record states the problem as measured latency on a named read path, not as a general wish for speed. The platform team is named as owner. The exit class is set to migration to exit, because callers will come to depend on cache timing. The sunset condition is that the layer is removed if hit rates fall below a stated level for a stated period. The record notes which read contracts gain eventual consistency and which stay unchanged, records the cheaper trial of a larger instance that was tried first, and names the reviewer who checked the latency figures. Only then does the Auditor record a Go.

## How to use it

Supply the pattern, whether it is adoption or removal, the design step, and the evidence for each record field. The gate stays closed until the record is complete. A person using this skill should expect Hold or Recycle, with missing fields named, if any part of the record is thin.

## For agents

An agent must not record a Go on an incomplete record, and must not edit a filed record to make it look complete in hindsight. The agent lists missing fields plainly, files corrections as superseding entries, and checks that the evidence matches the exit class before supporting any outcome.
