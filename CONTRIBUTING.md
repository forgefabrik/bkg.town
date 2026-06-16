# Contributing to BKG

## Purpose

This guide defines the contribution conventions for BKG. It keeps the repository readable, secure, and aligned with the Rust + WASM platform contract.

## Development Setup

### Prerequisites

- Rust 1.85+ through rustup
- Docker and Docker Compose v2+
- PostgreSQL 16+ or the local Compose stack
- Redis 7+ or the local Compose stack

### Standard Commands

```bash
make setup
make build
make test
make lint
make fmt
make fmt-check
make check
make clean
```

Use Docker Compose v2 only:

```bash
docker compose -f bkg/docker-compose.yml config
docker compose -f bkg/docker-compose.yml up -d
docker compose -f bkg/docker-compose.yml down
```

## Branching Model

- Create feature branches from the active base branch.
- Keep branches focused on one concern.
- Use descriptive branch names.
- Do not commit secrets or generated local state.
- Do not merge directly to the protected branch.

## Commit Conventions

Use conventional commits:

```text
<type>(<scope>): <subject>
```

### Types

| Type | Use |
|------|-----|
| `feat` | New user-visible or platform capability. |
| `fix` | Bug fix. |
| `docs` | Documentation change. |
| `refactor` | Internal restructuring without behavior change. |
| `test` | Test-only change. |
| `security` | Security hardening or vulnerability response. |
| `chore` | Build, tooling, or repository maintenance. |

### Subject Rules

- Use imperative mood: `add`, `fix`, `document`, `refactor`.
- Keep the subject concise.
- Do not include secrets.
- Reference bead or issue IDs when available.

Example:

```text
docs(architecture): add stack matrix
```

## Pull Request Requirements

Every pull request must satisfy the following before review:

1. The branch builds.
2. Formatting passes.
3. Linting passes.
4. Tests pass.
5. Documentation is updated when behavior or conventions change.
6. Security-sensitive changes include review notes.
7. No secrets, tokens, private keys, or local `.env` content are present.
8. No unrelated changes are included.

## Code Standards

- Follow Rust 2024 edition conventions.
- Prefer clear domain boundaries over clever code.
- Keep adapters between business logic and external systems.
- Validate all external input.
- Use parameterized database access.
- Keep secrets out of source, logs, and tests.
- Add tests for behavior, failure modes, and security boundaries.
- Avoid implementation details in Release 00 documentation.

## Documentation Standards

Documentation must be English-only and use proper Markdown.

Acceptable Release 00 documentation:

- architecture conventions;
- stack matrices;
- security policies;
- contribution rules;
- release evidence structure;
- placeholder sections that define required future evidence.

Unacceptable documentation:

- unresolved placeholder notes in legitimate sections;
- fake implementation claims;
- real secrets;
- outdated stack references;
- implementation detail that belongs in Release 01+ code comments or technical design docs.

## Security Requirements

- Do not commit secrets.
- Do not add browser-side provider keys.
- Do not bypass validation.
- Do not concatenate SQL or shell commands from untrusted input.
- Do not expose tenant or project data across ownership boundaries.
- Do not disable linting, tests, or security checks to make a PR pass.

## Release Evidence

Changes that affect production behavior must include release evidence:

- build result;
- format result;
- lint result;
- test result;
- security scan result;
- migration check when database changes exist;
- known issues and remediation notes.

Store evidence under `bkg/docs/release-evidence/<release>/`.

## Related Documents

- [README](README.md)
- [Architecture Overview](docs/architecture/overview.md)
- [Technology Stack Matrix](docs/architecture/stack.md)
- [External Component Conventions](docs/architecture/external-components.md)
- [Security Policy](SECURITY.md)
- [Production Master Prompt](PLAN.md)
