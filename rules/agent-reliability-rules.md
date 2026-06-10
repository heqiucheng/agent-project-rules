# Coding Agent Reliability Rules

## Purpose

Reduce the gap between "the agent changed files" and "the agent moved the project forward safely".

This rule exists because modern coding agents fail in repeatable ways:

- they over-edit to make errors disappear
- they assume rules were applied because a file existed
- they assume permission state from stale context
- they say "done" when only a surface layer changed
- they lose context across long tasks and resumes

## Startup Audit

Before non-trivial work, audit:

```text
applicable instruction sources
path-scoped rules
runtime capability state
governance files in or near scope
validation path
```

Do not start editing until this audit is complete.

## Runtime Capability Rule

When the task depends on permissions, sandboxing, network access, or filesystem reachability:

- confirm the current runtime state
- do not rely on prior chat statements alone
- if the capability is uncertain, downgrade claims and say what could not be proven

Claims like "I already have full access" or "the mode changed" are not valid unless the current session state supports them.

## Scope Lock

Before editing, define:

- intended files or modules
- intended behavior change
- what is explicitly out of scope
- an initial diff budget

Default diff-budget guidance:

- small task: 1 to 3 files
- medium task: 3 to 8 files
- large task: state the affected subsystems explicitly

If the touched area expands, report the expansion and reason.

## Governance File Protection

Treat these as protected surfaces:

```text
AGENTS.md
.agents/**
.codex/**
.cursor/**
.github/copilot-instructions.md
CI files
deployment configuration
security policy files
approval / sandbox configuration
```

Do not edit them casually. State why they are in scope and what risk the change carries.

## Deterministic Gates First

If the same failure repeats, do not rely on a better prompt alone.

Prefer:

- scripts
- test helpers
- linters
- CI checks
- hooks
- generated reports
- state templates

Prompt discipline matters, but repeated failures should become machine-checkable when practical.

## Work Log Rule

Use a work log for:

- multi-step tasks
- long-running tasks
- resumed tasks
- tasks with branching decisions
- rule or prompt experiments
- anything likely to exceed one working session

The log should capture goal, scope, assumptions, validation, blockers, and next step.

## Delivery Rule

`Modified` is the default after editing.

Do not upgrade to `Verified` or `Deliverable` unless:

- the validation path was actually run for the claimed scope
- evidence is available
- skipped gates are disclosed
- residual risk is stated

## Anti-Patterns

- "The rules are loaded, so we're fine."
- "The UI changed, so the feature works."
- "The command should have succeeded."
- "I probably have the right permissions now."
- "This touched more files than expected, but it's cleaner this way."
- "We can fix verification later."
