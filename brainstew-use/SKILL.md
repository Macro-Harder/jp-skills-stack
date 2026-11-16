# Brainstew Use

Quick version, written 2026-11-14 outside the build flow. The rule in full is R-242 in ~/workspace/build-flow/LEVEL-1-STANDING.md. This skill is the loadable short form. Where this skill and the documents disagree, the documents win.

Use this skill on any build that has Brainstew installed (Step 1 of the flow installs it; the console command is wiki). Brainstew is the build's shared memory: a raw layer of source material and a wiki layer distilled from it.

## The rule

Brainstew is used, not only installed. A Brainstew holding only a metrics record has not been used as intended.

- Ingest material as it is produced: notes, research, decisions, and records go in when they are made, with their sources cited, not in a batch at the end.
- Query before re-reading or re-deriving: when a question can be answered from what the build already ingested, ask Brainstew first instead of re-reading source files or working the answer out again.
- Update records at every step close at the latest: the wiki layer reflects the build's state as each step closes.
- No step closes with its lint dirty: run the lint, fix what it flags, then close.

## In practice

- New source material: add it to the raw layer with its citation, then update the affected wiki pages.
- Starting a work session on the build: query Brainstew for the current state and the open questions before opening raw files.
- Closing a step: ingest the step's outputs, update the wiki, lint, and only then record the closure.
