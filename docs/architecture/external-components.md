# BKG External Component Conventions

## Purpose

This document defines the Release 00 convention for external components referenced in [PLAN.md](../../PLAN.md) Section 3A. It establishes how external systems are represented inside BKG without turning them into direct production dependencies.

Every external component must be adapter-gated, auditable, configurable, testable, versioned, and replaceable.

## Section 3A Components

| External Component | BKG Target Name | Release 00 Role | Required Evidence |
|--------------------|-----------------|-----------------|-------------------|
| AlmostNode | BKG Browser Sandbox | Browser-native sandbox for isolated experiments, preview sessions, snapshots, diffs, and import plans. | Repository reference, version or commit, license, security notes, adapter contract, isolation tests. |
| OpenRouter | BKG Model Router | Provider-neutral model routing fabric for free and paid model access, capability discovery, routing policy, and audit logs. | Provider adapter contract, routing policy, health check, redacted usage logs, cost controls. |
| Kilo Code | BKG Coding Runtime | Controlled coding-agent runtime for sessions, modes, skills, MCP workflows, patch handling, context, policy, and audit. | Runtime contract, policy boundaries, audit schema, validation tests, redaction tests. |

## Integration Boundaries

### No Direct Calls from Business Logic

BKG domain logic must call BKG adapters, not external component internals.

```text
BKG domain crate
  -> BKG adapter crate
    -> external component client
      -> external service
```

### Required Adapter Capabilities

Each adapter must define:

- normalized inputs;
- normalized outputs;
- normalized errors;
- timeouts;
- retry rules;
- health checks;
- capability discovery;
- audit logging;
- secret redaction;
- cost or usage tracking when relevant;
- replacement strategy.

### Security Boundaries

External components must not receive secrets they do not require. Secrets must be injected server-side, redacted from logs, and excluded from browser bundles.

For browser-facing sandbox work, the sandbox must enforce tenant isolation, workspace root limits, path normalization, command restrictions, network restrictions, and resource limits.

## Release Mapping

| Release Block | Component Area | Expected Outcome |
|---------------|----------------|------------------|
| Release 00C | Upstream audit and recode mapping | Audit inventory, license review, feature mapping, and BKG target mapping. |
| Release 01+ | Adapter contracts | Rust interfaces, normalized errors, health checks, and redaction. |
| Release 02+ | Production integration | Auth, permissions, audit, tests, and release evidence for each integrated component. |

## Documentation Requirements

For each external component, future implementation must record:

- original repository;
- selected version or commit;
- installation method;
- license;
- checksum when available;
- audit date;
- security notes;
- known limitations;
- upgrade strategy;
- rollback strategy;
- BKG adapter location;
- test evidence;
- release evidence link.

## Related Documents

- [Architecture Overview](overview.md)
- [Technology Stack Matrix](stack.md)
- [Security Policy](../../SECURITY.md)
- [Contributing Guide](../../CONTRIBUTING.md)
- [Production Master Prompt](../../PLAN.md)
