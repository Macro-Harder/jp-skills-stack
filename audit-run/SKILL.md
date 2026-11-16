# Audit Run

Quick version, written 2026-11-14 outside the build flow. The standing audit plan in full lives at ~/workspace/audit-plans/FINISHED-PRODUCT-AUDIT-PLAN.md, and the audit rules inside the flow live in ~/workspace/build-flow/LEVEL-1-STANDING.md and LEVEL-2-STEPS.md. This skill is the loadable short form. Where this skill and those documents disagree, the documents win.

Use this skill whenever an audit runs inside a build: a loop audit, a logic audit, a test audit, or the finished-product audit.

## The lenses

Every audit looks through seven lenses. They are lenses, not a fixed seven-team form: staffing is set per level, with distinct agents, and one agent never covers two colour teams in the full form.

- Red: adversarial. Attack the thing, find how it breaks or can be abused.
- Blue: correctness. Does it do what it claims, case by case.
- Purple: trace, both directions. Every decision, ruling, and fix traced into the artifact and back, marked LANDED, PARTIAL, CONTRADICTED, or MISSING.
- Green: operations. Install, run, monitor, recover.
- Yellow: spec completeness and conformance. Everything the spec promises, present and matching.
- Orange: human and operator. Could a real person follow and operate this.
- White: clerk and honesty. Records reconciled, claims checked against evidence, nothing overstated.

## Running an audit

1. Seal the target: name exactly what is being audited, at which commit or state, so findings cannot drift.
2. Staff it per the level's audit numbers, distinct agents, from the auditor pool only.
3. Each lens audits and writes its own paper.
4. White triages: findings are deduplicated, severity-rated, and entered in the round register. Severity counts in reports come from the register, never estimated.
5. Argue: contested findings get argued before they are accepted.
6. Sign-off: the round's verdict is recorded, pass, qualified, or fail, with grounds named.

## The severity bar

Every issue an audit raises is fixed before moving on, any severity. The standing bar is 100 percent closure. An exception is discretion in the moment only: recorded, with its grounds, and the closure labelled qualified. A check that was done wrong never qualifies as an exception; it voids and re-runs. A check that ends in "cannot verify" because records were hidden counts as a fail.

## Fix loop

Audit, fix, re-audit, until the round comes back clean or Captain JP stops it. Fixes are test-first: a failing test reproduces the finding before the repair. After the loop, findings split two ways:

- Defects: repaired in the loop, in their own defect fix rounds.
- Design questions: go to Captain JP. Never fixed silently, never implemented on the audit's own authority.

## Exit gate

An audit stage closes only when all of these hold: 0 Critical and 0 High findings open, the Purple trace at 100 percent with nothing PARTIAL, CONTRADICTED, or MISSING, the full suite green from a clean clone, and the live proof passed or honestly bounded and labelled. Evidence packs live only in the project's private design repo, never in a public repo.
