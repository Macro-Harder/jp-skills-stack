# Repo Content Sweep

## Define the banned content first

- List the banned content classes before scanning, drawn from the user standing rules for that repo, such as build process sections, working document material, builder attribution or provenance stamps, and citations to people or sources who did not write the code.

- List the decided exceptions beside the banned classes, such as benchmark and eval harnesses that ship on purpose, product content that names agents as the system users, third party credits the user ruled to keep, and any specific comment or file the user ruled to keep.

- Treat a hit that matches a decided exception as kept, and record it as an exception rather than removing it or reporting it as a violation.

## Scan contents, not only file lists

- Grep the full text of every shipped file for each banned class, including readmes, install docs, license files, source docstrings and comments, and test fixtures.

- Check file names and the tree listing as a separate pass, and never treat a clean file list as proof the contents are clean.

- Read each grep hit in context before deciding, because the same words can be product content in one place and banned provenance in another.

- Search for the concepts as well as the exact phrases, covering section headings, credit lines, origin stories and citation formats such as paper titles, author names and archive identifiers.

## Fix and verify the shipped tree

- Remove or rewrite each confirmed violation in place, keeping the surrounding content accurate as a standalone description of the system.

- Re-run the full content grep after fixes and report counts per banned class, including zero counts, rather than saying the repo is clean without numbers.

- Run the repo test suite from the cleaned tree and report the result beside the sweep counts.

- Verify the pushed result through the GitHub API, checking the remote head and tree, before claiming the clean version landed.

- Flag any ambiguous hit to the user as a pending ruling and leave it unchanged, instead of guessing whether it is a violation or an exception.

## Available connectors

- [GitHub](~/workspace/custom-connectors/custom.github/CONNECTOR.md) for pushing the cleaned tree and verifying the remote head and contents through the API.

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Sweep a small sample repo first when the banned classes are new, and show the user the hit list before applying the same sweep across many repos.

- Keep the banned class and exception lists in the project design repo, so later sweeps reuse the ruled lists instead of re-deriving them.
