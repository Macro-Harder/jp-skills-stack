# Verified Fold and Trace

## Build the element list

- Turn the agreed decisions into a numbered element list before changing anything, with one element per decision and no element that bundles two decisions.

- Give each element a stable id and keep the list in the project record so the fold, the repair and the re-trace all cite the same ids.

- Treat summaries of a decision as navigation only. Read the full decision text before folding it, because folds written from summaries dropped machinery in the early bridge-guard cycles.

## Fold one element at a time

- Apply each element to the target document or codebase on its own, and note the exact section, heading or code location it changed.

- Check cross references after each element lands, including lists, matrices and definitions elsewhere that must name the same thing.

- Push or save each landed element separately when the project workflow calls for small verifiable changes, and verify the saved revision before moving on.

## Trace independently

- Trace every element after the fold with a reader who did not write that fold, or in a separate pass that starts from the element list rather than from the fold notes.

- Classify each element as landed, partial, contradicted or missing, and back every landed call with a quoted string or an exact location from the target.

- Count the trace out loud in the report, such as 51 of 51 landed, and list every element that is not landed by id.

- Never report a round as complete from the fold pass alone. A completion claim needs a finished trace behind it.

## Repair and re-trace

- Repair only the elements the trace marked partial, contradicted or missing, and keep each repair scoped to its element.

- Re-trace the repaired elements plus anything their repair touched, and update the counts before claiming the round closed.

- Bank any defect the round cannot settle as a named open item for the next round instead of folding it into the success count.

- Apply the same element thinking to code audits by listing each invariant once and checking every place it must hold, not only the first place found.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Shrink the round when the element list grows past what one trace pass can check carefully, because two traced rounds beat one untraced round.

- Freeze a known good revision for outside readers while later rounds keep moving, and name the frozen revision in anything sent out.

- Stop the loop when a full round returns no critical or high findings, or when the user calls the stop, rather than tracing forever.
