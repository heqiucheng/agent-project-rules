# Coding Agent Reliability Hardening Design

## Status

Approved for implementation

## Goal

Upgrade `agent-project-rules` so downstream repositories get stronger default protection against shallow fixes, false completion claims, instruction-chain drift, permission-state confusion, scope drift, and prompt-injection style rule bypass.

## Scope

- add explicit coding-agent reliability rules
- add explicit instruction-chain rules
- add explicit untrusted-input rules
- add work-log and cross-project bootstrap prompt templates
- wire the new rules into `AGENTS.template.md`, `README.md`, playbooks, and execution templates
- add a cross-tool `.agents/rules/` compatibility note

## Non-Goals

- no executable enforcement tooling in this repo yet
- no CI implementation in this repo yet
- no vendor-specific deep integration for any single coding tool

## Design Summary

The repository should stop assuming that rule files enforce themselves. The new default model is:

1. audit instruction sources before non-trivial edits
2. verify runtime capability assumptions when they matter
3. lock scope before editing
4. protect governance/configuration files
5. keep status claims evidence-backed
6. prefer deterministic gates over repeated prompt reminders
7. keep work logs for long-running or resumed tasks
8. treat third-party text as untrusted input unless validated

## Main Artifacts

```text
rules/agent-reliability-rules.md
rules/instruction-chain-rules.md
rules/untrusted-input-rules.md
templates/work-log-template.md
templates/other-project-bootstrap-prompt.md
.agents/rules/README.md
```

## Validation

Validation for this rules-only change is documentation-level:

- new artifacts exist
- root templates reference them
- playbooks include them in bootstrap/adoption guidance
- status and implementation templates expose the new reporting fields
