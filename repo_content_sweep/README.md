# Repo Content Sweep

## What it is
This skill sweeps a shipped repo tree for banned content inside file contents, not only in file names, before the repo is claimed to be clean. It starts by listing the banned content classes for that repo before scanning, drawn from the standing rules for the repo. Examples given in the skill include build process sections, working document material, builder attribution or provenance stamps, and citations to people or sources who did not write the code.

Beside the banned classes, the skill lists the decided exceptions. Examples include benchmark and eval harnesses that ship on purpose, product content that names agents as the system users, third party credits that are ruled to be kept, and any specific comment or file that is ruled to be kept. A hit that matches a decided exception is treated as kept and recorded as an exception, not removed or reported as a violation.

The scan greps the full text of every shipped file for each banned class, including readmes, install docs, license files, source docstrings and comments, and test fixtures. File names and the tree listing are checked as a separate pass, and a clean file list is never treated as proof that contents are clean. Each grep hit is read in context before a decision, because the same words can be product content in one place and banned provenance in another. The search covers concepts as well as exact phrases, including section headings, credit lines, origin stories, and citation formats such as paper titles, author names, and archive identifiers.

Confirmed violations are removed or rewritten in place, keeping the surrounding content accurate as a standalone description of the system. The full content grep is re run after fixes, with counts reported per banned class including zero counts. The repo test suite is run from the cleaned tree and reported beside the sweep counts. The pushed result is verified through the GitHub API, checking the remote head and tree, before the clean version is claimed to have landed. Any ambiguous hit is flagged to the user as a pending ruling and left unchanged.

## Example
A repo has already had its working document files removed, but its README still contains a build process section and citations to people who did not write the code. The sweep lists those as banned classes, greps all files including docstrings and fixtures, reads each hit in context, removes or rewrites the confirmed sections, then re runs the grep and reports the count per class. It runs the test suite from the cleaned tree and verifies the pushed head through the GitHub API before reporting the repo as clean.

## How to use it
Place the folder in an agent skills library. The agent loads the skill when a shipped repo needs a content sweep before a clean claim is made. A person can also ask directly in plain words, for example by asking for a repo to be swept for banned content in its file contents. The person supplies the repo to sweep and, where they exist, the standing rules that define the banned classes and the decided exceptions for that repo.

## For agents
When the skill loads, the agent defines the banned classes and exceptions first, scans contents and file names in separate passes, decides each hit in context, fixes confirmed violations, and reports per class counts, the test result, and the API verified head. For a sweep where the banned classes are new, the skill notes the option of sweeping a small sample repo first and showing the hit list before applying the same sweep across many repos. It also notes keeping the banned class and exception lists in the project design repo so later sweeps reuse the ruled lists.
