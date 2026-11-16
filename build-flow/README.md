# Build Flow

## What it is
This skill is the short form for running a build in the right order with the right gates. It applies whenever a build of any size starts or a build stage is being planned or closed.

It states the full order: take notes, then pre plan, then grill, then a loop of research, audit, and imagination, then a design brief with its own audit, fix, logic audit, and imagination loop, then a design plan with a logic audit loop, then more research, imagination, audit, and repair, then revisions only if needed, then an audit fix loop, then write tests and audit the tests, then build, then audit and fix, use it and fix, and attempt to break it and fix loops, then live proof, finished product audit and defect audit loops, confirmation live proof, release gate, and planning the next version if needed. Building is a late stage, and no code, scaffolding, or repo building comes before the notes, pre plan, grill, research, brief, plan, and tests that precede it.

It sets hard rules that apply across stages. A stage closes only at 100 percent, with no closure on a partial, missing, or contradicted fold in trace. Every stage closes with a push to GitHub verified as landed through the API before the next stage starts, and tests travel in the same push as the work they test. Each project has two repos from day one, a public build repo holding the system only and a private design repo holding briefs, plans, and audits, with design material never in a public repo and benchmarks allowed in the public repo. Tests come before the code they test, and fixes start with a test that reproduces the finding.

It also covers team and gate rules: team minimums mean separate distinct agents per member, every design and build team carries a fold in tracer and a principles agent as distinct seats, every design team carries a contrarian, parallel research carries a clerk for the shared evidence register, a review board sits at every step, every audit issue is fixed before moving on, and questions the work cannot settle go up rather than being guessed at.

It outlines the five tiers, Low, Medium, High, Extra High, and Plaid, which set team sizes as minimums, and gives stage notes for notes, grill, research, use it, attempt to break it, live proof, and the release gate.

## Example
A new build is requested. Instead of starting with code, the work begins with notes on the primary sources, a pre plan, and a grill to decide what is being built, what done looks like, and what is out of scope. Research and imagination run in a loop and are audited before the brief is written, tests are written before the build, and the built product goes through use it, attempt to break it, live proof, and release gate stages in order.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example when a build starts or a stage is being planned or closed. A person can also ask for the work directly in plain words, such as asking to start a build or to close a stage under the flow.

The skill does not list a fixed input form. In practice the build needs a decided scope from the grill stage before building begins, and each stage needs its work and tests ready for the verified push that closes it.

## For agents
Agent use is the same as the use described above. When the skill loads, the agent follows the stated order, enforces the hard rules as stage conditions, and treats the full rulebooks named in the skill as governing where this short form and those documents disagree.
