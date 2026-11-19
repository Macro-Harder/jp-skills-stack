# Attempt to Break It

## What it is
This is a structured attack stage for a finished build. After normal testing and audit, a separate group tries to break the product on purpose. They use inputs and patterns that ordinary use would rarely produce: values at or past limits, malformed payloads, repeated submissions, wrong sequences, and abuse patterns such as trying to bypass a check or exhaust a shared resource.

Each successful break goes into an attack log organised by class, so patterns become visible. A single odd failure is a bug. Several failures in one class point to a weak boundary. Fixes are made one by one, each fix is audited, and the attackers return to test the same ground again plus new ground. The loop ends only when the product holds against the recorded attacks, or when the owner decides to stop it and accepts what remains open.

The separation of roles matters. Builders know how the product is meant to work and tend to test along those lines. Prior auditors have already formed a view of the code. Attackers start fresh and hostile, which is why they find different faults.

## Example
A form service passes its test suite. Attackers take it next. They submit a file name far longer than any field expects, a date set far in the past, an empty body with headers that claim content, and the same request sent many times in quick succession. Two cases crash a worker, one stores a truncated name that later breaks a lookup, and the repeated requests create duplicate records. Each result is logged under its class: boundary, malformed data, and abuse. Developers fix the length check, the storage rule, and the duplicate guard, each with a reproducing test first. Auditors check the fixes. Attackers re-run the whole log and add new variants. On the second pass the product holds, and the log is kept as the record.

## How to use it
Place the folder in the custom skills directory so an agent can load SKILL.md when this stage opens. A person using it supplies the built product, access to its real interface, the prior audit result, and a place to keep the attack log. The output is the log itself, the list of fixes, and a closing record that states what held and what, if anything, remains open.

## For agents
An agent running this stage must not attack its own build. Seat distinct attackers, keep the log complete even when a break is embarrassing, and never close the loop on a verbal assurance. Closure needs a re-run against the log. If a break cannot be fixed, say so in plain terms in the final report and in the log, with severity and impact unchanged.
