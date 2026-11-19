---
name: guardrail-layer-audit
description: Audit an agent guardrail stack layer by layer and replace text inspection controls with capability removal where possible. Load when reviewing agent safety controls, tool permissions, or sandbox scope.
---

# Guardrail Layer Audit

This skill is distilled from entry 38 (@sermakarevich) in the ranked X-posts library, voice-to-prompt-per-post-advanced.md, rewritten from the idea in original words.

## Purpose

Test whether each guardrail still holds when an attacker adapts to it. Judge controls by what the agent can actually do in practice, not by what instruction text says it should do.

## Procedure

1. List the agent, its tools, its data sources, and every action it can take without asking a person.
2. Walk the layers in order. First, controls before the model, such as input handling and filtering. Second, controls inside the model instructions. Third, controls between the model and its tools, such as argument checks. Fourth, controls around each tool, such as permissions, scope, and sandboxing. Fifth, controls after the model, such as output handling. Sixth, the design as a whole.
3. At each layer, write down the controls present and the real capability that remains. Note gaps where a control exists on paper but the capability is still open.
4. Classify each control. Mark it as capability removal if it takes an action away entirely. Mark it as text inspection if it only reads a prompt, a request, or a reply and decides from the wording.
5. Apply the sorting rule. Treat capability removal as holding under adaptation, because there is nothing left to talk the agent into. Treat text inspection as failing under adaptation, because new wording can bypass it.
6. Replace text inspection controls wherever the work allows it. Drop the tool, narrow its scope, cut its permissions, sandbox it more tightly, or move the action behind an approval.
7. Record each layer in a table with its controls, their class, and either the replacement made or the reason no replacement was possible.
8. Re-check the whole design after replacements. Confirm no layer depends on another weak layer to stay safe.

## Edge cases

If a tool must stay broad for the work to function, keep it but isolate it, limit its data, and require approval for irreversible actions. If a text inspection control must remain, label it as weak in the record and pair it with at least one capability removal control. If you cannot tell what an agent can actually do, test it in a sandbox before finishing the audit.
