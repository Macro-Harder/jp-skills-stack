# Build Flow

Quick version, written 2026-11-14 outside the build flow. The full rulebooks live in ~/workspace/build-flow/ (FLOW.md, LEVEL-1-STANDING.md, LEVEL-2-STEPS.md, LEVEL-3-TEAMS.md, LEVEL-4-MEMBERS.md, METRICS.md, REPORTING.md, PLAID.md). This skill is the loadable short form: enough to run a build in the right order with the right gates. Where this skill and the documents disagree, the documents win.

Use this skill whenever a build of any size starts or a build stage is being planned or closed.

## The order, always

take notes → pre-plan → grill → (research, audit, imagination) loop → design brief → (audit, fix, audit logic, fix logic, imagination) loop → design plan → (audit logic, fix) loop → more (research, imagination, audit, repair) loop → revisions only if needed → audit fix loop → (write tests, audit test) → build → (audit, fix loop) → (use-it, audit, fix) loop → (attempt-to-break-it, audit, fix) loop → live proof → (finished-product audit, fix) loop → (defect audit, fix) loop → confirmation live proof → release gate → plan next version if needed

Never start with the builder. Building is a late stage. No code, scaffolding, or repo building before the notes, pre-plan, grill, research, brief, plan, and tests that precede it.

## Hard rules

- A stage closes only at 100 percent. No closure on a partial, missing, or contradicted fold-in trace.
- Every stage closes with a push to GitHub, verified as landed through the API, before the next stage starts. Tests travel in the same push as the work they test.
- Two repos per project from day one: a public build repo holding the system only, and a private repo named with the design suffix holding briefs, plans, audits, and everything else. Design material never enters a public repo. Benchmarks and eval harnesses do ship in the public repo.
- Tests come before the code they test. Fixes also start with a test that reproduces the finding.
- Team minimums mean separate, distinct agents per member, never one agent wearing several hats. The only exception is the small tier's single audit team wearing several colour lenses.
- Every design and build team carries a fold-in tracer and a principles agent as distinct seats. Every design team carries a contrarian. Parallel research carries a clerk keeping the shared evidence register.
- A review board sits at every step, and the approval row after each step records its verdict.
- Every issue an audit raises is fixed before moving on, any severity. An exception is discretion in the moment only, recorded, with the closure labelled qualified. A check done wrong never qualifies and voids, then re-runs.
- Questions the work cannot settle go up, never get guessed at silently. Design questions are never implemented without a ruling.

## Tiers in outline

Low, Medium, High, Extra High, Plaid. The tier sets team sizes for every kind of team (note-taking, pre-plan research, research, imagination, design, build, audit, logic audit). Sizes are minimums, never ceilings, and never reduced below the numbers Captain JP set. The full ladder lives in LEVEL-3-TEAMS.md and the tier role files. Plaid is the maximum build and has its own document, PLAID.md.

## Stage notes

- Notes first: when the work rests on a primary source, the note-taking team covers it in full before anything is planned from it (see the note-taking-team skill).
- Grill: interview until what is being built, what done looks like, and what is out of scope are decided (see the grill-mode skill).
- Research before the brief runs as parallel teams with a clerk; imagination proposals are logged, audited, and fold-in traced before any of them land.
- Use-it means driving the real interface through real work as a first user would, not re-running the test suite.
- Attempt-to-break-it is adversarial: hostile inputs, abuse cases, ways to make it fail.
- Live proof runs the finished thing on the real system it was built for.
- Release gate: clean clone sweep, license and copyright holder check, no design material in the public repo, install verification where the product installs.
