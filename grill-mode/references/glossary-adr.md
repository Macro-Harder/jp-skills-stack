# Glossary and ADR formats

Adapted from the domain-modeling skill in mattpocock/skills by Matt Pocock, MIT license.

## GLOSSARY.md format

One file per context. Single-context repos keep one `GLOSSARY.md` at the repo root. Multi-context repos keep a root `GLOSSARY-MAP.md` that lists each context and where its glossary lives, with one `GLOSSARY.md` per context.

```md
# {Context Name}

{One or two sentence description of what this context is and why it exists.}

## Language

**Order**:
{A one or two sentence description of the term}
_Avoid_: Purchase, transaction

**Invoice**:
A request for payment sent to a customer after delivery.
_Avoid_: Bill, payment request

**Customer**:
A person or organization that places orders.
_Avoid_: Client, buyer, account
```

Rules:

- Be opinionated. When several words exist for one concept, pick the best one and list the others under `_Avoid_`.
- Keep definitions tight. One or two sentences at most. Define what the term IS, not what it does.
- Only include terms specific to this project's context. General programming concepts do not belong, even if the project uses them a lot.
- Group terms under subheadings when natural clusters emerge. A flat list is fine when everything belongs to one cohesive area.
- Keep the glossary free of implementation details. It is a glossary and nothing else.

## ADR format

ADRs live in `docs/adr/` with sequential numbering: `0001-slug.md`, `0002-slug.md`, and so on. Scan the directory for the highest existing number and increment by one. Create the directory lazily, only when the first ADR is needed.

```md
# {Short title of the decision}

{1 to 3 sentences: what is the context, what did we decide, and why.}
```

That is the whole template. An ADR can be a single paragraph. The value is in recording that a decision was made and why, not in filling out sections.

Optional sections, only when they add genuine value:

- Status frontmatter: proposed, accepted, deprecated, or superseded by ADR-NNNN. Useful when decisions are revisited.
- Considered Options: only when the rejected alternatives are worth remembering.
- Consequences: only when non-obvious downstream effects need to be called out.

Offer an ADR only when all three are true: the decision is hard to reverse, a future reader would wonder why it was done this way, and it came from a real trade-off between genuine alternatives.

What qualifies: architectural shape, integration patterns between contexts, technology choices that carry lock-in, boundary and scope decisions (including explicit no's), deliberate deviations from the obvious path, constraints not visible in the code, and rejected alternatives when the rejection is non-obvious.
