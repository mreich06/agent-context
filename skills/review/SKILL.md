---
name: review
description: Review finished feature work against its spec and the AGENTS.md rules. Use after a feature is implemented and before it is considered done
---

# review

## When to use

- When a feature is implemented and its tests are written, before it is called done

## Inputs

- The spec in `specs/<story-id>-<short-name>.md`
- The rules: the project `AGENTS.md` and `.agent-context/AGENTS.md`
- The changes for the feature (working tree)

## Steps

1. Read the spec and both `AGENTS.md` files. If there is no spec for the feature, stop and say so.
2. Map every acceptance criterion (AC) in the spec to the test that covers it. Flag each AC with no test.
3. Check the changes against each rule in the `AGENTS.md` files.
4. Look for risks the spec missed: concurrency, error paths, edge cases, anything in the code that has no requirement behind it.

## Output

- Start with the AC-to-test table, marking uncovered ACs.
- Then a list of findings, most serious first. Each has the file and line, what is wrong, and the spec item or rule it breaks (or "not in spec").
- If nothing is wrong, say so. Do not invent findings.

## Rules

- Never change code or any other file
- Never run git commands
