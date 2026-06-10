# Chief Orchestrator Status Update Template

Use this template for short phase updates during execution.

## Format

```text
Status:
- Modified | Verified | Deliverable

Scope lock:
- intended files/modules
- whether scope expanded

Runtime state:
- permission/sandbox/network state if relevant

Completed:
- what was done
- which files/modules moved

Roles activated:
- which personas were actually used this phase

Decision:
- what path was chosen
- why this path was chosen

Validation:
- what checks ran
- what passed

Evidence:
- command, screenshot, artifact, log, or sample result that supports the status

Risk:
- remaining limitation or gap

Next:
- the action already started or about to start
```

## Rules

- Keep it short.
- Do not ask the user to approve low-risk obvious next steps.
- Do not hide failed validation.
- If a gate could not run, say so directly.
- If validation is missing, keep the status at `Modified`.
- Do not use `Deliverable` when required validation is missing.
- If scope expanded, say so directly.
- If runtime capability mattered, report what was actually confirmed.
- "Next" should be an action, not a vague suggestion.
