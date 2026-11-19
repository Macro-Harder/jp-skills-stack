---
name: attempt-to-break-it
description: Run an adversarial attack loop on a built product with independent attackers, logging each break, fixing it, and re-attacking until it holds. Load when a build has passed its normal audit and needs hostile testing before live proof.
---

# Attempt to Break It

This skill distils Step 17, the attempt-to-break-it, audit, fix loop, in LEVEL-2-STEPS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose
Normal tests check that a product works as intended. This loop checks the opposite: how it fails when someone tries to make it fail. Independent attackers probe with hostile inputs, abuse cases, boundary values, and malformed data. Their work finds faults that builders and earlier auditors miss because they were not looking for failure in the same way.

## Procedure
1. Confirm the product is built and has cleared its prior audit loop. Do not start on a partial build.
2. Seat attackers who are separate from the builders and separate from the auditors who audited the build. Record the roster.
3. Give attackers the real interface and the product surface, not the internal test plan. Let them choose attack lines.
4. Run attacks by class. Cover at least hostile inputs, abuse cases, boundary values, malformed data, repeated or out of order actions, and resource pressure where relevant.
5. Log every break in an attack log grouped by attack class. For each entry record what was sent, what happened, what should have happened, and the severity.
6. Stop and fix each break. A fix starts with a test that reproduces the break, then the code change.
7. Audit each fix on its own. Confirm it closes the break without opening a new one.
8. Send the attackers back in. Re-run the full attack log plus fresh attacks in the same classes.
9. Repeat steps 5 to 8 until the product holds against the attack log, or the owner stops the loop.
10. Record the closing state plainly: what held, what was fixed, and any break left open.

## Edge cases
- A break that cannot be fixed is reported plainly, with its impact stated. Do not soften it, reclassify it as minor, or leave it out of the log.
- If an attacker is also a builder or a prior auditor on this product, replace that attacker. Fresh hostile eyes are the point.
- If an attack would cause real harm outside the test target, bound it to a safe copy or a local target and note the bound in the log.
- Passing the attack log once is not closure if new attack classes remain untried. Name untried classes in the closing record.
