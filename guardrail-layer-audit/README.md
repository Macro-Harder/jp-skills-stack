# Guardrail Layer Audit

## What it is

This is a structured audit for the safety controls around an agent. It works through the stack in the order a request travels: before the model, inside the model instructions, between the model and its tools, around each tool, and after the model, then it looks at the whole design together.

The central distinction is simple. Some controls remove a capability. If an agent has no tool for sending mail, no wording can make it send mail. Other controls only inspect text. They read a prompt or a reply and try to judge intent from wording. Those controls are brittle, because an attacker who learns how they judge can rephrase until the same action passes.

The audit forces that distinction at every layer. For each control you record what it is, which class it falls into, and what you did about it. Weak controls are replaced where possible by dropping a tool, narrowing scope, cutting permissions, tightening a sandbox, or adding a human approval step. Where replacement is not possible, the record says why, so the remaining risk is visible rather than hidden behind reassuring instruction text.

## Example

An agent can read files and call a shell tool. Its instructions say it must never delete files, and an output filter blocks replies that mention deletion. The audit classifies both as text inspection. The shell still has delete capability, so adapted wording can reach it. The fix removes delete rights from the sandbox, limits the shell to a single working folder, and routes any removal request to an approval. The instruction and the filter can stay as backup, but safety no longer depends on them.

## How to use it

Supply the agent configuration, its instruction text, its tool list with permissions, and any sandbox or approval settings. Run the procedure in SKILL.md and produce the layer table. A person reviewing the result should be able to see, layer by layer, which controls hold and which were only wording.

## For agents

An agent running this audit must test real capability, not quote policy back. Try the action in a safe environment when unsure. Do not mark a control as strong because it is written firmly. Strength comes from removal, not tone.
