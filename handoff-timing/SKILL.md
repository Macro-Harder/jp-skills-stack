---
name: handoff-timing
description: Produce the timing line that rides with a counting report in chat.
---

# handoff-timing

## Purpose

Produce the timing line that rides with a counting report in chat.

## Input

Measured durations in milliseconds for poll, read, ack, and send, plus a derived detection time and a derived total, each labelled measured or derived.

## Output form

One line only:

timing: detection Xs (derived), poll Xms, read Xms, ack Xms, send Xms, total Xs (derived)

Detection and total are shown in seconds. Poll, read, ack, and send are shown in milliseconds; a value at or over 1000 ms is also shown in seconds with one decimal place, in parentheses after the millisecond value.

## Worked example

Input: poll 7461, read 7588, ack 11297, send 1905, detection 76.1s derived, total 195s derived.

Output: timing: detection 76.1s (derived), poll 7461ms (7.5s), read 7588ms (7.6s), ack 11297ms (11.3s), send 1905ms (1.9s), total 195s (derived)
