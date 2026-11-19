---
name: use-it-loop
description: Test a built product through real use by a genuine first user, fix what real use breaks, and repeat until use holds. Load after the build audit loop and before any break it work.
---

# Use-It Loop

This skill distils Step 16, the use-it, audit, fix loop, in LEVEL-2-STEPS.md of the build flow documents. Where this skill and the source disagree, the source wins.

## Purpose
After a product is built and its audit loop is clean, it still has not been used. This loop closes that gap. A first user drives the real interface through real work, the work its actual users do, so the flaws that only appear in genuine use are found and fixed before anyone tries to break the product on purpose.

## Procedure
1. Pick the first user. This person must never have built the thing. A builder cannot see the product fresh, so a builder in this seat voids the loop.
2. Give the first user real work, start to finish: a complete task an actual user would bring to the product, with real inputs. Do not give a demo path and do not give a test script.
3. Let the first user drive the real interface unaided. Watch and record, but do not coach, explain, or rescue. Help given during the run hides the very flaws the loop exists to find.
4. Record everything real use breaks or makes awkward: steps that confuse, inputs that are missing, an order of steps that fights the user, wording a non expert cannot follow, and any place the user stalls, guesses, or works around the product.
5. Fix each finding. Route design questions to the owner rather than settling them silently. Start each fix from the recorded finding so the fix can be checked against it.
6. Audit each fix. Confirm the fix resolves the finding and does not break work that previously held.
7. Run the loop again with real work, including the tasks that failed before. Repeat the use, fix, and audit cycle until a full session holds with no new findings.
8. Close on a session record: who the first user was, what work they drove, what broke, what was fixed, and the final clean run that closed the loop. File the record with the build records.

## Edge cases
- If the only available user helped build the product, wait for a genuine first user. Do not substitute a builder and call it done.
- If a session is run on a demo or a scripted path, it does not count. Rerun with real work.
- If wording confuses the first user, the wording is wrong, even if it is technically accurate. Fix the wording.
- Never coach the first user through a confusing step and then mark that step as passing.
- Never close the loop on a session with unrecorded findings.
- Never skip the audit of a fix to save time.
