# Verification And Truthfulness Rules

## Purpose

Prevent false completion claims, shallow "surface-only" fixes, and confidence that is not backed by verification.

This rule is about engineering truthfulness:

- changing files is not the same as fixing behavior
- reading code is not the same as runtime verification
- intended behavior is not the same as observed behavior

## Status Model

Every meaningful task should use one of these statuses:

```text
Modified
Verified
Deliverable
```

Definitions:

- `Modified`: files, prompts, or configuration changed, but the claimed result is not yet verified.
- `Verified`: the claimed scope was checked with relevant validation, and the evidence is available.
- `Deliverable`: the work is verified, required gaps are disclosed, and the result is suitable to hand back as the current best completed unit.

Do not merge these states in language. If validation is missing, the work is not `Verified`. If required validation is missing or failed, the work is not `Deliverable`.

## Hard Rules

- Do not say `fixed`, `completed`, `successful`, `working`, `ready`, or equivalent unless the status and evidence support that wording.
- Do not treat static inspection alone as proof of runtime behavior when runnable validation is possible.
- Do not report manual testing, smoke checks, screenshots, logs, or builds unless they were actually performed.
- Do not hide failed checks behind a positive summary.
- Do not silently downgrade a problem from behavior risk to "probably okay".
- If only a partial layer changed, say which layer changed. UI text or layout changes are not proof that underlying workflow logic works.

## Evidence Requirements

Any `Verified` or `Deliverable` claim should include evidence appropriate to the task, such as:

- commands run
- tests run
- build, lint, or typecheck results
- browser/manual smoke checks
- screenshots or artifact paths
- logs or API responses
- sample inputs and observed outputs

Summarize the evidence in the response. If the raw output is large, point to the file or artifact path.

## Task-Specific Guidance

Frontend work:

- If the app can run locally, prefer a real browser smoke check for user-facing changes.
- Visual edits should be checked on the affected state, not only by reading the code.

Backend or API work:

- Prefer runnable tests or local requests over static reasoning alone.
- Integration behavior should be verified with mocks, fakes, or local smoke checks where practical.

Prompt or AI behavior work:

- Verify against at least one representative input when practical.
- Distinguish between prompt text being updated and prompt behavior being validated.

Bug fixes:

- When practical, add or run a regression check that would have caught the original issue.

## Failure Handling

If validation could not run:

- keep the status at `Modified`, or explicitly describe the narrow part that is `Verified`
- explain why validation could not run
- state what remains risky
- state the next concrete check needed

If validation failed:

- report the failure directly
- do not summarize the task as successful
- either continue fixing it or hand back the blocker clearly

## Reporting Contract

Preferred reporting shape:

```text
Status:
Completed:
Validation:
Evidence:
Risk:
Next:
```

The status should match the strongest claim supported by the evidence, not the desired outcome.
