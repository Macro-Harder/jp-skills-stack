# Use-It Loop

## What it is
The use-it loop is the stage where a built product meets real use for the first time. It runs after the build and its audit loop, and before any deliberate attempt to break the product. Audits check the product against its design. This loop checks the product against a person trying to get work done.

The driver is a first user: someone who has never built the thing. That freshness is the whole point. Builders already know where things are, what words mean, and which order steps expect. A first user knows none of that, so every confusing step, missing input, awkward order, and unclear phrase shows up at once, in the way it will show up for real users later.

The first user is given real work, not a tour. They drive the actual interface from the start of a task to the end, unaided. Everything that breaks or slows them down is written down. Each finding is fixed, each fix is audited, and the loop runs again. It closes only when a full session of real work holds clean, and that closing session is recorded.

## Example
A small invoicing tool has passed its build audit. A bookkeeper who had no part in building it is asked to do a normal morning task: enter three invoices, send one to a client, and produce a summary for the month.

She finds the send action only after checking two menus, because the label uses a term her office does not use. She cannot enter the third invoice because there is no field for a purchase order number her clients require. She also completes the steps in a different order than the tool expects and loses her entries once.

All three findings are recorded. The label is rewritten in plain office language, the missing field is added, and the order problem is fixed so entries survive either sequence. Each fix is audited. The bookkeeper then runs a fresh morning task, including the cases that failed, and completes it without stalls. That clean run, with her name, the work, the findings, and the fixes, becomes the session record that closes the loop.

## How to use it
Place this folder in the skills directory so an agent can load SKILL.md at this stage of a build. The build team supplies the working product, its real interface, and real tasks drawn from what actual users do. The coordinator supplies a genuine first user and protects the session from coaching or interference.

Sessions need no special tooling. They need a place to record findings as they happen and a record to file at the end.

## For agents
An agent coordinating this loop guards the independence of the first user. It does not let a builder take the seat, does not hand the user a script, and does not explain confusing parts during the run. After the run, the agent makes sure every finding is either fixed and audited or sent to the owner as a design question, and that the closing session record is complete before the stage is marked closed.
