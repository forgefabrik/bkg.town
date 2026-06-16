# BKG Technology Stack Matrix

## Purpose

This document records the Release 00 technology stack convention for BKG. It defines the approved technology families and the evidence expected when Release 01 and later implement them.

The binding source of truth is [PLAN.md](../../PLAN.md), especially the Rust + WASM stack, external component boundaries, and release evidence requirements.

## Matrix

| Concern | Release 00 Choice | Rationale | Evidence Required |
|---------|-------------------|-----------|-------------------|
| Product language | Rust 2024 edition | Memory safety, performance, strong typing, and WASM compatibility. | Cargo workspace, crate manifests, rustfmt/clippy evidence. |
| Workspace | Cargo workspace | Shared dependency management and consistent crate boundaries. | Workspace manifest and package inventory. |
| Web backend | Axum or equivalent Rust web framework | Async-first HTTP, WebSocket support, Tower ecosystem, Rust-native routing. | Route inventory, integration tests, security review. |
| Browser UI | Rust + WASM UI framework | Keeps browser surfaces in the Rust production stack. | WASM build evidence, browser tests, accessibility checks. |
| Async runtime | Tokio | Mature Rust async runtime for web, workers, queues, and timers. | Worker tests, timeout tests, cancellation behavior. |
| Serialization | serde | Standard Rust serialization and deserialization. | Contract tests and API fixture tests. |
| Database | PostgreSQL 16+ | Durable relational storage, strong consistency, pgvector support. | Migration checks, query tests, backup/restore evidence. |
| Database access | SQLx or SeaORM | Rust-native database access with prepared statements. | Parameterized query evidence, migration tests. |
| Queue and cache | Redis 7+ | Durable queues, pub/sub, retry state, and worker coordination. | Queue tests, failure recovery tests. |
| Object storage | S3-compatible storage or MinIO in development | Generated assets, builds, exports, launch artifacts, and media. | Upload/download tests, ownership policy tests. |
| Auth | BKG-controlled identity layer | Centralized sessions, roles, tenant boundaries, and audit events. | Auth flow tests, RBAC tests, session rotation tests. |
| Live events | WebSockets with SSE fallback | Real-time production status, agent discussion, and preview updates. | Event ordering tests, reconnect tests. |
| AI provider routing | BKG Model Router over OpenRouter | Provider-neutral model access, cost control, and health monitoring. | Adapter tests, routing policy tests, redacted audit logs. |
| Coding runtime | BKG Coding Runtime | Controlled coding-agent workflow, policy enforcement, and auditability. | Session tests, policy tests, patch validation tests. |
| Browser sandbox | BKG Browser Sandbox | Isolated browser-native experimentation and preview environment. | Isolation tests, path traversal tests, network policy tests. |
| Observability | tracing + OpenTelemetry | Structured logs, traces, metrics, and release evidence. | Trace samples, log redaction tests, metric inventory. |
| CI/CD | GitHub Actions | Repeatable build, test, lint, format, audit, and Docker checks. | Passing workflow runs and release evidence. |
| Local infrastructure | Docker Compose v2 | Reproducible PostgreSQL, Redis, storage, and service setup. | Compose config check and local setup evidence. |
| Documentation | Markdown under `docs/` | Durable architecture, security, contribution, and release records. | Documentation review and release evidence links. |

## Prohibited Product Foundations

The following are not approved as final product foundations for BKG:

- Next.js as a product backend or UI framework.
- React as the required UI implementation basis.
- TypeScript as the main product implementation language.
- Prisma as the required database access layer.
- Python as a product backend.
- Go as a product backend.
- Local JSON files as the production database.
- Markdown files as runtime source of truth.
- Uncontrolled shell execution from user or agent input.
- Multiple competing ORMs or parallel backend codebases.

## Evidence Convention

Every stack choice must produce release evidence before it is considered production-ready:

1. Code path exists under the appropriate `bkg/apps/` or `bkg/packages/` crate.
2. Tests cover the behavior.
3. Formatting, linting, and build checks pass.
4. Security implications are reviewed.
5. Release evidence is recorded under `bkg/docs/release-evidence/<release>/`.

## Related Documents

- [Architecture Overview](overview.md)
- [External Component Conventions](external-components.md)
- [Security Policy](../../SECURITY.md)
- [Contributing Guide](../../CONTRIBUTING.md)
- [Production Master Prompt](../../PLAN.md)
