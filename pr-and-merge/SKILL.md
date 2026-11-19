# PR and merge

Open and merge pull requests one concern at a time. For a batch from one audit or plan, fix order before any branch exists.

## 1. Plan before branching

List every change and the files it will touch, including new files.

Build a pairwise overlap matrix: for each pair, note shared paths and any path both would create.

If two changes touch the same file, or both create the same new file or module:

- Combine them into one PR, or
- Give one PR ownership of the new module and stack the other on it, or
- Serialize them so the second starts only after the first is on main.

Put broad cleanup, hygiene, and rename passes last. They overlap everything.

## 2. Pick merge order first

Order dependencies first, independent small fixes next, broad passes last.

Write that order in every PR body: `merge after #N` (or `merge after: none`).

Do not open the batch until the order is written down.

## 3. Each PR

One concern. Small diff. No drive-by edits.

```bash
git fetch origin main
git checkout -b <branch> origin/main
```

Run the full test suite on the branch. Do not open the PR if tests fail.

PR body must state:

- Goal
- Files touched
- Verification: paste literal test output
- Merge order (`merge after #N`)

```bash
gh pr create --base main --title "<concern>" --body "$(cat <<'EOF'
## Goal
<one sentence>

## Files
- path/to/file

## Verification
<paste test command and output>

## Merge order
merge after #N
EOF
)"
```

## 4. Commit identity

Use only the name and email the owner specifies. Never guess.

```bash
git config user.name "<owner-specified name>"
git config user.email "<owner-specified email>"
```

Set this before the first commit on the branch.

## 5. Before each merge

```bash
gh pr view N --json mergeable,mergeStateStatus,statusCheckRollup
```

If `mergeable` is `UNKNOWN`, wait and re-query. Do not merge yet.

Require `mergeable=MERGEABLE` and CI green.

If the repo has no CI, merge the PR onto current main locally and rerun the full test suite. Do not merge if that run fails.

```bash
git fetch origin main pull/N/head
git checkout -B trial-merge origin/main
git merge --no-commit --no-ff FETCH_HEAD
# run full tests; then:
git merge --abort
git checkout -
```

## 6. Merge one at a time

Merge only in the planned order. Watch each result. Log it.

```bash
gh pr merge N --merge
git fetch origin main
git checkout main && git pull origin main
# rerun full test suite on main
```

After each merge, re-check every remaining PR:

```bash
gh pr view N --json mergeable,mergeStateStatus
```

A merge can make later PRs conflict. Stop and handle that before the next merge.

## 7. First conflict

Stop the batch for that PR. Do not force-merge. Do not skip it blindly.

Trial-merge read-only and list conflicted files:

```bash
git fetch origin pull/N/head:prN
git checkout main && git pull origin main
git merge --no-commit --no-ff prN
git diff --name-only --diff-filter=U
git merge --abort
```

Rebase that PR onto new main. Keep both sides' intent. Never drop the other side's change to clear the conflict.

```bash
git checkout <branch>
git rebase origin/main
# resolve, then rerun full tests
git push --force-with-lease
```

Re-check mergeability, then continue the batch.

Report: merged, skipped, conflicting (with file list).

## 8. Never

- Force-push shared branches or main without owner confirmation.
- Merge a red PR.
- Resolve a conflict by deleting the other side's change.
- Merge a batch in an unattended loop. Log each result as it happens.

## 9. Finish

On main, confirm the build and the full test suite pass.

Close or update stale PRs that the batch superseded.

Report:

- Final main SHA: `git rev-parse origin/main`
- Per PR: number, merge commit or skip reason, conflicted files if any
