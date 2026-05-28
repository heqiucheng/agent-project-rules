# API Contract: [API Name]

## Purpose

What does this API do?

## Endpoint

```text
METHOD /path
```

## Auth

[Auth requirement]

## Request

```json
{}
```

## Response

```json
{
  "data": {},
  "error": null,
  "meta": {
    "request_id": "req_xxx",
    "timestamp": "2026-01-01T00:00:00Z"
  }
}
```

## Errors

| Code | HTTP | Meaning | Client Action |
| --- | --- | --- | --- |
| ERROR_CODE | 400 | [Meaning] | [Action] |

## Local Verification

- [ ] Smoke test created
- [ ] Mock/fake created
- [ ] Sanitized sample response captured
- [ ] Timeout/rate limit/error behavior tested