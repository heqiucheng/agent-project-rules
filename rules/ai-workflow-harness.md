# AI Workflow Harness

## Purpose

Make AI-assisted development constrained, repeatable, and reviewable.

## Workflow

```text
1. Read AGENTS.md and relevant rule/persona docs.
2. Understand the request and current project state.
3. Identify required roles.
4. Design before implementation when behavior or UI changes.
5. Verify external contracts before integration implementation.
6. Implement in small, bounded changes.
7. Run quality gates.
8. Review against rules.
9. Explain what changed, what was tested, and what remains risky.
10. Update rules when repeated issues appear.
```

## Hard Rules

- Do not blindly code against unknown APIs.
- Do not ignore project style or architecture rules.
- Do not claim success without verification.
- Do not hide test failures or skipped tests.
- Do not leave long-running needed processes unmanaged.
- Do not revert unrelated user work.

## Step Explanation Requirement

For major technical stages, report:

```text
What was done
Technologies used
Why this approach
Hard parts
Risks
Validation method
Next step
```