---
name: auditor-approval-gate
description: "Use when a build flow step has finished and its approval gate is to be held, a review board is to sit on a finished step, a gate ruling is to be recorded, a step closure is to be tested, a broken rule, sound work case is to be decided at its gate, the Step 23 review of recorded gate outcomes for the whole build is to be run, or, at Plaid, closure evidence is to be independently re-verified before the Auditor rules; the flag naming inside the gate runs under red-flag-check, loaded as a required companion. Never for an audit round as such, a Step 22 Auditor ruling, or closing a stage on a coordinator report."
---

# Auditor Approval Gate

> This skill rests on the Auditor approval gate and broken rule passages in LEVEL-2-STEPS.md, with R-51, R-7, R-27, and R-92 in the same document, R-55 in LEVEL-3-TEAMS.md, R-248 and R-3 in LEVEL-1-STANDING.md, the FLOW statement in FLOW.md, and the Plaid gate act in PLAID.md, as extracted in the build source selection. Where this skill and the documents disagree, the documents win.

## When to use

The one job: run the Auditor approval gate on a finished build flow step, from packet to recorded ruling, without which the next step does not open.

- T1: A build flow step has finished and the move to the next step is waiting on approval.
- T2: An Auditor is about to audit a finished step, check its roster against spawn records, or rule on the next step plan.
- T3: A review board is about to sit on a finished step, or its verdict is about to be recorded in the step approval row.
- T4: A gate record is being written for an ordinary step, with a commitment record for the next step, a plan ruling, or an expansion requirement.
- T5: A step closure is being tested against the closure conditions, including the fold trace condition, the roster condition, and the attested closure checks.
- T6: A case of broken rule, sound work has arisen at a step and must be examined and decided at that step gate.
- T7: At Step 23, the recorded gate outcomes for the whole build are being reviewed.
- T8: At Plaid, closure evidence must be independently re-verified before the Auditor rules.

Precedence, each line a skill construction:

- When this skill and audit-run both match, this skill governs the sitting, the gate internal audit runs under this skill judging act, and audit-run governs audit rounds as such.
- When red-flag-check matches inside a gate, this skill governs the sitting and red-flag-check runs as the required companion, its naming block inside the gate record itself, in the annex, in the companion recorded forms.
- At Step 22 this skill does not govern the sitting at all, release-gate governs, and this skill loads at build close for the Step 23 review.
- Where a task asks both for a step gate and for the judgement that a repo is fit to be called shipped, release-gate governs the shipment judgement and this skill governs the step ruling; neither substitutes for the other, at any step, not only at Step 22.
- Where a task asks for a gate ruling and a principles check together, principles-check loads alongside this skill, its breaches are inputs the gate must deal with, and neither half of the task may be dropped for the other.

The words approval, gate, audit, or closure in a document do not by themselves load this skill. The trigger is a finished step waiting on this gate, or a gate act in T1 to T8 being performed.

## Inputs

The fixed input set, a skill construction: four parts, relations stated, no claim that the source equates the terms: the board charge; the entrance record; and inside the entrance record, the step packet and the drawn checklist. The packet and the checklist are the gate working inputs. The charge states which gate outcomes the board may issue and on which stages.

Recognition rule for the fixed input set: an input counts as present only where a record in the step record set is identified as that input by its title, its heading, or an explicit pointer in the step record or the ledger entry for the step. A record whose substance resembles an input but which is nowhere so identified is recorded as not identified, and is not silently treated as that input. Any part not identified under this rule is recorded as missing, and the packet defaults and precondition consequences in this skill apply to it as missing.

The step packet carries four parts, each delivered by its producer, no single assembler:

- The step snapshot, by the Metrics Reporter: a one section summary of closed step metrics against base expectations, produced under REPORTING.md before the ruling is recorded. Context only, never a criterion.
- The skip summary, as defined in LEVEL-1 under Skipping a move. The six answers and the return trigger sit in the step record claiming the skip, not in the packet.
- The Estate Keeper step check report, covering unverified pushes, unfiled evidence, and drift.
- The gate policy entry, stating one of its three wordings in full at Act 3.

Packet defaults, a skill construction: a missing Estate Keeper report bars the sitting. A missing snapshot or skip summary does not bar the sitting; the gap is recorded, the ruling states the part was not before the board, and the board may Hold or Recycle if it wants the part. The absence of the snapshot is never a bar. Policy status not checked bars recording a Go, though it need not bar the sitting.

Two pointers, not restatements: packet figures are re-measured under R-256; an ending without a packet is classified under R-250, not argued over at the gate.

The drawn checklist: drawn under R-92 by the step record keeper, by standing appointment the Project Manager unless the step record names another record keeper at its opening, from the step stated preconditions as written, in the version in force for that step instance. The stated preconditions for a step stand in the step record at its opening, or in the stage layout or step definition record that the step record points to, with that pointer named as the source. The version in force is the version standing in that home at the time the step closed, as evidenced by that record. Where no such home can be identified under the recognition rule above, the checklist cannot be verified as drawn from the stated preconditions and Precondition 2 fails on that ground, recorded in those words. The step record, for all purposes in this skill, is the record identified under the recognition rule above as the record of the step under gate, in this estate the step own record file where one stands, otherwise the ledger entry for the step together with the records it points to. A checklist with no named drawer is not drawn under that rule. The drawer naming must stand in that step record; a drawer named only in a product of the step, such as an eval file, an audit paper, or a trace, does not satisfy the rule. Item form under R-61 and running under R-62 are pointed to, not restated. If no checklist is drawn, or it is drawn from other than the stated preconditions, or it omits a stated precondition meeting the R-61 killer test, the pause point does not run and the gate is recorded as not held under Precondition 2.

Remaining inputs, by pointer only: the finished step record and its evidence artefacts, presented as a named list at the gate, with no artefacts meaning no gate; roster evidence and spawn records, including seats added under R-50 with recording times; the fold trace over the stage inputs; the attested closure links named by the stage layout under R-79; the next step plan as written; the tier recorded for the step; and, at Plaid, the independent verification recorded in the packet under Act 4.

Belonging rule for evidence: evidence belongs to the gate only where it is identified under the recognition rule above as a record of the step under gate, or is pointed to by that step record. A file recording a later run, a re run, or a later stage position on the same material does not displace the step record position for this gate, and is noted as later material where it conflicts. Any unresolved conflict between belonging files is recorded in the gate record annex, or, where the gate is not held, in the gate event reason line, and bars a Go until resolved.

Step specific entrance item: where a step own rule adds an entrance item, for example the Step 6 Research Clerk completeness signature under LEVEL-2-STEPS.md line 73, it rides with the packet for that step, in addition to the four packet parts.

Criterion status, a skill construction, item by item: the snapshot is context only, never a criterion; the skip summary and the Estate Keeper report are evidence the board weighs, neither a blocking condition on its own; a gate policy entry, where one stands, governs how this gate runs only inside the bars and the closure conditions, and is applied as written within that scope; it cannot waive a bar, a closure condition, or the 100 percent LANDED trace condition; where policy text purports to waive one, the bars govern, the gate does not record a Go on the waived point, and the conflict is recorded in the gate record; blocking comes only from the closure conditions and the gate bars in Bars and blocks, applied at Acts 8 and 9.

## Working tables

Home passage: P1, the Auditor approval gate, LEVEL-2-STEPS.md lines 17 to 19.

Table A: the three ruling forms and their mapping.

| Ruling form | R-51 outcome | Recorded as |
|---|---|---|
| Approved | Go, only where the commitment record stands | The applicable CLOSED state of R-3 |
| Approved with required expansion of the next step plan | Go, on the same terms, with the expansion consequence recorded in the commitment record naming the additions | The applicable CLOSED state of R-3 |
| Not approved | No single outcome word: the board selects Kill, Hold, or Recycle | Kill records KILLED; Hold records SUSPENDED, with the release condition and the lift authority named; Recycle records RECYCLED, with the stage returned to named |

The four outcome words are gate outcomes only, and no other word is recorded as a gate outcome.

Home passage: S9, R-3, LEVEL-1-STANDING.md lines 109 to 111.

Table B: the three recorded states.

| Recorded state | Meaning |
|---|---|
| CLOSED-PASS | Closed under the closure rule with verdict PASS, and terminal. |
| CLOSED-QUALIFIED | Closed with verdict PASS-QUALIFIED, where the qualification lies in the result itself, such as a named bound, a recorded non-pass, or a recorded deferral, and travels with every citation. It records closure over outstanding trace elements only under the R-7 bounded exception, with the exception named, and closure let stand over an uncorrected breach only under the same exception, with the exception named. A qualified record does not satisfy a later gate bar requiring a pass. |
| CLOSED-FAIL | Closed with verdict FAIL, and terminal. |

At Plaid no closure records CLOSED-QUALIFIED and the bounded exception does not run, so a step that would need either does not close at Plaid (PLAID.md line 124, DQ-119).

> Stated limit: CLOSED-FAIL stands in R-3 for a record closed as failed. No act in this procedure records it. The not approved outcomes of this gate record as KILLED, SUSPENDED, or RECYCLED with the outcome, and no mapping entry in this skill assigns CLOSED-FAIL.

The CLOSED state assignment per mapping entry at Act 8 is labelled an inference in this skill, because no passage names the applicable state entry by entry.

## Bars and blocks

One line per bar, short form, with the act that applies it. No bar is explained here.

- No artefacts, no gate (Precondition 1).
- No checklist drawn, or a checklist drawn from other than the stated preconditions, the pause point does not run (Precondition 2).
- A missing Estate Keeper report bars the sitting (Act 2).
- Policy status not checked bars a Go (Act 3).
- A staffing shortfall recorded PARTIAL bars the move to the next step (Act 5, first subcheck).
- The red flag check not run, the step does not advance (Act 5, second subcheck).
- A present flag touching closure, staffing integrity, verification, or secrets blocks closure until remedied and recorded or carried under governing rules (Act 5, second subcheck).
- Failure of the attested closure links or checks (Act 5, third subcheck).
- The fold trace short of 100 percent LANDED with no bounded exception (Acts 8 and 9).
- The commissioning bar, the Auditor records no ruling on work the Auditor commissioned (Acts 5, 6, and 7).
- A board below the fixed form does not sit (Act 6).
- At Plaid, the bounded exception does not run and no closure records CLOSED-QUALIFIED, so a step needing either does not close at Plaid (Acts 4 and 8).

## Procedure

The procedure is one ordered procedure. The ten act order is a skill construction, restructured from the twelve act working order: old Acts 1 and 2 are the Preconditions; old Act 3 splits into Acts 1 to 3; old Acts 5 to 7 merge as Act 5; old Act 8 splits into Acts 6 and 7; old Act 9 splits into Acts 8 and 9; old Act 10 stands; old Acts 11 and 12 stand as sections after Gate not held. Source timing points stand inside their acts: snapshot before the ruling is recorded; Plaid re-verification before the Auditor rules; no checklist, no pause point. No deadline for the ruling is prescribed, because the source states none; the ruling is recorded before the next step opens, which is definitional. Wording discipline, a skill construction: step for the gate acts, stage for closure and recycle statements, join at Precondition 1; recycle entries name the stage returned to, in its recorded form. Exit line rule, governing every act: where an act carries the line, if this cannot be completed, record a gate not held event and stop, that line is the whole instruction for that failure, with no added mechanics.

### Precondition 1: The step finishes

- Input: the finished step, its step record, and its evidence artefacts.
- Action: verify that the stage presents its evidence artefacts at the gate as a named list. The list is presented by the step record keeper, presenting the step record and its evidence artefacts at the gate, and the list must stand in the step record or in a gate covering record that the step record points to. A list supplied only in a tasking, a brief for the sitting, or any paper outside those two homes does not by itself satisfy this precondition, though the artefacts named in it may be identified under the recognition rule in Inputs and presented by the keeper on that basis. Finished status is evidenced by the step named evidence artefacts existing in their final form for the step and identified under the recognition rule in Inputs, together with the step record of the work. A status line asserting finished, whoever wrote it and wherever it stands, including inside the step record itself, is an assertion and not evidence. Where the only finished evidence offered is a status assertion, Precondition 1 is not met and the gate is not held on that ground. A coordinator report never closes a stage. The wording join stands here: the gate acts are stated for the step, and closure and recycle statements from Act 8 onward are stated for the stage; this is where the procedure passes from one to the other.
- Output: the named artefact list at the gate.
- Done condition: the artefacts stand presented as a named list in one of the two homes stated in the Action. If absent, record a gate not held event and stop.
- If Precondition 1 cannot be completed, record a gate not held event and stop.
- The notice duty for a gate not held stands in full in the Gate not held section.

### Precondition 2: The checklist is drawn

- Input: the step stated preconditions as written, in the version in force for that step instance. The stated preconditions stand in the step record at its opening, or in the stage layout or step definition record that the step record points to, with that pointer named as the source, and the version in force is the version standing in that home at the time the step closed, as evidenced by that record. Where no such home can be identified under the recognition rule in Inputs, the checklist cannot be verified as drawn from the stated preconditions and this precondition fails on that ground, recorded in those words.
- Action: verify that the step record keeper has drawn the judging checklist under R-92, its drawer named in the step record, standing inside the entrance record. The step record here is the record identified under the recognition rule in Inputs as the record of the step under gate, and a drawer named only in a product of the step, such as an eval file, an audit paper, or a trace, does not satisfy this action. Drawing is not running, not judging, and not closing, and creates no new criteria.
- Output: the drawn checklist, inside the entrance record.
- Done condition: a checklist drawn from the stated preconditions stands, its drawer named. If absent, or drawn from other than the stated preconditions, record a gate not held event and stop.
- If Precondition 2 cannot be completed, record a gate not held event and stop.
- The notice duty for a gate not held stands in full in the Gate not held section.

### Act 1: Parts delivered

- Input: the four packet parts in Inputs, each delivered by its producer, and the figures the packet rests on, re-measured under R-256.
- Action: each part is delivered by its producer: the snapshot by the Metrics Reporter, the skip summary from the step record, the step check report by the Estate Keeper, the gate policy entry from the build records. There is no single assembler.
- Output: the packet parts as delivered, each present or recorded missing.
- Done condition: every part stands delivered or recorded missing, with no part presented as present when it is not.
- The notice duty for a gate not held stands in full in the Gate not held section.

### Act 2: Completeness checked

- Input: the packet as delivered at Act 1.
- Action: the Auditor checks packet completeness before judging, and applies the packet defaults in Inputs part by part. The Auditor presents no incomplete packet as complete, and every missing part is recorded as missing.
- Output: the packet as it stands, with each part present or recorded missing.
- Done condition: either the packet stands ready for judging, with any non-barring gap recorded, or the sitting is barred, in which case a gate not held event is recorded and the step does not advance. A missing Estate Keeper report bars the sitting.
- The notice duty for a gate not held stands in full in the Gate not held section.

### Act 3: Policy status stated

- Input: the gate policy entry from the build records.
- Action: the gate policy entry is stated in one of its three stated wordings, given in full: a policy entry follows; no policy stands for this step after a named check of the build records; or policy status not checked, naming who checked and where. A gate policy entry governs how the gate runs only inside the bars and the closure conditions; it cannot waive a bar, a closure condition, or the 100 percent LANDED trace condition; where policy text purports to waive one, the bars govern, the gate does not record a Go on the waived point, and the conflict is recorded in the gate record.
- Output: the policy status in one of the three wordings, standing in the packet.
- Done condition: the policy status stands stated in one of the three wordings. Policy status not checked bars a Go at Acts 8 and 9, though it need not bar the sitting.

### Act 4: Plaid re-verification

At Plaid only.

- Input: the step closure evidence at tier Plaid: that the artefacts exist, the roster matches spawn records, and the trace is complete.
- Action, a skill construction settling an operational reading: an outside agent meeting the outside conditions performs the re-verification before the Auditor rules. The operative outside conditions, stated once and in this form only, are no seat on the build, not a member of any of its teams, and not the step coordinator. The Auditor receives the re-verification into the packet and performs the attested closure checks at Act 5, third subcheck, on its basis, except for work the Auditor commissioned, where the assessor under the commissioning bar performs them. The packet records both acts separately, with names and standing. Source point: the re-verification happens before the Auditor rules; a step whose closure evidence has not been independently verified does not reach the Auditor.
- Output: the verification record inside the packet, naming performer, standing, and its three coverage items.
- Done condition: the verification stands recorded in the packet before any ruling.
- Plaid bar: at Plaid the bounded exception does not run and no closure records CLOSED-QUALIFIED; a step that would need either does not close at Plaid (PLAID.md line 124, DQ-119).
- Stated limit, OI-T05, in full at this act only: the source states both that the re-verification is the gate act itself and that the attested checks are the Auditor own checks; this construction reconciles the two, and where a build cannot seat an outside verifier, a Plaid gate cannot be recorded as fully compliant.

### Act 5: The judging act

One judging act over one evidence set, with three named subchecks in fixed order. A failure in any subcheck is a failure of the act.

- Input: the packet, the drawn checklist, the step record, roster evidence and spawn records, the next step plan as written, the step handovers, records, and reports, and the stage layout required links. Only evidence that belongs to the step under gate under the belonging rule in Inputs is judged here; later material and unresolved conflicts are handled as that rule states.
- Action: run the three subchecks below, in fixed order, over one evidence set.

#### Subcheck 1: Audit as staffed

The Auditor audits the finished step against the rules of this flow, checks the roster against spawn records, and judges the step as it was actually staffed, including agents spun up during it under R-50. The Auditor neither approves nor vetoes spin ups, and may require additions as a condition of approving the next step plan, each addition taking a distinct scope and a unique role. Work the Auditor commissioned by requiring its addition is not audited for ruling by the Auditor; an assessor other than the Auditor assesses it under R-73, and the commissioning bar in full at Acts 6 and 7 applies to its board and its attested checks. The Auditor tests the closure conditions that can be tested before the board sits: the evidence artefacts named for the stage exist; the fold trace stands at 100 percent LANDED with no element PARTIAL, MISSING, or CONTRADICTED, subject only to the two closure routes at Act 8; and the roster evidence satisfies the member and team rules at the tier recorded for the step, with a staffing shortfall recorded PARTIAL barring the move to the next step. The full Auditor job in auditor.md is pointed to, not restated.

#### Flag naming under red-flag-check

Load red-flag-check now, before naming any flag, and stand its naming block inside the gate record itself, in the annex. Until red-flag-check is released into ~/workspace/custom-skills/, the companion loads from its build draft in its build folder; on release the catalogue copy governs. Red-flag-check runs as the required companion inside this gate; this skill governs the sitting, and red-flag-check owns the check, its flag list, its evidence set, its judging, and its naming block. Flag naming cannot be completed from this skill alone. The red flag list is pointed to the red-flag-check skill as its carrier, with the LEVEL-1 annex named as that skill source. Each flag is named present or absent for the step, or, where the companion form has it, not named; a flag recorded not named leaves the check not run in full for gate bar purposes. A present flag is a finding in the ruling, at the severity the Auditor judges under the severity rules in force, pointed to, not restated. A step does not advance where the check was not run. A present flag touching closure, staffing integrity, verification, or secrets blocks closure until remedied and the remedy recorded, or the closure carries it under the rules governing findings and qualifications. The check creates no state, no grade, and no verdict form.

#### Subcheck 3: Attested closure checks

The three attested closure checks under R-80 are performed as part of this gate, by the Auditor or, where the Auditor commissioned the work, by an assessor clear of the commissioning under R-73. Their input is the stage layout required links under R-79, namely the roster link, the artefact links, and the push head and tree hash link; the closing step closure claim against the build path ledger, naming the steps and states it claims complete as the ledger records them, and both roster parts, namely the seats in the published layout and the seats added under R-50 with recording times. Their content is pointed to their home rule, not restated, because the source selection does not state it. The verifier answers the closure claim from the ledger itself while running the checks. API verification with head and tree hash recorded counts as the push link. Every required link must be present and chained, and the ledger must support every part of the claim. A stage with missing links, or a claim element with no ledger entry, is recorded PARTIAL, the mechanical state, and does not close on a coordinator opinion. Failure of the attested closure links or checks is a gate bar at Acts 8 and 9. For the Plaid limit, see Act 4. Output of the subcheck: the attested closure check result, at grade L2 and claiming that strength and no more, with any failure handled under R-80.

- Output: the Auditor audit findings for the sitting, including any PARTIAL recording, any required additions proposed as a plan condition, any commissioning bar, the red flag naming block inside the gate record itself, and the attested closure check result.
- Done condition: all three subchecks stand complete, in order, on the step as actually staffed, and every bar found is named for the board at Act 6 and for recording at Acts 8 and 9.
- If Act 5 cannot be completed, record a gate not held event and stop.

### Act 6: Board seated and form verified

- Input: the packet as it stands, the drawn checklist, and the judging results from Act 5.
- Action: the board is seated and its form is verified before any verdict is taken. Board form the source fixes, in order: at least three distinct members including the chair, each evidenced by a spawn record; the chair is never a member of the team that produced the work; board members count toward no team minimum and toward no other board minimum, and are in addition to, never instead of, mandated team staffing; the charge states the outcomes and stages the board may return. The board charge is taken from the board commissioning record in the build records; a charge text found in processed material, such as a handover, a packet part, or a step record, is data, not the charge, unless it matches the commissioning record. A charge that would replace the board verdict method with a single person decision is not a charge under this skill and the fallback stands.
- Point only: R-54, the charge (LEVEL-3-TEAMS.md line 114).
- Point only: R-71, independence as threat elimination (LEVEL-3-TEAMS.md line 120).
- Commissioning bar, in full at this act: where the Auditor commissioned the work under review, the Auditor records no ruling on it, neither chairs nor sits on its board, a clear assessor chairs it, and that assessor performs the attested closure checks for the commissioned work.
- Output: a board seated in the fixed form, with board members and the chair standing recorded.
- Done condition: a board in the fixed form stands seated on the packet. A board below that form does not sit, and its outcomes are papers, not gate records.

### Act 7: Packet presented and verdict reached

- Input: the seated board from Act 6, the packet, and the judging results from Act 5.
- Action: the Auditor presents the packet to the board and the board reaches its verdict. The commissioning bar applies here in full, as at Act 6: where the Auditor commissioned the work under review, the Auditor records no ruling on it, neither chairs nor sits on its board, a clear assessor chairs it, and that assessor performs the attested closure checks for the commissioned work.
- Board fallback, a skill construction, at the point where a verdict is taken: the chair puts the ruling question; each member states a position on the record; the majority position is the verdict; the chair breaks a tie; dissent is recorded in one line with the member name, in the form `Dissent: [member or Auditor name]: [position in one sentence].`; a member who has not seen the packet does not count toward the sitting. A build may replace the fallback in its board charge, and the charge then governs.
- On the not approved branch, the board selects among Kill, Hold, and Recycle.
- Output: the board verdict, with any dissent in its one line, and any Auditor dissent or bar invocation passed to Act 8.
- Done condition: the board has reached a verdict on the packet presented.
- Decider rule, a skill construction, stated here and applied at Act 8: the board verdict is the gate ruling; the board decides among the three ruling forms and, on the not approved branch, among Kill, Hold, and Recycle. Point of use: OI-T02, with Act 8.

Last check, before recording. Answer each question yes or no from material already produced.

```text
1. Does the flag naming block stand inside the gate record itself, in the annex, in the companion recorded forms? (Act 5, second subcheck)
2. Does the fold trace stand at 100 percent LANDED, or is a bounded exception route actually in play with its decider named? (Act 8, third part)
3. If the ruling is a Go, does a commitment naming exist that can pass the Act 9 test? (Act 9)
4. If the state will be CLOSED-QUALIFIED, is the qualification named in words, and, at Plaid, is that state barred for this step? (Act 8, fourth part)
5. Is any gate bar standing unnamed? (Bars and blocks; Act 8)
```

A no answer is fixed before recording, or recording does not proceed on that basis. The strip carries questions and pointers only, no rule text of its own.

### Act 8: Verdict recorded

- Input: the board verdict from Act 7, the closure condition results from Act 5, the packet standing from Acts 1 to 3, and the next step plan.
- Action: the verdict is recorded in four parts, all recorded before the next step opens.

#### First part: The decider rule and the Auditor bar

The decider rule, a skill construction: the board verdict is the gate ruling. The plan ruling remains the Auditor named field in the gate record, completed at Act 9. The Auditor holds one bar: stop a Go only by naming a failed closure condition or gate bar, cited in the record. Any other disagreement is dissent beside the board ruling, in the form `Dissent: [member or Auditor name]: [position in one sentence].`, and does not stop the step. Where the bar is invoked and the board disputes the failure, both positions are recorded, the step does not advance, and the dispute goes to the decision queue, in the form `Dispute to the decision queue: Auditor bar on [failed closure condition or gate bar cited]; board position: [position in one sentence]; Auditor position: [position in one sentence]; step does not advance.`, because the dispute is about a closure fact, not a judgement. Point of use: OI-T02 with Act 7.

#### Second part: Closure conditions and gate bars

No Go is recorded unless every closure condition holds and no gate bar stands. Bars are applied here in two short sublists, each item cited from Bars and blocks, not restated at length.

Closure conditions: artefacts named for the stage do not exist; fold trace short of 100 percent LANDED with no bounded exception under the routes below; staffing shortfall recorded PARTIAL.

Gate bars: no checklist drawn; red flag check not run; present red flag touching closure, staffing integrity, verification, or secrets, until remedied and recorded or carried under the governing rules; failure of the attested closure links or checks; missing Estate Keeper report under the Act 2 defaults; policy status not checked.

The commissioning bar and the board below fixed form bar are omitted from both sublists here: the first bites at Acts 5, 6, and 7, the second at Act 6.

#### Third part: The two closure routes

Route one, broken rule, sound work. Where a team broke a rule of this flow in the step and the work is otherwise sound, the gate examines and decides the case at the gate, on the case, on soundness, and on the future problems test, namely whether the broken rule will cause problems later down the line, with no standing bad mark, no standing block, and no precedent. A staffing, audit form, or closure breach is not decidable at the gate; the step is recorded PARTIAL and RECYCLED under R-7. A corrected breach closes ordinarily. An uncorrected breach the gate lets stand closes CLOSED-QUALIFIED only under the bounded exception, decided by Captain JP on the presented case or by the Manager under the recorded grant at DQ-016, with four elements named in the step record: the element left unproven, here the breach standing uncorrected; the reason closure cannot or should not wait; the owner of the remainder; the release condition or date. The breach, examination, decision, and any later problems are also recorded in the step record.

Route two, trace short of 100 percent LANDED, for any reason including a breach causing the shortfall, is the same exception mechanism, as the source states. Only the bounded exception deciders may close it, Captain JP on the presented case or the Manager under the recorded grant at DQ-016, with all four elements named: the element left unproven; the reason closure cannot wait or should not wait; the owner of the remainder; the release condition or date. An exception closure missing any element does not stand. No exception covers an anomaly in how the closure evidence was produced. Where both routes apply, both records are made and each names the other.

No authority other than Captain JP on the presented case or the Manager under the recorded grant may record a qualified closure over outstanding elements or over an uncorrected breach. Point of use: OI-T03.

Plaid bar, at this recording act: at Plaid the bounded exception does not run and no closure records CLOSED-QUALIFIED; a step that would need either does not close at Plaid (PLAID.md line 124, DQ-119).

Point only, at this recording act: R-89, Trade-off Judge weighing (LEVEL-1-STANDING.md line 240); where a gate decision is irreversible, point to R-89 and restate none of it.

#### Fourth part: Ruling and mapping

The Auditor records the ruling in its three forms, its R-51 outcome, and its CLOSED state, under the mapping in Working tables. The CLOSED state is assigned as an inference, labelled as such: approved records as CLOSED-PASS; approved with required expansion records as CLOSED-PASS, the expansion being a condition on the next step plan, not a qualification of this step; not approved records in the recorded forms KILLED, SUSPENDED, or RECYCLED with the outcome, and those recorded forms are not CLOSED states. CLOSED-QUALIFIED is recorded wherever the qualification lies in the result itself, in the sense of the definitions in Working tables: a named bound, a recorded non-pass, a recorded deferral, a Go standing only under the bounded exception, or a closure let stand over an uncorrected breach under the bounded exception, the qualification named in every case, in the form `CLOSED-QUALIFIED. Qualification: [the qualification in words, naming the bound, the recorded non-pass, the recorded deferral, the bounded exception relied on, or the uncorrected breach let stand, as the case stands].` The exception and breach routes are examples, not an exhaustive list. The bounded exception is required for the cases the source reserves it for: closure over trace elements short of 100 percent LANDED, and closure let stand over an uncorrected breach. Point of use: OI-T01 and OI-T04, with Working tables A and B.

- Output: the verdict recorded, in its three forms, its R-51 outcome, and its CLOSED state, with any qualification named.
- Done condition: the verdict stands recorded in the R-51 vocabulary only, with its recorded state and qualification where one applies. No next step opens before Act 9 is complete.

### Act 9: Gate completed

- Input: the recorded verdict from Act 8 and the next step plan.
- Action, first part: the plan ruling is recorded as a named field, sufficient as written or expanded before that step starts, and it is not a gate outcome.
- Action, second part: commitment naming or the negative outcome element. For a Go, the commitment is made by the Manager, the role that commits resources and staffing, and the naming in the gate record is the commitment act. The Auditor checks the naming against one stated test, in full: every role the next step plan requires carries a named seat or a named spawn intention, and every committed resource is identified, recorded in the form `Commitment, made by the Manager, naming as the commitment act: [each role the next step plan requires, with its named seat or named spawn intention]; resources: [each committed resource identified]. Test: every required role carries a named seat or a named spawn intention, and every committed resource is identified: [pass / fail].` A named spawn intention names the role, the number of seats or the named source the seats are drawn from, and the step it serves; an identified resource names the resource and its amount, its location, or its account; a naming missing those elements fails the test and a Go may not be recorded on it. The merits of sufficiency beyond that test belong to the board, which may refuse a Go or require expansion. A Go with no commitment recorded is not a Go. Where expansion is required, the commitment record names the additions the next step plan must carry, each with a distinct scope and a unique role; the additions stand in the core record under Outputs, and the expanded plan is the plan the next step opens on. For a not approved outcome, its one named element is recorded: the release condition and lift authority for Hold, or the stage returned to for Recycle.
- Action, third part: annex owed marking. The record is presented as one record on one page under Outputs, and every annex line stands marked not triggered, owed, or complete, with an annex item owed but not yet written recorded as owed, with an owner, in the form `[annex line name]: owed. Owner: [name or role].`, never silently filled later.
- Output: the completed gate record, as one record on one page under Outputs.
- Done condition: the core record stands complete, the plan ruling stands as a named field, for a Go the commitment naming passes the stated test, and every annex line stands marked. No next step opens before this condition holds.

### Act 10: Opening and discharge

- Input: the completed gate record from Act 9.
- Action: on approval, the next step opens, on the expanded plan where expansion was required. Without approval it does not open. Follow through recording, split: for Hold, Recycle, and Kill, the owner and the next check or re-presentation date stand in the core record under Outputs, and the annex carries the outcome with its named elements and where the follow through record lives. Watching, re-presentation, and resource release mechanics are pointed to the build record keeping and queue rules, not prescribed here. Remainder discharge after a bounded exception is prescribed, because the source states its duties: the remainder is watched by its named owner, its outcome recorded in the build record when the release condition falls due, in the form `Remainder outcome: [element left unproven]; owner: [name or role, continuing from exception time unless replaced on the record]; release condition or date: [condition or date]; outcome on falling due: [completed / late, new linked instance under R-3 created / unmet, reported to the Auditor and filed to Captain JP queue as an open item]; record: [build record reference].`, a late completion creates the new linked instance under R-3, and an unmet remainder past its date is reported to the Auditor and filed to Captain JP queue as an open item. Owner continuity, a skill construction: owners named at exception time continue unless replaced on the record. An exception creates no class and no precedent.
- Output: the next step opened on the correct plan, or the step held, recycled, or killed with its follow through ownership recorded, and any remainder under active discharge.
- Done condition: the opening matches the ruling, and every negative outcome and every remainder has a named owner, a named date or condition, and a named record home.

## Gate not held

A gate that is not held produces no gate record. It produces a gate event only, in the step record, in this form:

```text
GATE EVENT: GATE NOT HELD
Step: [step name and number, copied exactly as recorded in the step record or the ledger entry for the step, including the word Stage where that is the recorded word; the form label Step is a field label only and is never a reason to rewrite the recorded name]
Words of record: gate not held
Reason: [reason in words]
Missing part or unmet precondition: [named, including checklist not drawn where that is the reason]
Blocker: [what blocks the gate]
Owner who will clear it: [name or role]
Date recorded: [the date this event is written, which must be no later than the day the step record closes for the sitting]
Second not held event on this step: [no / yes, referred to the decision queue]
Outcome word: none. CLOSED state: none. Gate record: none.
```

No outcome word is used, no CLOSED state is recorded, and the step does not advance. No fifth outcome word is created, a skill construction within the closed vocabulary.

Notice duty, OI-T07, a skill construction, in full in this section only: where a gate has not been held by the time the step record closes for the sitting, a gate not held event is recorded that day, naming the blocker and the owner who will clear it, and a second not held event on the same step goes to the decision queue. Where no step record closing date stands in the records, the date written is the date of the run or sitting at which the gate was attempted, recorded without qualification.

## Step 22 exception

Who governs: the Release-gate Keeper governs the Step 22 sitting under release-gate; this skill does not govern the sitting at all.

What this skill does there: it lists the Step 22 acts in the Keeper form, briefly, and records that no Auditor ruling issues there.

- Input: a build reaching Step 22, the release gate step.
- Action, a skill construction, the acts in a short list: a board chaired by the Release-gate Keeper; the outcome recorded in the four outcome form; the Keeper pass or fail act, recorded as the Keeper act in the gate record, distinct from the four outcome form (source passage S5); the red flag check run by the Keeper for the build as a whole; no Auditor ruling; no Auditor plan ruling. Step 23 opens on the Keeper verdict. The release gate checklist belongs to the release-gate skill and is pointed to, not restated. Both board form statements are carried: no stage is excepted from the board form or the gate outcome form, and the carve out governs at Step 22 only in the Keeper form. Point of use: OI-T08.
- Output: no Auditor gate record for Step 22. The approval that opens Step 23 is the Release-gate Keeper verdict under R-27.
- Done condition: no second Auditor ruling has issued on Step 22.
- Stated limit, OI-T06, in full at this section: whether any plan ruling exists in Keeper form at Step 22 is not stated by the source, and the skill does not state it.
- Stated limit, OI-T06, in full at this section: at Step 22 Captain JP general closure authority is not exercised through this skill, because the Keeper verdict governs under the exception and under live gate precedence.

## Step 23 review

Who governs: the Auditor governs and owns this review at build close, hosted at Step 23.

What this skill does there: it reviews the recorded gate outcomes for the whole build and carries the review line below; it does not re-run any step gate.

- Input: the recorded gate outcomes for the whole build, in gate record and ledger form, including pattern outcomes under R-223, and the step records carrying gate not held events.
- Action: the Auditor reviews the recorded gate outcomes per build. The review line lists, per step, the number of not held events recorded before the step ruling, drawn from the step records, in this form, so repeated not held events followed by a Go are visible:

```text
STEP 23 REVIEW LINE
Step: [step name and number]
Ruling recorded: [ruling form; R-51 outcome; recorded CLOSED state, with qualification where one stands]
Gate not held events before this ruling, count: [number, drawn from the step record]
All Go prompt: [this build shows an all Go distribution up to this step: yes / no; a prompt for the review only, not a reclassification]
Reclassification: [none / reclassified as a status meeting, not a gate, evidence: reference to the review evidence]
Consequence where reclassified: [stage reopened and recorded RECYCLED to: stage name; re-presentation required before closure: yes]
```

An all Go distribution is reported as a prompt for the review, not by itself a reclassification. A gate is reclassified as a status meeting, not a gate, only on evidence from the review that its criteria were not checked or its decider lacked authority. The F-8 distribution is unchanged and still counts approval rows only.

- Output: the gate outcome review record in the design repo, cited in the Step 23 record, with any reclassification and its evidence recorded, the report going to Captain JP.
- Done condition: the review record stands cited in the Step 23 record. Where a gate is reclassified, the stage it passed and every later stage whose closure rested on that passage is reopened, recorded RECYCLED to the reclassified gate stage, and re-presented to a gate meeting R-51 before closing again. The build must not close at Step 23 while such a stage stands unexamined again, and a closure recorded on such a stage does not stand.

## Outputs

One gate produces one of three output forms. This section is the single statement of the output forms; Acts 8 and 9 assemble to it. The gate record is one record on one page: a core block, then an annex block directly beneath it. Every annex line appears in every record, marked not triggered, owed, or complete, so absence is a visible state, never a missing section. Annex material other than the flag naming block is linked by reference rather than restated; the flag naming block stands inside the gate record itself, in the annex. The core block is complete before the next step opens, its contents in one sentence: step and tier; board members and chair standing; the ruling in the three forms; the R-51 outcome; the recorded CLOSED state with any qualification named; the plan ruling; for a Go, the commitment naming, or, for a not approved outcome, its one named element (Hold: release condition and lift authority; Recycle: stage returned to); expansion additions where the ruling is approved with required expansion; and, for every negative outcome, its owner and next check or re-presentation date. The annex contents in one sentence: packet parts present or missing; checklist drawn; the red flag naming block inside the annex, in the companion recorded forms, including its not named state where the companion form has it; attested closure check result; breach case entries; the Plaid verification reference; remainder entries; and, for every negative outcome, where the follow through record lives. The gate event is the only output where a gate is not held, in the form in Gate not held. The review line stands at Step 23 only, in the form in Step 23 review.

Gate record. One record on one page. The record is not complete while any annex line stands marked owed.

```text
GATE RECORD: CORE
Step: [step name and number, copied exactly as recorded in the step record or the ledger entry for the step, including the word Stage where that is the recorded word; the form label Step is a field label only and is never a reason to rewrite the recorded name]
Tier: [tier recorded for the step]
Board chair: [name, standing: chair, spawn record reference]
Board members: [name, spawn record reference]; [name, spawn record reference]; [further members as seated]
Ruling form: [approved / approved with required expansion / not approved]
R-51 outcome: [Go / Kill / Hold / Recycle]
Recorded CLOSED state: [state, with qualification named where the state is CLOSED-QUALIFIED, in the form at Act 8, fourth part]
Plan ruling, Auditor named field, not a gate outcome: [sufficient as written / expanded before that step starts, additions named below]
Commitment naming, for a Go only, in the form at Act 9: [Manager naming, where a named spawn intention names the role, the number of seats or the named source the seats are drawn from, and the step it serves, and an identified resource names the resource and its amount, its location, or its account; a naming missing those elements fails the test and a Go may not be recorded on it; or: not a Go, no commitment stands]
Expansion additions, where the ruling is approved with required expansion: [each addition, distinct scope, unique role; or: none]
Negative outcome element, for a not approved outcome only: [for Hold: release condition and lift authority; for Recycle: stage returned to, in its recorded form; for Kill: none beyond the outcome]
Negative outcome owner, for every negative outcome: [name or role]
Next check or re-presentation date, for every negative outcome: [date or named condition]
Auditor bar or dissent, where one stands: [bar with the failed closure condition or gate bar cited, or dissent in the one line form, or: none]
```

The record is not complete while any annex line stands marked owed.

```text
GATE RECORD: ANNEX
Packet parts present or missing: [not triggered / owed / complete] [if owed, write: owed. Owner: name or role] [snapshot: present / missing; skip summary: present / missing; Estate Keeper report: present / missing; gate policy entry: present, status wording used] [owner where owed]
Checklist drawn: [not triggered / owed / complete] [drawer named, drawn from the stated preconditions: yes / no] [owner where owed]
Red flag naming block, standing inside this gate record: [not triggered / owed / complete] [owner where owed]
Naming block, in the red-flag-check recorded forms, copied in full inside this record, a linked or filed outside copy does not count: [each flag, in the companion form order: flag name; named present / absent / not named, where the companion form has the not named state; evidence reference as the companion form states it]
[further flags in the same form, one line per flag, until every flag in the companion list stands named inside this block]
Attested closure check result: [not triggered / owed / complete] [result at grade L2, performer name and standing] [owner where owed]
Breach case entries: [not triggered / owed / complete] [breach, examination, decision, route used, exception reference where one stands, or: no breach case] [owner where owed]
Plaid verification reference: [not triggered / owed / complete] [verification record reference, performer name and standing, or: not at Plaid] [owner where owed]
Remainder entries: [not triggered / owed / complete] [each remainder: element left unproven, owner, release condition or date, record home, or: no remainder] [owner where owed]
Follow through record location, for every negative outcome: [not triggered / owed / complete] [where the follow through record lives] [owner where owed]
```

Every blank in a copied record is filled or struck with a reason; an empty blank is an incomplete record.

Fictional miniature, form only, facts invented, no precedent. Miniature one: a fictional Go record, filled from the templates above.

```text
GATE RECORD: CORE
Step: Step 4, Example step
Tier: Medium
Board chair: A. Chair, standing: chair, spawn record SR-1
Board members: B. Member, SR-2; C. Member, SR-3
Ruling form: approved
R-51 outcome: Go
Recorded CLOSED state: CLOSED-PASS
Plan ruling, Auditor named field, not a gate outcome: sufficient as written
Commitment naming, for a Go only: Commitment, made by the Manager, naming as the commitment act: Builder, named seat D. Builder; Reviewer, named spawn intention for the Reviewer role, one seat drawn from the reviewer pool, serving the next step; resources: build environment, location in the build records. Test: every required role carries a named seat or a named spawn intention, and every committed resource is identified: pass
Expansion additions: none
Negative outcome element: none
Negative outcome owner: none
Next check or re-presentation date: none
Auditor bar or dissent: none
GATE RECORD: ANNEX
Packet parts present or missing: complete. Snapshot: present; skip summary: present; Estate Keeper report: present; gate policy entry: present, a policy entry follows.
Checklist drawn: complete. Drawer named, drawn from the stated preconditions: yes.
Red flag naming block, standing inside this gate record: complete.
Naming block, in the red-flag-check recorded forms, copied in full inside this record: Flag one; named absent; evidence reference EF-1.
Attested closure check result: complete. Result at grade L2, Auditor, standing recorded.
Breach case entries: not triggered. No breach case.
Plaid verification reference: not triggered. Not at Plaid.
Remainder entries: not triggered. No remainder.
Follow through record location: not triggered.
```

Fictional miniature, form only, facts invented, no precedent. Miniature two: a fictional gate not held event, from the gate event form.

```text
GATE EVENT: GATE NOT HELD
Step: Step 4, Example step
Words of record: gate not held
Reason: checklist not drawn
Missing part or unmet precondition: checklist not drawn
Blocker: no checklist drawn from the stated preconditions
Owner who will clear it: step record keeper
Date recorded: the date this event is written
Second not held event on this step: no
Outcome word: none. CLOSED state: none. Gate record: none.
```

Both miniatures show form only, are traced to the record forms above, and carry no precedent. Miniature two carries no outcome word and no CLOSED state beyond the none statements in its form.

## Edge cases

Each entry changes the handling of its case only; the rest of the gate runs as stated.

- Board and Auditor split on approval (Act 8): board verdict rules, subject to the Auditor bar; other dissent is recorded.
- Missing snapshot, seated board (Acts 2 and 8): sitting runs, gap recorded, board may Hold or Recycle.
- Missing Estate Keeper report (Act 2): sitting barred; gate not held event recorded.
- Missing skip summary (Act 2): as for the snapshot; gap recorded, sitting runs.
- Policy status not checked (Act 3): sitting may run; no Go recorded.
- No checklist, wrong source, or killer test omission (Precondition 2): pause point does not run; step does not advance.
- Plaid, only verifier holds a build seat (Act 4): no outside verifier; gate cannot be recorded fully compliant.
- Plaid step needing the bounded exception or qualified closure (Acts 4 and 8): step does not close at Plaid.
- Minor uncorrected breach, no exception decider available (Act 8, route one): no qualified closure recorded on that route.
- Breach in an excluded category (Act 8, route one): staffing, audit form, or closure breach records PARTIAL and RECYCLED.
- Trace shortfall caused by the breach itself (Act 8, both routes): both records made, each naming the other.
- Present protected flag; check not run (Act 5, second subcheck): closure blocks until remedied and recorded, or carried under governing rules; an unrun check bars advance.
- Auditor commissioned the work (Acts 5, 6, and 7): commissioning bar applies in full; clear assessor chairs.
- Go without a passing commitment naming (Act 9): not a Go, not recorded as one.
- Only this skill loaded (Act 5, second subcheck): load red-flag-check before naming any flag.
- Repeated not held events, one step (Gate not held; Step 23 review): second event to the decision queue; all count in the review line.
- Ending without a packet (Inputs): classified under R-250, pointed to, not argued at the gate.
- Step 22 reached in Auditor form (Step 22 exception): no Auditor ruling issues, whatever the request form.

## Never-do list

Point of use prohibitions also stand inside the acts; every prohibition here binds every gate run.

- Never record a gate outcome in any word outside Go, Kill, Hold, and Recycle, and never create a fifth outcome word for a gate that is not held.
- Never record a Go without the commitment naming, and never treat a Go with none recorded as a Go.
- Never treat the plan ruling as a gate outcome.
- Never open the next step without approval, or on the unexpanded plan where expansion was required.
- Never treat the step snapshot as a criterion for the ruling.
- Never advance a step where the red flag check was not run.
- Never let a coordinator report close a stage.
- Never rule on, chair, or run attested checks on work the Auditor commissioned.
- Never waive the 100 percent LANDED trace condition by ruling, and never record a bounded exception closure with any one of its four elements missing.
- Never count board members toward a team or board minimum, or seat them instead of mandated staffing.
- Never issue a second Auditor ruling at Step 22, and never use Captain JP general closure authority through this skill to pass, fail, or overturn a live release gate.
- Never treat a broken rule decision or bounded exception as precedent, class, or entitlement.
- Never treat a qualified record as satisfying a later bar requiring a pass; the qualification travels with every citation.
- Never silently fill an owed annex item; record it as owed, with an owner.
- Never restate pointed material as if the restatement were the rule; where this skill and the documents disagree, the documents win.

## Boundary

A task that belongs to a neighbour is routed there, not worked here.

| Neighbour | Load this gate skill, not the neighbour, when | Load the neighbour, not this gate skill, when |
|---|---|---|
| skip-checklist | A finished step waits on its gate and the packet must carry the skip summary. | A move inside a step is to be adopted or skipped, or a claimed skip must be run through the six questions. |
| requirement-grammar | A gate ruling or a plan ruling is being made or carried as a record field. | Statement level artefacts only: drafting, presence checking, or failure cases for statements in a brief, a plan, or a new rule. |
| audit-run | The gate internal audit runs under this skill judging act, ending in a ruling. | An audit round as such runs, with no gate ruling; audit-run governs audit rounds as such. |
| release-gate | Any step other than Step 22 is at its gate, and at Step 22 only to record that no Auditor ruling issues there. | Step 22 itself, and any repo about to be called shipped, with the Keeper alone passing or failing it. |
| build-flow | One step gate is being run now, with packet, board, and ruling. | The flow as a whole is being stated, ordered, planned, or started. |
| principles-check | The question is the gate outcome, the plan ruling, or the closure state. Where a task asks for a gate ruling and a principles check together, both load jointly under the joint load line in When to use. | Work or a decision must be checked against the adopted principles set, principle by principle, where no gate ruling is asked for in the same task. |
| team-staffing | The gate judges a finished step as actually staffed, including a PARTIAL shortfall. | A team is being seated, or a short stage is being restaffed. |
| verified_fold_trace | The gate tests the fold trace as a closure condition and any bounded exception. | Decisions must be folded into a target and traced element by element, repaired, and re-traced. |
| grill-mode | A gate must be run under rules already settled. | A plan, design, or build is still undecided and must be interviewed until decided. |
| red-flag-check | The gate as a whole is being run, with the check inside it as one part. | Flags must be named in that skill recorded forms for a ruling or record, or a remedy recheck, dispute recheck, or completion of a partial check on a ruling already written, and its recorded forms include the not named state where the companion form has it. |

Red-flag-check: the check runs inside this gate; a step does not advance where it was not run. Until red-flag-check is released into ~/workspace/custom-skills/, the companion loads from its build draft in its build folder; on release the catalogue copy governs. Ownership stays split: this gate owns the ruling; the neighbour owns the check, its flag list, evidence set, judging, and naming block. This skill names it as a required companion, so the pairing is designed, not discovered mid gate.

Release-gate: the Step 22 exception is total for the Auditor form; no second Auditor ruling issues. The board and outcome forms still apply at Step 22 in Keeper form, and the row covers any repo about to be called shipped, not only Step 22. At a live gate the Keeper verdict stands; a ruling bearing on the gate changes rules for later builds, not the verdict of a gate already sitting. Where a task asks both for a step gate and for the judgement that a repo is fit to be called shipped, release-gate governs the shipment judgement and this skill governs the step ruling; neither substitutes for the other, at any step, not only at Step 22.

Principles-check: where a task asks for a gate ruling and a principles check together, principles-check loads alongside this skill, its breaches are inputs the gate must deal with, and neither half of the task may be dropped for the other.

Audit-run: the gate internal audit runs under this skill judging act, ending in a ruling that opens or bars the next step; audit-run governs audit rounds as such, ending in findings, a register, and a round verdict. The two must not be merged; the precedence line in When to use governs when both match.

Skip-checklist: the skip summary is a packet item; the six answers and return trigger sit in the step record claiming the skip, not in the packet. The claim check belongs to that skill. This gate receives the summary and does not re-run the six questions. That skill states on its face it is never for Auditor gates or stage closure.

## Reference

Pointed material only, name and home only, no restatement.

- Attested closure checks, R-80.
- Layout and links, R-79.
- Checklist form and running, R-61, R-62, R-63, including the killer test.
- Roster and tier rules, R-29, R-30, R-4.
- Severity rules in force.
- Re-measurement, R-256; packetless endings, R-250.
- Pattern outcomes, R-223; F-8 distribution.
- Decision queue records DQ-006, DQ-010, DQ-016, DQ-065, DQ-113, DQ-119, DQ-120, DQ-128, DQ-147, including the DQ-016 grant and bounds and the DQ-119 Plaid bar at PLAID.md line 124.
- R-54, LEVEL-3-TEAMS.md line 114, at Act 6; R-71, LEVEL-3-TEAMS.md line 120, at Act 6; R-89, LEVEL-1-STANDING.md line 240, at Act 8.
- Assessor eligibility, R-73; closures that do not stand, R-90.
- Full R-3 state set; R-8 verdict form.
- Full Auditor job, auditor.md.
- Snapshot production, REPORTING.md.
- Skip summary definition, LEVEL-1 under Skipping a move.

The referred rules are not restated in this skill, and where this skill and the documents disagree, the documents win.

## Limits index

One line per limit, name and pointer only, no restatement.

- OI-T01: Act 8 and Working table A.
- OI-T02: Acts 7 and 8.
- OI-T03: Act 8, third part.
- OI-T04: Act 8 and Working table B.
- OI-T05: Act 4.
- OI-T06: Step 22 exception.
- OI-T07: Gate not held in full; pointers only at Preconditions, Acts 1 and 2, and Outputs; visibility rule at Step 23 review.
- OI-T08: Step 22 exception.
- Keeper form plan ruling at Step 22: Step 22 exception.
- Referred rules not restated, Q12: Reference.
- Step and stage wording join, Q15: Procedure introduction and Precondition 1.
- Closure state assignment as an inference, Q03: Act 8 and Working table B.
- CLOSED-FAIL limit: Working table B.
