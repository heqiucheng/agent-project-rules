# Security Rules

## Hard Rules

- Enforce authentication, authorization, tenant isolation, and least privilege.
- Never log secrets, tokens, credentials, or raw sensitive user data.
- Encrypt sensitive integration credentials.
- Validate input and upload files strictly.
- Record audit logs for critical write actions and high-risk AI/external actions.
- High-risk AI output must require human confirmation.

## Review Focus

```text
Auth bypass
Permission escalation
Tenant data leakage
Sensitive logs
Unsafe file parsing
Prompt/data leakage
Unbounded external actions
```