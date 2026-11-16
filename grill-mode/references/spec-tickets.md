# Spec and ticket templates

Adapted from the to-spec and to-tickets skills in mattpocock/skills by Matt Pocock, MIT license.

## Spec template

```md
## Problem Statement

The problem the user faces, from the user's perspective.

## Solution

The solution to the problem, from the user's perspective.

## User Stories

A long, numbered list of user stories, each in this format:

1. As an <actor>, I want a <feature>, so that <benefit>

## Implementation Decisions

- The modules that will be built or modified
- The interfaces of those modules that will be modified
- Technical clarifications from the developer
- Architectural decisions
- Schema changes
- API contracts
- Specific interactions

## Testing Decisions

- What makes a good test (only test external behaviour, not implementation details)
- Which modules will be tested
- Prior art for the tests (similar types of tests already in the codebase)

## Out of Scope

The things that are out of scope for this spec.

## Further Notes

Any further notes about the feature.
```

Do not include specific file paths or code snippets. They go stale fast. The one exception is a prototype snippet that encodes a decision more precisely than prose can, trimmed to the decision-rich parts, with a note that it came from a prototype.

## Local ticket template

One file per ticket, under `.scratch/<feature>/issues/`, numbered from `01` in dependency order (blockers first).

```md
# <NN>: <Ticket title>

**What to build:** the end-to-end behaviour this ticket makes work, from the user's perspective, not a layer-by-layer implementation list.

**Blocked by:** the numbers and titles of the tickets that gate this one, or "None (can start immediately)".

**Status:** ready-for-agent

- [ ] Acceptance criterion 1
- [ ] Acceptance criterion 2
```

## Vertical slice rules

- Each slice cuts a narrow but complete path through every layer (schema, API, UI, tests). Vertical, not a horizontal slice of one layer.
- A completed slice is demoable or verifiable on its own.
- Each slice is sized to fit in a single fresh context window.
- Any prefactoring is done first, as its own ticket.

## Wide refactor exception

A wide refactor is one mechanical change (rename a column, retype a shared symbol) whose blast radius fans across the whole codebase, so no vertical slice can land green. Do not force it into a tracer bullet. Sequence it as expand, then contract:

1. Expand: add the new form beside the old so nothing breaks.
2. Migrate the call sites over in batches sized by blast radius (per package, per directory), each batch its own ticket blocked by the expand, keeping CI green batch to batch because the old form still exists.
3. Contract: delete the old form once no caller remains, in a ticket blocked by every migrate batch.
