# Brainstew Use

## What it is
This skill covers how to use Brainstew on a build that has it installed. Brainstew is the build shared memory, with a raw layer of source material and a wiki layer distilled from it. The console command named in the skill is wiki.

The rule is that Brainstew is used, not only installed. A Brainstew holding only a metrics record has not been used as intended.

In practice this means four things. Ingest material as it is produced, with sources cited, rather than in a batch at the end. Query Brainstew before re reading or re deriving an answer that the build has already ingested. Update records at every step close at the latest, so the wiki layer reflects the build state as each step closes. Run the lint before a step closes, fix what it flags, and only then close, so no step closes with its lint dirty.

The skill also gives the working pattern for three moments: adding new source material to the raw layer and updating affected wiki pages, starting a work session by querying Brainstew for current state and open questions before opening raw files, and closing a step by ingesting its outputs, updating the wiki, and linting.

## Example
Work on a build produces a new research note and a decision. Instead of leaving them only in files, the agent adds the note to the raw layer with its citation, updates the wiki pages the decision affects, and later, when a question comes up that the note already answers, queries Brainstew first instead of re reading the source files.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example on any build that has Brainstew installed. A person can also ask for the work directly in plain words, such as asking to ingest new material into Brainstew, to query it for the current state, or to update and lint it at a step close.

The skill does not require a specific input from the person beyond identifying the build or the material to ingest or the question to query.

## For agents
Agent use is the same as the use described above. When the skill loads, the agent ingests as work is produced, queries before re deriving, and treats a clean lint as a condition for closing a step.
