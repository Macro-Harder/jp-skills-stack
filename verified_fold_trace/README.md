# Verified Fold and Trace

## What it is
This skill verifies that every agreed decision actually landed in a large document or codebase, element by element, before a round is claimed complete. It first turns the agreed decisions into a numbered element list before changing anything, with one element per decision and no element that bundles two decisions. Each element gets a stable id, and the list is kept in the project record so the fold, the repair, and the re trace all cite the same ids. Summaries of a decision are treated as navigation only, and the full decision text is read before folding it.

Each element is then folded into the target document or codebase on its own, with the exact section, heading, or code location it changed noted. Cross references are checked after each element lands, including lists, matrices, and definitions elsewhere that must name the same thing. Where the project workflow calls for small verifiable changes, each landed element is pushed or saved separately and the saved revision is verified before moving on.

After the fold, every element is traced by a reader who did not write that fold, or in a separate pass that starts from the element list rather than from the fold notes. Each element is classified as landed, partial, contradicted, or missing, and every landed call is backed by a quoted string or an exact location from the target. The trace is counted out loud in the report, such as 51 of 51 landed, and every element that is not landed is listed by id. A round is never reported as complete from the fold pass alone. A completion claim needs a finished trace behind it.

Repair covers only the elements the trace marked partial, contradicted, or missing, with each repair scoped to its element. The repaired elements, plus anything their repair touched, are re traced and the counts are updated before the round is claimed closed. Any defect the round cannot settle is banked as a named open item for the next round instead of being folded into the success count. The same element thinking applies to code audits by listing each invariant once and checking every place it must hold, not only the first place found.

## Example
A set of agreed decisions is to be folded into a large document. The decisions become a numbered element list with stable ids. Each element is applied on its own and its location noted. An independent trace then checks each id against the target and reports, for example, 51 of 51 landed, or lists the ids that are partial, contradicted, or missing. Only the listed elements are repaired, they are re traced, and the updated count is reported before the round is called closed.

## How to use it
Place the folder in an agent skills library. The agent loads the skill when agreed decisions are being folded into a document or codebase and a round is to be verified before it is claimed complete. A person can also ask directly in plain words, for example by asking for a fold to be traced element by element. The person supplies the agreed decisions and the target document or codebase to fold into and trace against.

## For agents
Agent use is the same as the use already described, with the added notes the skill gives for better results. The agent can shrink the round when the element list grows past what one trace pass can check carefully, freeze a known good revision for outside readers while later rounds keep moving and name the frozen revision in anything sent out, and stop the loop when a full round returns no critical or high findings, or when the user calls the stop.
