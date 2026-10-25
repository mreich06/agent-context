# agent-context

Shared agent rules and skills, consumed by other repos as a git submodule.

- `AGENTS.md`: general rules for any project
- `skills/write-spec/`: write a spec before any code
- `skills/review/`: review finished work against its spec and the rules

Project-specific rules (stack, commands, domain rules) stay in each project's own `AGENTS.md`.

## Use it in a repo (for example a frontend)

```
git submodule add https://github.com/mreich06/agent-context.git .agent-context
mkdir -p .claude && ln -s ../.agent-context/skills .claude/skills
```

Then add a `CLAUDE.md` with two lines, so the agent loads the shared rules and the project's own:

```
@.agent-context/AGENTS.md
@AGENTS.md
```

## Clone a repo that uses it

```
git clone --recurse-submodules <repo-url>
```

If you already cloned without the flag: `git submodule update --init`.

## Change the shared context

1. Edit and commit in `agent-context`, then push it.
2. In each consuming repo: `git submodule update --remote`, then commit the new pointer.
