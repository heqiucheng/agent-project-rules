# [Project Name]

[Short description]

## Development Rules

This project uses AI-assisted development rules based on `agent-project-rules`.

Key local files:

```text
AGENTS.md
docs/agents/
docs/rules/
docs/specs/
docs/design/
.agents/rules/
```

## Quality Gates

```bash
# format
# lint
# typecheck
# test
# build
```

## Important Principles

- Rules first.
- Design before implementation.
- Audit the instruction chain before non-trivial edits.
- Verify integrations before feature coding.
- Verify runtime capability assumptions when permissions or sandboxing matter.
- Test before claiming completion.
- Review before merge.
