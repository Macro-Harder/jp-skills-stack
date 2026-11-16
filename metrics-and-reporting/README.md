# Metrics and Reporting

## What it is
This skill sets the counting rules and reporting rules for a build whenever it reports status, fills a live status snapshot, or counts anything that will be quoted. It is the loadable short form. The full metric definitions and reporting forms live in the build flow documents named in the skill, and those documents win where they disagree with this short form.

For counting, severity counts come from the round registers, never estimated. A snapshot carries critical, high, medium, and small counts, in that order, plus what is known and what is fixed. Total found is cumulative across rounds, with rounds keyed by step and round number, and a re report of the same round replaces that round figure instead of adding it twice. Live agent counts come from the registry of what is actually running at the moment of the snapshot, while the all time spun total is the scale figure and never shrinks. Before any count is reported, it is reconciled against its counting unit and its derivation, and counts of different kinds are never mixed into one figure. A figure whose source cannot be checked is labelled as unverified or left out.

For reporting, reports are brief, with bullets, one line per item, and the outcome first. A report states what finished, what failed, and what is next, with the evidence named. Coordinator claims are checked against the build own records before they are passed on, and anything the reader must act on is surfaced directly instead of being buried inside a progress update.

## Example
A build fills a live status snapshot after a new audit round. The severity counts are taken from that round register in critical, high, medium, and small order, the total found adds the new round to the running cumulative total, and the live agent count is read from the registry at that moment rather than from the total spun so far. The short report that follows gives the outcome first in bullets and names the evidence, such as a verified push or a register read.

## How to use it
Place the folder in an agent skills library. The agent loads the skill when a build reports status, fills a live status snapshot, or counts anything that will be quoted. A person can also ask for the work directly in plain words, for example by asking for a status report or a count that follows these rules.

The skill does not name inputs the person must supply. Its counts depend on the round registers and the registry of what is running, which the agent reads when preparing the snapshot or report.

## For agents
Agent use is the same as the use described above: apply the counting rules before quoting any figure, and apply the reporting rules to the form of every report.
