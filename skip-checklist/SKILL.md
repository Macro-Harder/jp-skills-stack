---
name: skip-checklist
description: Use before adopting or skipping a move inside a build-flow step, when a move cannot be performed properly, and when a step record claims or omits a skip. Run the six questions, apply the verdict rules and the R-89 never-skip override, and record any skip. Never for flow steps, Auditor gates, stage closure, or pattern decisions.
---

# Skip Checklist

This skill rests on LEVEL-1-STANDING.md at /home/hatch/workspace/build-flow/LEVEL-1-STANDING.md. Where this skill and the documents disagree, the documents win.

## When to use

- T1: About to adopt a move in a step.
- T2: About to skip a move in a step.
- T3: About to skip a move on an irreversible decision, or one the step record marks so.
- T4: Checklist passes, move would not change the decision: a skip with a return trigger is considered.
- T5: A step record about to claim a skipped move, checked under step 7.
- T6: A move cannot be performed properly: distinguish gap from skip, screened at step 4.
- T7: A Framer, Breaker, or Trade-off Judge skip is proposed on an irreversible decision.
- T8: At step-record drafting and handover, a charged move is absent without a recorded skip: absence strip at step 8.

## Inputs

Sought, not guaranteed; no input gates a run.

- The move, a unit inside a step; flow steps, Auditor gates, and stage closures are out of scope.
- The entry, adopting or skipping, stated before verdict.
- The irreversibility determination, against the Passage 3 floor: the Step 19 exit gate where it closes a build, the Step 22 release gate, or a decision the step record marks irreversible. The source does not state a criterion for irreversible beyond that floor.
- The facts the six questions ask about. Where a demanded thing does not exist, the honest answer is "no".
- Gate 3 classification facts: the hosting step's charge and closure requirements.
- The charged-moves list and source (document and section or line, as stated in records), for the absence strip.
- Whether the team could perform the move properly, from context.
- The step record or working record, the run record's home and transplant target; step 7 covers neither existing. Working record, a construction: the record the step team drafts before the step record exists.

## Procedure

Search order, guidance only, not a precondition or step: find the hosting step's charge, irreversibility mark, closure requirements, and step or working record.

### Step 1: Entry routing

- State the run (adopting or skipping), move, and step, filling the run record's identification and Entry fields.
- If the candidate is a flow step, Auditor gate, or stage closure, stop: this skill does not apply.
- The source states no test for a step, gate, or closure presented as a move. Detection rests on runner classification.
- Move-or-pattern route: see Boundary.
- Skill-construction ruling: where the move cannot be identified beyond that exclusion and route, the run stops, recording the attempt in the working record or, where none exists, in output to the review channel; no verdict or run record is produced.
- Skill-construction ruling: where the entry cannot be stated, the six questions may run (entry-neutral) but no verdict is claimed; the record states entry as unstated. Step 2 runs; Gate 1 applies; Gates 2 and 3 do not; step 4 applies where inability is stated; step 5 runs; step 6 does not; step 7 records the answers, entry as unstated. The verdict field reads "No stated verdict" with the flag sentence: "The source does not state a verdict for a run whose entry cannot be stated."
- A mixed entry run: one move considered for both acts; two moves are two runs.

### Step 2: The irreversibility question

- Ask on the record whether the hosting decision is irreversible, against the Passage 3 floor; record the answer, or that it could not be obtained, in the irreversibility field.
- Where it could not be obtained, state plainly the R-89 protection cannot be confirmed.
- Contradictory irreversibility statements in the run material are treated as an answer that could not be obtained.
- Skill-construction ruling: in that unconfirmed state the three R-89 moves are treated as protected; a proposed Framer, Breaker, or Trade-off Judge skip does not proceed; the run records the block and unconfirmed state, puts the question to the step's Auditor.
- A run blocked by this protection produces no run record; its record is the step record block entry. No default is stated on irreversibility.

### Step 3: The three hard blocks

- Gate 1: Never a flow step, Auditor gate, or stage closure. Pattern-shaped uncertainty: see Boundary.
- Gate 2: The Framer, the Breaker, and the Trade-off Judge are never skipped on an irreversible decision, whatever the checklist returns, per R-89. The three outputs must be on record before the decision is taken. If any is skipped, the decision is not taken, is recorded as not taken, and the move runs before it is taken again. The source does not state who holds the never-skip check as such.
- Gate 3: A move whose output is the hosting step's closure evidence, or that a numbered rule requires at that step, is not skippable. Either limb is stated from the charge and closure requirements. The source does not state what counts as a step's closure evidence, nor which rules count as numbered rules.
- Skill construction ruling at Gate 3: where run material states the charge and closure requirements were sought and cannot be obtained, or do not settle whether either limb holds, the move is treated as not skippable for that run; the block is recorded. Where run material is merely silent on them, and states neither, Gate 3 does not block; the run proceeds; the run record states the Gate 3 classification was not stated in the material.
- Skill-construction scoping at Gate 3: this gate bars a skip only; an adopting run proposes no skip and is not blocked; where run material states the team cannot perform the move properly, step 4 screens it before a Gate 3 block takes effect; a step 4 gap is not blocked; the undetermined ruling applies only to a proposed skip not screened as a gap.
- A block under any gate ends the path; steps 4 to 6 do not run; the run proceeds only to step 7 recording. A gate-blocked run produces no run record; its record is the step record block entry and, under Gate 2, the not-taken entry where applicable. A block entry names gate and move.

### Step 4: Gap screening

- Runs where no gate has blocked the move; where inability is stated, screening precedes a Gate 3 block.
- If the team could not perform the move properly, record a gap; do not run the skip verdict rules. Steps 5 and 6 do not run; a pure gap produces no run record; the gap entry is its record.
- Where inability is stated for a move in a run that also proposes a skip of that move, the gap entry controls for that move, the skip verdict rules do not run for it, and any mixed entry records the skipping act as screened as a gap.
- Skill-construction minimum form: a step record entry naming the move and recording it as a gap, including the flag sentence: "The source does not state a form, place, or consequence for a gap beyond being recorded as a gap."
- The source states no standard for properly in could not perform the move properly.

### Step 5: The six questions

Runs only for unblocked, non-gap runs. Answers fill the six answers field, in order, and the who answered field.

1. Is the problem stated in one sentence, with a metric or a done condition? State it.
1. Was a cheaper move tried first? Say whether one was.
1. Is the owner of the move, and the owner of what it produces, named? Name both.
1. Are the new failure modes listed, and has at least one actually been tested? List them, one tested.
1. Is the consequence written down, covering cost, consistency, reversibility, who pays, and when? Write it across all five.
1. Is an exit or revisit trigger named? Name one.

- The questions are self-answered; the source states no verifier or evidence standard beyond each question's wording.
- For a genuinely new move, questions 2 and 4 often answer "no" until a cheaper move is tried and a failure mode tested.
- Skill-construction ruling, labelled by its flag, not as a source rule: a skipping run states on the record whether the move would change the decision, judged against question 1's problem statement and metric or done condition, by the answerer. The source states neither who makes it nor its evidence standard. The statement is recorded in the step record entry, read by step 6; not a run record field.
- Skill-construction line, mirroring step 2: where the determination cannot be made, record that; the closing rule requires the move would not change the decision and cannot fire on an unmade determination, so a skipping run in that state takes the "No stated verdict" path at step 6 with the P2 action note.

### Step 6: The verdict rules

Fills the verdict field.

- Adoption rule (adopting runs): Any "no" on adopting means do not adopt it yet. The source states the "no" consequence only. Labelled skill-construction presentation: an all-"yes" adopting run's verdict records the adoption rule does not bar adoption.
- Skipping rule (skipping runs): Any "no" on skipping an irreversible decision means do not skip it. The source does not state what "it" resolves to. As one unit with it, where irreversibility is established or undetermined: do not skip the move, do not take the decision on that skip, record the block and six answers, put the question to the step's Auditor.
- The source does not state a "no" consequence for skipping a reversible move and does not state an explicit outcome where the checklist passes and the move would change the decision.
- Closing rule (skipping runs): If the checklist passes and the move still would not change the decision, skip it and record the trigger that would bring it back.
- Before a skip results, record the Passage 2 judgement where that ground is relied on: that the move would cost more than it returns on this problem, at this scale, with this team, today. The closing rule stands here, the Passage 2 doctrine in its reference section, no relation stated between them.
- Action note for a "No stated verdict" outcome, adopted proposal P2: the note is not a verdict rule and gives no permission to skip on a "no". Record the six answers, claim no checklist verdict, and either run the move or record a taken skip separately on the Passage 2 judgement, with reason and return trigger.

### Step 7: Recording and the claim check

- Fills the skip field from step 6's verdict and judgement. For unblocked, non-gap runs, assemble the run record in Outputs order, checked against Outputs for the six answers; the verdict, with its case flag sentence and, where a verdict rule fired, the rule with its flag as one unit; the skip, with reason naming its ground, two separately labelled trigger lines, and the statement that the source does not state whether one trigger can satisfy both; the irreversibility question and answer; and who answered, before recording or transplanting.
- Record a skip in the step record as the full entry Outputs specifies: the skip, its reason naming its ground, and two separately labelled trigger lines, "exit or revisit trigger" and "the trigger that would bring it back".
- A working-record run record is transplanted into the step record when one exists or is created.
- Skill-construction ruling: if no step record or working record exists, present the run record to the step's review channel as output, transplant duty stated; the run never completes silently without a record home. Review channel, a construction: the step's records' route to its review board, the Auditor packet route.
- Never enter a skip in the decision queue.
- Skill-construction precedence: where a completed skip is presented for recording with the listed elements, it is recorded as the specified full entry; the claim check governs a skip asserted by a record under check, not a skip presented for recording.
- Claim check: check a claimed skip against the run record elements: the six answers, the verdict, the reason naming its ground, the two trigger lines, and, where the reason names Passage 2, a Passage 2 judgement recorded before the skip resulted. A judgement first recorded after the skip does not satisfy the check and the claim is recorded as an unverified claim. A claim missing elements, or lacking a run record, is recorded as an unverified claim in the step record. The source states no verifier for a claimed skip and no consequence for a fabricated claim.
- A claimed skip that is also a pattern skip, refusal, or parking result is recorded in one step record entry only, carrying both the claim check outcome and the shared form, and is listed once in the Auditor packet summary.
- Auditor packet summary, Passage 2: assembled at packet time from recorded skips, each named, with reason and return trigger, in short form, so the board sees every skip. Not a run output.

### Step 8: The absence strip

- At drafting and handover, compare charged moves against claimed moves. Each charged move shows as done, a recorded skip, a recorded gap, or an unrecorded absence.
- Screen each unrecorded absence for inability first: one the team could not perform is a gap under step 4. Any other absence runs this checklist now, each producing its own step 7 run record; the strip entry records each outcome, referencing its record. A claimed skip found goes through the step 7 claim check.
- A strip-initiated gate-blocked run produces no run record; the strip entry records the block and references the block entry.
- Skill-construction ruling: a recorded skip found by the strip is a claimed skip for the claim check where strip material quotes the record; where material summarises the skip without the claim check elements, the strip entry records the claim check could not be completed from the quoted material; the classification stands as recorded.
- The strip blocks nothing; its outputs never enter the decision queue.
- Skill-construction ruling: if a handover strip produces a new recorded skip after packet summary assembly, supplement the summary in sourced form before the board sees the step.
- Count check, labelled a construction: count the charged moves in the charged-moves list independently and state that total; then state done plus recorded skips plus recorded gaps plus unrecorded absences, with each charged move counted in exactly one category. Any difference between the two totals is recorded as an unresolved strip result. It proves internal consistency only, not charge completeness.
- The strip's classification, count statement, and unresolved results stand in the step record's strip entry, which records the charged-moves list's source (document and section or line, as stated in records); a packet supplement goes to the packet summary. A strip with no citable charge-list source records that as an unresolved strip result.

## Outputs

- One run, one run record: a bulleted field list, a skill-construction ruling: a self-contained block, so the source's silence on recording answers, adoption, and gaps does not negate it.
- The move and its hosting step; any uncertain classification annotates this field.
- Entry: adopting, skipping, mixed (one move considered for both acts), or unstated.
- The six answers, in order.
- The verdict, under the stated rules. Where no stated rule produces one, this field reads "No stated verdict", with the flag by case: for an unstated-entry run, the sentence "The source does not state a verdict for a run whose entry cannot be stated."; for other cases, the step 6 flags, printed in the same words: The source does not state a "no" consequence for skipping a reversible move and does not state an explicit outcome where the checklist passes and the move would change the decision. In a mixed entry run, one entry per act, each labelled by act, no combined verdict.
- Where a skip results: the skip, its reason naming its ground, and two separately labelled trigger lines in the source's exact terms, "exit or revisit trigger" (question 6) and "the trigger that would bring it back" (the recording duty). The source does not state whether one trigger can satisfy both.
- The irreversibility question and answer, or that it could not be obtained.
- Who answered.
- A gap is recorded under step 4, not as a run record field.

## Edge cases

- Mixed entry: no combined verdict; see step 6.
- Irreversibility cannot be obtained: the run proceeds under step 2, with R-89 protection unconfirmed and three moves treated as protected.
- No step record exists: see step 7; the transplant duty and, where neither exists, its presentation ruling apply.
- Classification uncertain, move or pattern: run anyway and record as uncertain; see Boundary.
- A "no" on a reversible skip: no consequence or outcome is stated. Record answers; any skip taken rests on the recorded Passage 2 judgement; the verdict field records "No stated verdict".

## Never-do list

- Never skip a flow step, Auditor gate, or stage closure.
- Never skip the Framer, Breaker, or Trade-off Judge on an irreversible decision.
- Never skip a move whose output is the hosting step's closure evidence, or that a numbered rule requires at that step.
- Never enter a skip in the decision queue.
- Never record a move the team could not perform properly as a skip.
- Never resolve the source's open points: no reading of "it", no relation between the two grounds, no unified trigger term, no criterion for "irreversible", no definition of "move" or "pattern".
- Never decide pattern adoption, refusal, or parking as such.

## Boundary

- This skill runs before adopting or skipping a move in any step, whether or not the move is pattern-shaped; it does not decide pattern adoption, refusal, or parking as such. Pattern adoption, refusal, and parking are decided under the R-226 Pattern skip test and the R-233 apparatus; where a pattern skip results, this skill carries only the shared recording form: the step record, a summary in the Auditor packet, and no entry in the decision queue. The two skills both ask six questions, one for moves and one for patterns; the pattern test governs the pattern decision as such. See step 7 for claimed skips that are also pattern results.
- Routing test, labelled a skill-construction rule: where move and pattern cannot be told apart, run this checklist, record the classification as uncertain.
- Interim, until the R-226 skill exists: this skill loads for move-level questions and the shared recording form only; the pattern decision waits for its apparatus.
- The shared form landed for move skips under DQ-032 and stands for patterns at R-233 in LEVEL-2, where a pattern skip, refusal, or parking results. When an R-226 Pattern skip test skill is installed in the skills directory, the interim line is deleted and this section is re-audited.
- Neighbour note: skills co-load; this skill governs only its own procedure. The release-gate skill governs the release gate stage; a move inside it is this skill's subject. The build-flow skill governs build and stages. The audit-run skill governs an audit as such; the claim check inside an audited record is this skill's. Skill-construction routing: where a request asks for an audit of a record including a claimed skip, the audit as such is the audit-run skill's; the claim check runs under step 7 in the same request. The principles-check skill checks decisions against the adopted principles set. The grill-mode skill is the grill step where the Framer runs, not a skip procedure.

## Reference: The skipping doctrine (Passage 2)

Passage 2. Source: LEVEL-1-STANDING.md at /home/hatch/workspace/build-flow/LEVEL-1-STANDING.md.

- A move inside a step may be skipped only on a recorded judgement that it would cost more than it returns on this problem, at this scale, with this team, today.
- The skip is recorded in the step record, with reason and the named trigger that would bring the move back. The Auditor packet's short summary lets the board see every skip in judging the step. Skips are not entered in the decision queue.
- A move the team could not perform properly is recorded as a gap, not a skip.
- This doctrine applies to moves only, never to flow steps, Auditor gates, or stage closure, which R-7 and the Auditor approval gate govern absolutely.
- R-89 overrides this doctrine wherever both apply.
- A move whose output is the hosting step's closure evidence, or that a numbered rule requires at that step, is not skippable under this doctrine.
- The doctrine's own test is the architect's question: "which step would change the decision, and have we done that one?"
- Passage 1 is carried in the procedure and Passage 4 in the recording step; neither is duplicated here.

## Reference: R-89 (Passage 3)

Passage 3. Source: LEVEL-1-STANDING.md at /home/hatch/workspace/build-flow/LEVEL-1-STANDING.md.

- On an irreversible decision, the Framer (Move 2), the Breaker (Move 12), and the Trade-off Judge (Move 17) must all run, outputs on record before the decision is taken.
- Framer: runs at the grill and brief steps, held by the Interviewer and the design team in their framing work.
- For each irreversible decision, a one sentence frame of that decision itself is on record before the decision is taken, framed by the role that brings the decision: the design team for design decisions, the Auditor for gate and closure decisions other than the release gate, and the Release-gate Keeper at the release gate.
- The source does not state a reconciliation of the Framer timing in the two statements above.
- Breaker: runs in the design and break work, held by the Contrarian in design and by the Red team in the break and audit work, never by the author of the work under decision.
- Trade-off Judge: runs at gate and closure decisions, held by the Auditor at gate and closure decisions other than the release gate, who runs those gates, and held by the Release-gate Keeper at the release gate; its weighing is recorded in the gate record.
- Minimum list: the Step 19 finished-product exit gate where it closes a build; the Step 22 release gate; any decision the step record marks irreversible.
- If any of the three is skipped, the decision is not taken, it is recorded as not taken, and the skipped move runs before it is taken again.
- Passage 1 is carried in the procedure and Passage 4 in the recording step; neither is duplicated here.
