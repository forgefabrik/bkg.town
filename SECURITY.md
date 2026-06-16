# BKG Security Policy

## Scope

This policy applies to all BKG code, infrastructure, documentation, automation, and release evidence.

## Core Principles

1. No secrets in source control.
2. No secrets in browser bundles.
3. No secrets in logs, tickets, screenshots, generated artifacts, or release evidence.
4. All external input is untrusted until validated.
5. All database access uses parameterized queries.
6. All external integrations use adapter boundaries.
7. All services run with least privilege.
8. All security-sensitive changes require review and evidence.

## Secret Handling Rules

### Allowed

- Local development placeholders in `.env` or `dev-vars-example`.
- CI/CD secrets stored only in the repository secret store.
- Production credentials stored only in a dedicated secret manager.
- Redacted logs and audit records.

### Forbidden

- API keys in source code.
- Private keys in source code.
- Database passwords in commits.
- Provider tokens in browser bundles.
- Secrets in documentation.
- Secrets in test fixtures.
- Secrets in screenshots or generated release evidence.
- Secrets in shell history or command output.

### Rotation

Rotate any secret that has been committed, logged, exposed in a browser bundle, shared in a ticket, or sent to an unauthorized recipient. Rotation must be recorded as a security incident and included in release evidence.

## Vulnerability Disclosure

Report suspected vulnerabilities to:

```text
security@forgefabrik.com
```

A responsible disclosure report should include:

- affected component or document path;
- steps to reproduce;
- impact;
- suggested severity;
- whether secrets or customer data are involved;
- safe contact details.

Do not include live secrets in the report. Redact tokens, passwords, session IDs, and private keys.

## Access Control

- Use role-based access control for user and admin routes.
- Enforce tenant and project ownership checks at the database layer.
- Admin routes require explicit authorization middleware.
- Service accounts receive only the permissions required for their job.
- Cross-tenant access is denied by default.

## Input Validation

All external inputs must be validated before use:

- HTTP request bodies;
- query parameters;
- path segments;
- file names;
- uploaded assets;
- agent outputs;
- provider responses;
- database values crossing trust boundaries.

Validation must enforce size limits, schema rules, allowed character sets, and path normalization.

## Injection Prevention

- Use prepared statements for all SQL.
- Do not concatenate user input into queries.
- Do not construct shell commands from user or agent input.
- Do not pass unvalidated paths to file operations.
- Validate all migration content before applying migrations.

## Dependency and Supply Chain Security

- Run dependency audits in CI.
- Review licenses for external components.
- Pin external component versions or commit SHAs.
- Record checksums when available.
- Block known vulnerable dependencies.
- Review third-party crates before production use.

## External Component Security

External components must be isolated behind BKG adapters. Adapters must provide:

- secret redaction;
- timeout limits;
- retry limits;
- health checks;
- audit logs;
- capability discovery;
- failure classification;
- provider-neutral error handling.

Business logic must not call external component internals directly.

## Incident Response

When a security incident is detected:

1. Contain exposure.
2. Rotate affected secrets.
3. Preserve relevant logs and evidence.
4. Notify the security contact.
5. Patch the root cause.
6. Add regression tests.
7. Record the incident and remediation in release evidence.

## Related Documents

- [Architecture Overview](docs/architecture/overview.md)
- [Technology Stack Matrix](docs/architecture/stack.md)
- [External Component Conventions](docs/architecture/external-components.md)
- [Contributing Guide](CONTRIBUTING.md)
- [Production Master Prompt](PLAN.md)
