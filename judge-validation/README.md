# Judge Validation

## What it is

Judge Validation is the end to end protocol for deciding whether an automated judge can be trusted to grade work. It treats the judge as a measurement instrument that must be calibrated against humans before use, not as a model whose scores are taken on trust.

The protocol has six parts. First, humans label a sample blind, without seeing judge output. When several humans label the same items, their agreement sets the realistic ceiling. No judge can be expected to agree with humans more than humans agree with each other, and admission stops if that ceiling is not on record. Second, the judge grades the same sample blind, with no provenance about which system produced which output. Third, code computes the comparison: Cohen kappa, per class agreement, and recall on the fail class. Fourth, pairwise judges face a swap test. Both orders run, and only verdicts that survive the swap count. The rest are ties. Fifth, every disagreement is reviewed and classified as rubric ambiguity, judge error, or human error. Sixth, the rubric is iterated on a fresh sample, and the judge prompt is never tuned to a single grader.

Revalidation runs monthly and at once on any change to the judge model, the rubric, or the task family. A kappa below 0.6 points first to the spec or the rubric wording, not to judge size.

## Example

A team wants a judge to grade code review comments as pass or fail. Two humans label 200 comments blind and agree at a kappa of 0.78, which becomes the ceiling. The judge grades the same 200 blind and scores a kappa of 0.71 against the human consensus, with fail recall of 0.92. Disagreements cluster on comments that mix praise with one blocking issue. Review classifies most of them as rubric ambiguity. The rubric is clarified to state that a blocking issue means fail regardless of tone, then retested on a fresh 200. Kappa rises and the judge is admitted for that task family only.

## How to use it

Supply a representative sample, a written rubric, and at least two human labellers for the overlap set. Run the steps in order and keep the artefacts: human labels, judge labels, the computed metrics, swap results where relevant, and the disagreement classification. Admission, rejection, or retest follows from those artefacts.

## For agents

An agent must keep labelling and judging blind in both directions and must let code compute agreement, not estimate it. An agent must not tune prompts to please one grader, must record swap failures as ties, and must trigger revalidation on model, rubric, or task change without waiting to be asked.
