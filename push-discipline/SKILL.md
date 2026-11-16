# Push Discipline

Quick version, written 2026-11-14 outside the build flow. The rule in full is R-241 in ~/workspace/build-flow/LEVEL-1-STANDING.md. This skill is the loadable short form. Where this skill and the documents disagree, the documents win.

Use this skill whenever work is pushed to GitHub during a build.

## The rules

- Two repos per project from the start: the public build repo holding the system only, and the private design repo named with the design suffix holding design documents and everything else.
- Push as the work lands, never in one big batch at the end. One finished unit or step per push: one fix, one paper, one record.
- Pushes on one repo are serial, never parallel. The next push on that repo starts only after the previous one is verified. Different repos may push in parallel, about four at most.
- Every push is verified as landed through the GitHub API before anything depends on it. A helper once reported success with a commit that did not exist on the remote, so a success message is never enough: read the commit or tree back.
- On a timeout, a 429, or a failed verification: stop on that repo, re-check its real state, then decide. Never re-push blind.
- Large trees use the fast push helper, which uploads changed blobs only. Locally, plain git push does not work with the GitHub connector; pushes go through the connector helpers in ~/workspace/custom-connectors/custom.github/bin/.
- Tests travel in the same push as the work they test.
- Every round ends with a push carrying the round's record: what tests ran, their results, and what happened in the round.
- A step or round normally pushes one repo or the other, both at the same step only rarely.
- The contribution count is never a target in either direction: no pushes to raise it, no finished work held back to lower it.
- A build whose repos lag its local tree is not finished.

## Text rules for anything pushed

Nothing pushed may read as obviously AI-written. No em dashes, and never swap an em dash for a hyphen or an en dash; rewrite the sentence. This covers repo text, docs, comments, and commit messages.
