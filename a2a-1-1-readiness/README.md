# A2A 1.1 Readiness

## What it is
This skill is a watching brief on A2A version 1.1. It records the standing position for planning and design work and explains what version 1.1 would add when it lands.

The standing position is that production stays on A2A 1.0 or 1.0.1 with current SDKs. Version 1.1 exists only as a release candidate, with no final release date and no official SDK support, so nothing ships on 1.1 by default.

The skill lists what 1.1 adds: SendLiveMessage for two way streaming on a single task, a task timeline with generation counters for optimistic concurrency and resumable subscriptions, client written artifacts gated by a user_artifacts capability, a new agent card media type, and discovery guidance that prefers an AI Catalog. It also lists known churn and gaps, including an open revision of live and artifact semantics, no dedicated security section for streaming or client artifacts, and a media model that was not standardised.

It gives a prototype recipe for cases where there is a reason to build against the release candidate, and a watch list of items to recheck before repeating any claim about 1.1 status.

## Example
A team is planning a new A2A surface and asks whether to build it on version 1.1. The skill applies, and the answer follows the standing position: build on 1.0 or 1.0.1 for production, and treat 1.1 features such as SendLiveMessage as future work unless both ends are controlled and the work is isolated from production.

## How to use it
The folder sits in an agent skills library, and the agent loads the skill when a request matches its description, for example when 1.1 comes up in design or planning. A person can also ask for the work directly in plain words, such as asking whether a design should use A2A 1.1 or what 1.1 changes.

The skill does not require a specific input from the person. For a prototype decision, the relevant facts are whether both ends are controlled and whether the work can be isolated from anything production depends on.

## For agents
Agent use is the same as the use described above. When the skill loads, the agent applies the standing position, checks the watch list before making claims about 1.1 status, and follows the prototype recipe only where the conditions in the skill are met.
