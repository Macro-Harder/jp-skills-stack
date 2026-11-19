# Fresh Eyes Review

## What it is

This skill separates building from reviewing. A builder works in a long session and accumulates deep context: the specification, the approaches that were tried and rejected, the reasons behind each decision. That memory helps building, but it harms reviewing. The builder reads the finished work through its history, sees what was meant instead of what is present, and passes over defects that a stranger would catch at once.

The fix is a genuinely fresh reviewer. It is an agent with no part in the work and no access to its history. It receives the finished diff or artefact plus the stated requirements, and nothing else. It cannot be charitable about intent, because it does not know the intent. It judges only whether the artefact in front of it meets the requirements in front of it.

Discipline matters on the builder side. The builder does not brief the reviewer, does not summarise, and does not pre answer findings. Findings return unfiltered, and each one is then dealt with on its merits: fixed, or rejected for a reason grounded in the work and requirements, not in private memory of what was intended or discussed.

## Example

A team builds a data import tool over a long session. Self review finds nothing wrong. A fresh reviewer, given only the code and the requirements, reports that the tool silently skips rows with empty dates, although the requirements say every row must be imported or logged. The builders had discussed empty dates early on and believed they had handled them, so their own review read the handling as present. The finding is fixed and a test is added. The rejection rule also applies in reverse: a finding the builders dislike still needs a real reason to refuse.

## How to use it

Supply the finished artefact and a clean statement of requirements, kept separate from build notes and discussion history. Assign a reviewer with no involvement in the work, collect its findings in full, and track each finding to a fix or a reasoned rejection.

## For agents

An agent acting as builder must not contaminate the review by adding context, however helpful it feels. An agent acting as reviewer must not ask the builder what was intended. Work only from the artefact and the requirements you were given.
