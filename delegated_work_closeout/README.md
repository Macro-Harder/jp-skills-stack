# Delegated Work Closeout Verification

## What it is
This skill recovers and verifies the true state of delegated work when a coordinator or agent ends without a final report. A missing, truncated, or interrupted report is treated as unknown state, not as failure and not as success.

The work is recorded in a closeout record written to disk before investigating, with each verified fact appended as its check completes. Every claim the departed agent made is listed and kept marked unverified until its own check lands.

The skill reconciles each state separately: the local working tree on disk, the remote head and tree fetched through the GitHub API, any sealed, archived, or clean copy tree, and the installed or connected copy. States that cannot be proved identical are reported as drift, with both heads named. Claims are verified, never reconstructed from truncated notes, a partial transcript, or memory. Test results are run from a clean copy of the verified remote tree and named with that tree, or marked as not run with the reason.

The output is a closeout record with one verdict per open claim, using only verified, drifted, contradicted, or unverified. Items the recovery could not settle are banked as named open items outside the success count.

## Example
A coordinator ends without filing a final report for a build. The skill opens a recovery record, lists the coordinator claims that still need proof, and checks the local tree, the remote tree, the clean copy, and the installed copy as separate states. If the installed copy still holds older code while the repo has moved on, that drift is named in the record instead of treating a live proof of the old install as proof of the current build. The record closes with a verdict for each claim, and a continuation agent receives the record as its starting brief.

## How to use it
Place the folder in an agent skills library. The agent loads the skill when delegated work needs closing out or recovering before anyone reports what was built or claims a stage closed. A person can also ask for the work directly in plain words, for example by asking the agent to verify what a departed coordinator actually finished.

The skill itself works from the project on disk and from the remote state fetched through the GitHub API. It names the GitHub connector for fetching remote heads and trees and for pushing the recovery record to the project design repo.

## For agents
When this skill loads, open the recovery record first and append facts as checks complete. Fetch every head, hash, and count you report from the API, the disk, or a fresh run. Run the test suite from a clean copy of the verified remote tree, re run a failing suite once, and check the environment before calling a failure a regression. Ask the departed agent for its report once through its own chat when that chat is still reachable, and start the disk and API checks in parallel rather than waiting on the reply. When the full state is large, you may shrink the recovery to the claims the next decision depends on and leave the rest marked unverified for a later pass.
