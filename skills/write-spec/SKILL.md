---
name: write-spec
description: Write a spec in specs/ for a user story before any code is written. Use when asked to spec, plan or start a feature.
---

# Write spec

## When to use

- Before implementing any story.
- To update an existing spec in `specs/` that is missing acceptance criteria, error cases, assumptions or open questions.

## Inputs

- The story ID, for example `PB-03`. Read that story in `BRIEF.md`, plus its "Context" section.
- Any existing file for that story in `specs/`.
- The user's answers to earlier open questions, if there are any.

## Output

- One file: `specs/<story-id>-<short-name>.md`, for example `specs/PB-03-check-in.md`, following `template.md`.
- No code and no changes outside `specs/`.

## Steps

1. Read the user story and any earlier specs.
2. Draft the spec following `template.md`. Put every choice you made under Assumptions and every unclear point under Open questions.
3. Ask me for my notes, then compare them with your draft and list the differences.
4. Stop. I will edit the spec.

## Checks

- Every requirement is testable
- Every error status is listed with its trigger, including 4xx and 5xx
- Terms the requirements depend on (for example "active session") are defined
- Acceptance criteria are numbered and written as "Given", "When", "Then"
- Every requirement is covered by at least one acceptance criterion
- Each assumption has a reason

## Rules

- Don't fill a gap. Put it in Assumptions and Open questions
- Keep specs concise: only what is core to the feature, so I can verify the spec quickly
- Cover only core behavior and error cases. No implementation details (tables, indexes, locks, libraries)
- Keep the spec as short as possible: core behavior and error cases only. Anything else goes under Open questions
- One acceptance criterion per behavior or error status. Merge near-duplicates
- Every error status gets one row in the contract and is covered by a criterion, with no extra cases beyond those
- Each assumption and open question is one line, with a reason or a default. Drop any that restate a requirement
- No requirement may repeat another requirement, assumption or the contract
