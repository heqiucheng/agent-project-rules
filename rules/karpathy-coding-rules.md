# Karpathy Coding Rules

## Purpose

Reduce common LLM coding failures during implementation, review, and refactoring:

- silent wrong assumptions
- hidden confusion
- over-engineered abstractions
- unrelated edits
- shallow "done" claims without a verifiable result

These rules are inspired by Andrej Karpathy's observations about LLM coding behavior and are adapted here as a reusable project rule layer.

## Activation

Apply these rules whenever an agent writes, edits, reviews, refactors, debugs, or explains code.

For trivial tasks, use judgment. A typo fix does not need a full plan. A non-trivial code change does.

## 1. Think Before Coding

Do not assume. Do not hide confusion. Surface trade-offs.

Before implementation:

- state important assumptions explicitly
- ask when ambiguity materially changes the result
- present multiple valid interpretations when the request is unclear
- push back when a simpler or safer path exists
- stop and name the confusion when the task cannot be executed responsibly

The agent should not silently choose one interpretation when the choice affects behavior, data, security, cost, public output, or long-term architecture.

## 2. Simplicity First

Use the minimum code that solves the stated problem.

Do not add:

- features beyond the request
- abstractions for one-off code
- configuration that was not requested
- speculative extension points
- defensive branches for impossible scenarios

If a solution becomes much larger than the problem warrants, simplify before presenting it.

Self-check:

```text
Would a senior engineer call this overcomplicated?
If yes, reduce it.
```

## 3. Surgical Changes

Touch only what the request requires.

When editing existing code:

- do not improve adjacent code, comments, names, or formatting unless required
- do not refactor unrelated areas
- match the existing style even if another style is preferred
- mention unrelated dead code or issues instead of deleting them
- remove only imports, variables, functions, or files made obsolete by this change

Every changed line should trace back to the user's request, the agreed scope, or a validation requirement.

## 4. Goal-Driven Execution

Convert vague implementation requests into verifiable success criteria.

Examples:

```text
"Add validation"
-> "Add tests for invalid inputs, then make them pass."

"Fix the bug"
-> "Reproduce the bug with a failing test or minimal check, then make it pass."

"Refactor this"
-> "Preserve behavior and show tests or checks passing before claiming success."
```

For multi-step work, state a compact execution loop:

```text
1. Step: [action]
   Verify: [check]
2. Step: [action]
   Verify: [check]
3. Step: [action]
   Verify: [check]
```

The agent should loop until the success criteria are met, blocked, or explicitly downgraded with the reason.

## Required Agent Checklist

Before non-trivial edits:

```text
Assumptions stated
Ambiguities resolved or surfaced
Scope locked
Simplest viable path selected
Validation path identified
```

Before final response:

```text
Only required files changed
No speculative abstraction added
Validation evidence reported
Unrun checks disclosed
Completion label matches evidence
```

## Working Signals

These rules are working when:

- diffs become smaller and more directly related to the request
- unnecessary rewrites decrease
- clarification happens before implementation mistakes
- reviews focus on behavior, validation, and scope rather than cleanup churn
- "done" claims include evidence or clearly state remaining gaps

