# Audit Run

## What it is
This skill is the short form for running an audit inside a build. It applies to a loop audit, a logic audit, a test audit, and the finished product audit.

Every audit looks through seven lenses. Red is adversarial and looks for how the thing breaks or can be abused. Blue checks correctness case by case. Purple traces every decision, ruling, and fix into the artifact and back, marked LANDED, PARTIAL, CONTRADICTED, or MISSING. Green covers operations such as install, run, monitor, and recover. Yellow checks spec completeness and conformance. Orange checks whether a real person could follow and operate the result. White is the clerk and honesty lens, reconciling records and checking claims against evidence.

Running an audit follows six steps: seal the target by naming exactly what is being audited and at which commit or state, staff it with distinct agents per the level numbers, have each lens write its own paper, triage and severity rate findings into the round register, argue contested findings, and record a sign off verdict of pass, qualified, or fail with grounds named.

The skill sets the severity bar and the fix loop. Every issue raised is fixed before moving on, fixes start with a failing test that reproduces the finding, and the loop repeats until the round is clean or is stopped. Defects are repaired in the loop. Design questions are not fixed silently and go up for a ruling.

It also sets the exit gate: no Critical and no High findings open, the Purple trace at 100 percent, the full suite green from a clean clone, and live proof passed or honestly bounded and labelled.

## Example
A build reaches its finished product audit. The target is sealed at a named commit, each lens produces a paper, and White triages the findings into the register. A Blue finding shows a case that does not match the claim. A failing test is written first, the defect is fixed, and the round is re audited until it comes back clean and the exit gate holds.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example when an audit runs inside a build. A person can also ask for the work directly in plain words, such as asking to audit a build, a stage, or a finished product.

The person needs to identify what is to be audited. The audit itself seals the target by naming the exact artifact and its commit or state before findings are taken.

## For agents
Agent use is the same as the use described above. When the skill loads, agents staff the audit as distinct agents per lens work, take severity counts from the round register and never from estimates, and keep evidence packs in the private design repo only.
