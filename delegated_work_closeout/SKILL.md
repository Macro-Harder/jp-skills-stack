# Delegated Work Closeout Verification

## Open a recovery record first

- Write the closeout record to disk before investigating, and append each verified fact to it as the check completes.

- Treat a missing, truncated or interrupted final report as unknown state, not as failure and not as success.

- List every claim the departed agent made that still needs proof, and keep each claim marked unverified until its own check lands in the record.

## Reconcile each state separately

- Check the local working tree on disk and record its head and whether it carries uncommitted changes.

- Fetch the remote head and tree through the GitHub API and record them separately from the local tree, because a shipped tree and a working tree can differ.

- Check any sealed, archived or clean copy tree as its own state, and prove its identity against the remote head instead of assuming two heads that look alike are the same tree.

- Check the installed or connected copy as its own state too, because an install can still hold pre-audit code while the repo has moved on, and a live proof of that install covers only the superseded build.

- Report any pair of states you could not prove identical as drift, with both heads named, rather than picking one as the truth.

## Verify claims, never reconstruct them

- Fetch every head, hash and count you report from the API, the disk or a fresh run, and never rebuild one from truncated notes, a partial transcript or memory of an earlier report.

- Run the test suite from a clean copy of the verified remote tree when you report a test result, and name the tree the result belongs to.

- Re-run a failing suite once and check the environment before calling a failure a regression, because a blocked binary, a full temp directory or a timing flake can fail a healthy tree.

- Mark a check you could not run as not run, with the reason, instead of carrying forward a result the departed agent reported.

## Report the recovered state

- Close the record with one verdict per open claim, using only verified, drifted, contradicted or unverified.

- Bank every item the recovery could not settle as a named open item for the user or the next coordinator, outside the success count.

- State plainly in the report to the user which states were verified first hand and which rest only on the departed agent word.

- Hand a continuation agent the recovery record as its starting brief, so it works from verified state rather than re-deriving the project from scratch.

## Available connectors

- [GitHub](~/workspace/custom-connectors/custom.github/CONNECTOR.md) for fetching remote heads and trees through the API and for pushing the recovery record to the project design repo.

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Ask the departed agent for its report once through its own chat when that chat is still reachable, and start the disk and API checks in parallel rather than waiting on the reply.

- Shrink the recovery to the claims the next decision depends on when the full state is large, and leave the rest marked unverified for a later pass.
