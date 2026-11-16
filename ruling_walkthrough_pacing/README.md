# Ruling Walkthrough Pacing

## What it is
This skill walks a user through a pre existing list of questions or rulings at the pace and in the format the user sets, so no item, part, or option is stacked, re read, or skipped ahead. It confirms the channel before starting, because voice and text use different formats, states the format it will follow in one short line, and then starts without background or filler. Any pacing rule the user gives during the walkthrough is treated as binding for every later item, not only for the item being discussed. It keeps a running record of each ruling as it is made, and records nothing for an item the user has paused or left unfinished.

In voice, the agent opens each question by stating how many parts it has, and how many sections it has when sections exist. It reads the problem for one part only, then stops and waits. It does not read the next part until the user tells it to move on, and does not move to part two until part one has a solution the user accepts. Within a part it presents one option at a time, then leaves room to think before offering the next. It never re reads a question, a part, or an option unless the user specifically asks. Each spoken turn stays brief and free of filler, and it stays on the current question without folding in parts of earlier or later questions.

In text, the agent presents the whole question at once, including all of its parts, keeping the presentation to the problem and its options without a preamble about the list as a whole. It waits for the ruling before presenting the next question, and applies the same no re reading rule, resending a question only when the user asks for it again.

To close each ruling, the agent restates the ruling the user made in their own terms in one or two short lines, writes it to the record the walkthrough is using before moving on when a record file or log has been named, and names the next question by number only when the user signals they are ready. When the user pauses an item, it is marked paused and unfinished, and no ruling is submitted, filed, or summarised for it.

## Example
A user is working through a numbered list of decision questions on a voice call. For the next question the agent says how many parts it has, reads the problem for part one only, and waits. The user thinks, gives a solution for part one, and only then hears part two, with its options presented one at a time. The agent restates the ruling in the user words, writes it to the walkthrough record, and waits for a signal before naming the next question number.

## How to use it
Place the folder in an agent skills library. The agent loads the skill when a walkthrough over a pre existing list of questions or rulings is requested. A person can also ask directly in plain words, for example by asking to go through a list of questions one by one. The person supplies the list to walk through and, where a ruling is to be written down, the record file or log named for it. The person also sets the channel, voice or text, and any pacing rules they want applied.

## For agents
Agent use is the same as the use already described. Two options the skill notes are to offer to switch formats when the channel changes mid walkthrough, applying the voice format on calls and the whole question format in text, and to offer a written list of the remaining question numbers only, without their content, when the user wants to see progress without breaking the pace.
