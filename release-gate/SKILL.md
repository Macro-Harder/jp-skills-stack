# Release Gate

Quick version, written 2026-11-14 outside the build flow. The gate's full definition lives in ~/workspace/build-flow/LEVEL-2-STEPS.md and LEVEL-1-STANDING.md. This skill is the loadable short form. Where this skill and the documents disagree, the documents win.

Use this skill at the release gate stage of any build, and as the checklist for any repo about to be called shipped.

## The gate

The release-gate keeper owns this checklist end to end and alone passes or fails it. Every item is checked on evidence, not on the build's own say-so.

1. Clean clone sweep: clone the public repo fresh and sweep the whole tree, file contents as well as file names, for design material, audit papers, registers, and anything else that is not the system, its tests, its README, and its license.
2. License and holder line: the public repo carries Apache 2.0, and the copyright holder line reads exactly "J.P. Picard aka Macro-Harder". Third-party work keeps its own license and credit, untouched.
3. No design material in the public repo: no briefs, plans, audit docs, or build-flow working papers. Benchmarks and eval harnesses are the exception; they ship.
4. No builder attribution: the repo never names an AI or agent as the thing that built it. No generated-by lines, no provenance stamps, no origin-story paragraphs. Agents named as the system's users are product content and stay.
5. No AI tells in the text: nothing reads as obviously AI-written. No em dashes anywhere, and never swap one for a hyphen or en dash; rewrite the sentence instead. Heavy dash use of any kind fails the check.
6. README: end-user content only. What the product is, what it does, how to install and use it. No build process, no registers, no step talk, no status narration. Where a product waits on something else being built before it works, say what it is and that it is not ready, and put no filler in.
7. Install verification: where the product installs, install it from the clean clone by the README's own steps and run it. A product that cannot be installed from its own instructions fails.
8. Suite green from the clean clone: the full test suite passes in the fresh clone, not only in the working tree.

## Verdicts

Pass, or fail with the failing items named. A failed gate sends the build back into its fix loops; the gate is re-run whole, not only on the fixed items. The gate result and its evidence go in the project's private design repo.
