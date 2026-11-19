# PR and Merge

## What it is
This skill sets the rules for opening and merging pull requests.

Plan the batch before any branch exists. List each change and its files. A pairwise overlap matrix notes shared paths and new paths. If two changes share a file or a new module, combine them, stack them, or serialize them.

Dependencies go first, small fixes next, broad passes last. Every body says merge after #N, or merge after: none, before any PR opens.

Each PR is one concern and a small diff from current main. The full test suite must pass before it opens. The body states the goal, files, literal test output, and merge order. Commit name and email are only what the owner specifies.

Merge one at a time in that order. Require MERGEABLE and green CI. Wait if mergeable is UNKNOWN. With no CI, trial-merge and rerun the suite. After each merge, rerun the suite on main and recheck open PRs. On a conflict, stop, list the files, rebase onto new main, and keep both sides. Do not force-push shared branches or main without owner confirmation. Do not merge a red PR. Do not run the batch unattended. Report the final main SHA and each PR outcome.

## Example
A batch of PRs comes from one audit. Two would both create the same new helper module. The overlap matrix catches that before any branch exists. One PR owns the module. The other is stacked on it. A broad cleanup PR goes last. Each merge is followed by a test run on main and a mergeability recheck.

## How to use it
Place the folder in an agent skills library. The agent loads the skill whenever pull requests are opened or merged. A person can also ask for the work directly in plain words, for example by asking for a batch of fixes to be opened and merged under these rules.

## For agents
Agent use is the same discipline described above: overlap and order before any branch, one concern per PR, one merge at a time, tests on main and a mergeability recheck after each merge, and a stop on the first conflict until a rebase keeps both sides.
