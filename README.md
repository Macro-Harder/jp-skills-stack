# JP skills stack

A stack of agent skills. A skill is a reusable procedure an agent loads on its own when a request matches it, and then follows cold. Each skill sits in its own folder with its SKILL.md and a README that explains what it is, gives an example, and says how to use it.

- [A2A 1.1 Readiness](a2a-1-1-readiness/) records the standing position on A2A version 1.1 for planning and design work, and what 1.1 would change.
- [A2A Card Signing](a2a-card-signing/) covers producing and verifying signed A2A Agent Cards.
- [A2A Version Negotiation](a2a-version-negotiation/) covers version negotiation for A2A surfaces that may meet a peer of a different generation.
- [Agent Admission Pipeline](agent-admission-pipeline/) admits a new agent, model, or harness version through six stages, each exiting on a paired comparison verdict against the incumbent.
- [Arbitration Protocol](arbitration-protocol/) settles a disputed eval case in seven steps: freeze, transcript, classify, fix, rule, override, and the eval-wrong ratio.
- [Attempt to Break It](attempt-to-break-it/) attacks the built product adversarially with independent attackers, fixes what breaks, and loops until it holds.
- [Audit Independence](audit-independence/) establishes an auditor independence by naming five threats and dispositioning each one before any audit work counts.
- [Audit Run](audit-run/) is the short form for running an audit inside a build: loop, logic, test, and finished product audits.
- [Auditor Approval Gate](auditor-approval-gate/) runs the Auditor approval gate on a finished build flow step, from packet to recorded ruling.
- [Brainstew Use](brainstew-use/) covers how to use Brainstew, a build's shared memory, on a build that has it installed.
- [Build Flow](build-flow/) is the short form for running a build in the right order with the right gates.
- [Context Fork Handoff](context-fork-handoff/) hands work to a subagent by forking the session with full context, working in series with retrieval, or splitting into fresh parallel sessions, instead of losing information in a summary brief.
- [Coordinator Succession and Handover](coordinator_succession/) covers handing a multi agent build over between coordinators without a silent stop.
- [Count and Total Reconciliation](count_reconciliation/) reconciles a count or total against its counting unit and derivation before it is reported.
- [Delegated Work Closeout Verification](delegated_work_closeout/) recovers and verifies the true state of delegated work when an agent ends without a final report.
- [Document Checking](document-checking/) checks a brief or plan as a document in two separate passes, verification of its statements and validation against the decisions they came from.
- [Experimenter Method](experimenter-method/) turns a contested, load-bearing assumption into a falsifiable test, with hypothesis, metric, falsifying result, and selector criteria fixed before the run, and judges whether a run offered as proof counts as a test.
- [Failed Node Retry](failed-node-retry/) maps a multi-agent job as a graph with owners and verifiers, and on failure re-runs only the failed nodes, never the whole batch.
- [Fresh Eyes Review](fresh-eyes-review/) splits a memory-rich builder session from a memory-free reviewer, so finished work is read by a stranger with no history in it.
- [Grill Mode](grill-mode/) interviews the user before building anything, so the plan is decided first instead of guessed.
- [Guardrail Layer Audit](guardrail-layer-audit/) audits an agent guardrails layer by layer and replaces controls that only inspect text with controls that remove the capability.
- [Handoff Timing](handoff-timing/) produces the timing line that rides with a counting report in chat, with each figure labelled measured or derived.
- [Harness Cost Tuning](harness-cost-tuning/) tunes an agent harness from its execution logs, one mechanism at a time, keeping or discarding each change on measured quality and cost gates.
- [Judge Validation](judge-validation/) validates an automated judge end to end: blind human labelling, blind judging, kappa comparison, a swap test, disagreement review, and rubric iteration.
- [Live Proof](live-proof/) runs the finished product on the real system it was built for with real work, and records a verdict that names anything the run did not carry.
- [MCP Era Migration](mcp-era-migration/) covers moving an MCP server from the handshake era toward the stateless spec revision.
- [MCP Server Security Review](mcp-server-security-review/) audits an MCP server before it is trusted, and again when its tools, transport, or auth change.
- [Metrics and Reporting](metrics-and-reporting/) sets the counting and reporting rules for a build whenever it reports status or counts anything.
- [rag-muse](muse-rag/) is hybrid BM25 and vector search over the user's own notes and memory files, with cited, provenance labelled results.
- [Note-Taking Team](note-taking-team/) runs a note taking team over a primary source before a build or decision rests on it.
- [Pattern Gate](pattern-gate/) runs the gate for adopting or removing a design pattern, on a complete gate record filed before any outcome.
- [Pattern Skip Test](pattern-skip-test/) puts six questions to a pattern proposal, and any field answered no means skip for now.
- [Principles Check](principles-check/) is the procedure for checking work against an adopted set of build principles.
- [Push Discipline](push-discipline/) sets the rules for pushing work to GitHub during a build.
- [Red Flag Check](red-flag-check/) names each of the eleven annex red flags present or absent inside a step ruling or gate record at an approval gate or the release gate.
- [Release Gate](release-gate/) is the checklist for the release gate stage of a build, and for any repo about to be called shipped.
- [Repo Content Sweep](repo_content_sweep/) sweeps a shipped repo tree for banned content inside file contents, not only in file names.
- [Requirement Grammar](requirement-grammar/) writes requirement statements in a defined grammar and runs presence checks over the stated forms.
- [Skill Retirement Test](skill-retirement-test/) re-tests each existing skill against the bare model on a fixed set of real tasks, and keeps, revises, or deletes it on that evidence.
- [Ruling Walkthrough Pacing](ruling_walkthrough_pacing/) walks a user through a pre existing list of questions or rulings at the pace and format the user sets.
- [Skip Checklist](skip-checklist/) is used before adopting or skipping a move inside a build flow step, and when a step record claims or omits a move.
- [Team Staffing](team-staffing/) gives the team sizes and staffing rules for seating a team at any stage of a build, by tier.
- [The Charge](the-charge/) opens an audit or review round on a written charge naming scope, success criteria, agenda, criteria, and materials, agreed before examination.
- [Tool Evaluation Checklist](tool-evaluation-checklist/) maps any tool considered for eval-driven development against the twelve harness primitives before adoption.
- [Use-It Loop](use-it-loop/) has a first user who never built the product drive the real interface through real work, fixes what real use breaks, and loops until it holds.
- [Verified Fold and Trace](verified_fold_trace/) verifies that every agreed decision actually landed in a large document or codebase, element by element.
- [Working Loop Start](working-loop-start/) runs the first two steps of the eval-driven working loop: spec one behaviour and pass the two-expert test, then build the eval first and watch it fail in the right places.
- [Write Tests, Audit Test](write-tests-audit-test/) writes and audits the tests for a build step at Step 13, before the code they test exists.

Licensed under Apache 2.0. Copyright 2026 J.P. Picard aka Macro-Harder.
