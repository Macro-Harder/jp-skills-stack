# Metrics and Reporting

Quick version, written 2026-11-14 outside the build flow. The metric definitions live in ~/workspace/build-flow/METRICS.md (39 metrics) and the reporting forms in ~/workspace/build-flow/REPORTING.md. This skill is the loadable short form. Where this skill and the documents disagree, the documents win.

Use this skill whenever a build reports status, fills a live-status snapshot, or counts anything that will be quoted.

## Counting rules

- Severity counts come from the round registers, never estimated. A snapshot carries critical, high, medium, and small counts, in that order, plus what is known and what is fixed.
- Total found is cumulative across rounds: if two rounds each find 20, the total reads 40. A re-report of the same round replaces that round's figure; it never adds it twice. Rounds are keyed by step and round number, not by label wording.
- Live agent counts come from the registry of what is actually running at the moment of the snapshot. Coordinators work in waves, so a low live count between waves is normal; the all-time spun total is the scale figure, and it never shrinks.
- Before any count is reported, reconcile it against its counting unit and its derivation: what kind of item was counted, and how the total was built. Counts of different kinds are never mixed into one figure.
- A figure whose source cannot be checked is labelled as unverified or left out, never presented as measured.

## Reporting rules

- Reports are brief: bullets, one line per item, the outcome first.
- A report states what finished, what failed, and what is next, with the evidence named (a push verified, a suite result, a register read).
- Coordinator claims are checked against the build's own records before they are passed on. A completion claim without its closing record stands as incomplete.
- Status text is cut down, never a wall of text. The full note sits behind the summary for anyone who opens it.
- Anything the reader must act on is surfaced directly, never buried inside a progress update.
