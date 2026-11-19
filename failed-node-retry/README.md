# Failed Node Retry

## What it is

This is a way to structure and recover multi agent work. Instead of running a job as one long batch that either succeeds or fails as a whole, you draw it as a graph of nodes. Each node is one unit of work with a named owner, defined inputs, its own tooling, and a check that decides whether its output is good.

When something breaks, the graph shows exactly which node failed. Only that node runs again, with a small context built for that node alone. Everything else keeps its completed work. This saves cost and time, and it also produces better information, because the record shows where failure concentrated, how many retries a node needed, and what had to change for it to pass.

The method also sets a limit. A node that fails again and again is not bad luck to be retried forever. It is evidence that the node spec is wrong, the inputs are wrong, or the owner is mismatched to the task. The graph names a retry cap in advance, and reaching it triggers escalation with that reading attached, rather than another silent attempt or a full job rerun.

## Example

A research job has five nodes: gather sources, extract claims, check claims, draft, and format. The claim checking node fails its check because half the claims lack locations. Instead of rerunning all five nodes, only claim checking runs again, given the extracted claims and the failure list. It passes on the second try, verified against the source files. The graph record shows one failure, one retry, and the fix, while the other nodes ran once each.

## How to use it

Supply the job broken into nodes, with an owner, inputs, and a pass check for each, plus a retry cap. Run the graph, keep the per node record as you go, and use that record for the final report instead of a single success or failure line.

## For agents

An agent coordinating a graph must resist rerunning the whole job for convenience. Retry narrowly, keep the failure visible in the structure, and escalate a repeatedly failing node as a finding rather than hiding it inside a general failure message.
