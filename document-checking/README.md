# Document Checking

## What it is
Document checking treats a brief, plan, or specification as a product worth testing on its own, before anyone builds from it. Weak documents cause expensive rework because builders fill gaps with guesses and later discover the guesses were wrong.

The check runs in two passes that stay apart. Verification asks whether the document is sound as writing: each statement is clear, has one reading, fits with the others, and can be checked in practice. Validation asks whether the document is faithful: each statement carries the need or decision it came from, traced back to the decisions register. A sentence can be perfectly clear and still be the wrong requirement. A correct decision can be written so vaguely that two builders build two different things. Only the two passes together catch both.

Every defect is recorded with three facts: the statement itself, which pass found the problem, and what is wrong. Each pass produces its own record and states its own outcome. The records are never merged into a single verdict.

The same check also serves at stage openings. When a stage starts from a brief or plan, the check names the activity that will verify the stage work, the level it will work at, and the evidence it will leave behind.

## Example
A plan states: the importer will handle large files quickly. Verification flags it: large and quickly have no measure, so the statement is ambiguous and not checkable. The author rewrites it with a size limit and a time limit. Validation then traces the statement to the register and finds the decision was about correctness on large files, with no time promise at all. That is a separate defect, found only in pass two. The statement is corrected to match the decision, and each correction is noted in the record of the pass that raised it.

## How to use it
Place the folder in the custom skills directory. A person or team supplies the document to check and the decisions register it derives from. Work through the document statement by statement, twice, and keep two defect records. Supply the records back to the author with the document so corrections can be tracked pass by pass.

## For agents
An agent must not summarise the two passes into one score or one paragraph. Keep the records separate, quote the exact statement for each defect, and name the pass every time. When opening a stage, an agent also carries the added duty of naming the paired verifying activity, its level, and its planned evidence before doing the stage work.
