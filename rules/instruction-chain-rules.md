# Instruction Chain Rules

## Purpose

Make rule application explicit, auditable, and portable across coding-agent toolchains.

## Authority Model

Use this precedence by default:

1. direct user instruction
2. most-local path-scoped project rule for the files being touched
3. repository root `AGENTS.md`
4. referenced project rules, personas, and templates
5. tool defaults and personal preferences

If two local rule files conflict, prefer the more specific file that governs the touched path. If the conflict is still ambiguous, ask the user or mark the ambiguity before proceeding.

## Startup Audit Contract

Before non-trivial work, identify and report:

- root rule entry file
- path-scoped rule files that apply to the touched area
- tool-specific mirrors
- any conflict or duplication risk

Preferred reporting shape:

```text
Instruction chain:
- root: AGENTS.md
- path-scoped: .agents/rules/...
- tool mirrors: ...
- conflict check: clear | needs attention
```

## Cross-Tool Compatibility

Use `AGENTS.md` as the primary repository entry point.

When cross-tool portability matters, mirror path-specific constraints inside `.agents/rules/`.

Common mirror surfaces that may coexist in real repositories:

```text
AGENTS.md
CLAUDE.md
GEMINI.md
.agents/rules/**
.cursor/**
.clinerules
.github/copilot-instructions.md
```

Do not let these drift silently. Decide which file is authoritative and note which files are mirrors.

## Path-Scoped Rule Rule

If a subdirectory has a more specific rule file than the repo root, use it for work in that path unless it conflicts with direct user instruction.

Do not assume the root rule is sufficient when the repository has local overrides.

## Governance Drift Rule

If the same rule exists in more than one place:

- compare them before relying on either
- do not assume they mean the same thing
- prefer updating the canonical source, then update mirrors intentionally

## Reporting Rule

If the instruction chain affects the work, include the chain in status updates and handoffs.

Silence about the rule chain is acceptable only for trivial read-only work.
