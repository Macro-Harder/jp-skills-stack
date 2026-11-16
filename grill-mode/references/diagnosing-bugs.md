# Diagnosing bugs: the six-phase loop

Adapted from the diagnosing-bugs skill in mattpocock/skills by Matt Pocock, MIT license. Skip a phase only when you can justify it in the reply.

## Phase 1: Build a feedback loop

This is the skill. Everything else is mechanical. Spend disproportionate effort here. Be aggressive, be creative, and refuse to give up.

Ways to construct a loop, in roughly this order:

1. Failing test at whatever seam reaches the bug: unit, integration, or end to end.
2. Curl or HTTP script against a running dev server.
3. CLI invocation with a fixture input, diffing stdout against a known-good snapshot.
4. Headless browser script that drives the UI and asserts on DOM, console, and network.
5. Replay a captured trace: save a real network request, payload, or event log to disk and replay it through the code path in isolation.
6. Throwaway harness: spin up a minimal subset of the system that exercises the bug code path with a single function call.
7. Property or fuzz loop: if the bug is sometimes-wrong output, run 1000 random inputs and look for the failure mode.
8. Bisection harness: if the bug appeared between two known states, automate boot at state X, check, and repeat, so you can bisect it.
9. Differential loop: run the same input through old version versus new version (or two configs) and diff outputs.
10. Human-in-the-loop bash script, last resort: if a human must click, drive them with a structured script so the loop is still structured.

Tighten the loop until it is fast (seconds, not minutes), deterministic (same verdict every run), and sharp (asserts on the exact symptom). For a flaky bug, loop the trigger 100 times, parallelise, add stress, and narrow timing windows until the reproduction rate is high enough to debug against.

If you genuinely cannot build a loop, stop and say so explicitly. List what you tried. Ask the user for access to the reproducing environment, a redacted captured artifact, or permission to add temporary instrumentation. Do not proceed to hypothesise without a loop.

Phase 1 is done when you can name one command you have already run at least once, that drives the actual bug code path, asserts the user's exact symptom, is deterministic, is fast, and is agent-runnable.

Redact every secret first: write `<REDACTED>` in its place. Build loops against environment variables, so the credential stays in the environment rather than in what you show. Captured artifacts carry auth headers: quote only the lines that carry the signal.

## Phase 2: Reproduce and minimise

Run the loop and watch it go red as the bug appears. Confirm the loop produces the failure mode the user described, not a different failure that happens to be nearby, and that it is reproducible across multiple runs.

Shrink the repro to the smallest scenario that still goes red. Cut inputs, callers, config, data, and steps one at a time, re-running the loop after each cut, and keep only what is load-bearing. Done when every remaining element is load-bearing: removing any one of them makes the loop go green.

## Phase 3: Hypothesise

Generate 3 to 5 ranked hypotheses before testing any of them. Each hypothesis must be falsifiable, stated as a prediction: "If X is the cause, then changing Y will make the bug disappear, or changing Z will make it worse." If you cannot state the prediction, discard or sharpen the hypothesis. Show the ranked list to the user before testing; they often have domain knowledge that re-ranks it instantly.

## Phase 4: Instrument

Each probe must map to a specific prediction from Phase 3. Change one variable at a time. Prefer a debugger or REPL inspection, then targeted logs at the boundaries that distinguish hypotheses. Never log everything and grep. Tag every debug log with a unique prefix, for example `[DEBUG-a4f2]`, so cleanup is a single grep. For performance regressions, logs are usually wrong: establish a baseline measurement first, then bisect.

## Phase 5: Fix and regression test

Write the regression test before the fix, but only if there is a correct seam for it: one where the test exercises the real bug pattern as it occurs at the call site. If the only available seam is too shallow, a regression test there gives false confidence, and the absence of a seam is itself the finding: the architecture is preventing the bug from being locked down. Flag it.

When a correct seam exists: turn the minimised repro into a failing test at that seam, watch it fail, apply the fix, watch it pass, then re-run the Phase 1 loop against the original un-minimised scenario.

## Phase 6: Cleanup

Required before declaring done:

- Original repro no longer reproduces (re-run the Phase 1 loop)
- Regression test passes, or the absence of a seam is documented
- All `[DEBUG-...]` instrumentation removed
- Throwaway prototypes deleted, or moved to a clearly marked debug location
- The hypothesis that turned out correct is stated in the commit or pull request message
