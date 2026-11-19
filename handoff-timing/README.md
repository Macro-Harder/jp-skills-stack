# Handoff Timing

## What it is
This skill produces the timing line that rides with a counting report in chat. When a counting exchange runs over the handoff hub, each report carries one timing line that shows how long each part of the receive and reply cycle took, and whether each figure was measured or derived.

## Example
Given measured durations of poll 7461, read 7588, ack 11297, and send 1905, with a derived detection time of 76.1s and a derived total of 195s, the skill produces this line:

timing: detection 76.1s (derived), poll 7461ms (7.5s), read 7588ms (7.6s), ack 11297ms (11.3s), send 1905ms (1.9s), total 195s (derived)

## How to use it
Place the folder in an agent skills library. The skill loads when a counting report is being written. The inputs are the measured durations in milliseconds for poll, read, ack, and send, plus a derived detection time and a derived total. The output is one line only, in the form the skill states.

## For agents
Detection and total are shown in seconds and labelled derived. Poll, read, ack, and send are shown in milliseconds, and a value at or over 1000 ms is also shown in seconds with one decimal place, in parentheses after the millisecond value. Produce the one line and nothing else in its place.
