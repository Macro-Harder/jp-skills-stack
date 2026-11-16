# Push Discipline

## What it is
This skill sets the rules for pushing work to GitHub during a build. It is the loadable short form of the full rule named in the skill. Where this skill and the full documents disagree, the documents win.

Each project has two repos from the start: a public build repo holding the system only, and a private design repo holding design documents and everything else. Work is pushed as it lands, never in one big batch at the end, with one finished unit or step per push, such as one fix, one paper, or one record. Tests travel in the same push as the work they test, and every round ends with a push carrying the round record.

Pushes on one repo are serial, never parallel, and the next push on that repo starts only after the previous one is verified. Different repos may push in parallel, about four at most. Every push is verified as landed through the GitHub API before anything depends on it, because a success message alone is not enough. On a timeout, a rate limit response, or a failed verification, work stops on that repo, its real state is re checked, and only then is a decision made. Nothing is re pushed blind. Large trees use the fast push helper, which uploads changed blobs only.

The skill also carries text rules for anything pushed. Nothing pushed may read as obviously AI written, in repo text, docs, comments, or commit messages.

## Example
A fix lands during a build round, together with its tests. It is pushed on its own as one unit, the commit is read back through the GitHub API to verify it landed, and only then does the next push on that same repo begin. At the end of the round, a further push carries the round record with what tests ran, their results, and what happened in the round.

## How to use it
Place the folder in an agent skills library. The agent loads the skill whenever work is pushed to GitHub during a build. A person can also ask for the work directly in plain words, for example by asking for finished work to be pushed and verified under these rules.

The skill states that plain git push does not work locally with the GitHub connector, and pushes go through the connector helpers at the path named in the skill.

## For agents
Agent use is the same discipline described above, applied to every push: one unit at a time, serial per repo, verified through the API before anything depends on it, and stopped on that repo after any timeout, rate limit response, or failed verification until its real state is re checked.
