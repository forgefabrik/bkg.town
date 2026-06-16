# BKG — Agents Guide

This file contains BKG-specific instructions for polecat agents working in the BKG rig.

## What Is BKG

BKG is a Rust + WebAssembly game development platform. It enables creators to build performant browser-based games by compiling Rust code to WASM modules. The platform provides game engine components, asset pipelines, live event systems, and multiplayer coordination — all served through a Rust web stack.

BKG is not a generic web application framework. It is a domain-specific platform focused on game creation, and every architectural decision reflects that focus.

## Technology Constraints

The BKG rig is Rust-native. The following technologies are **prohibited** and must not be introduced as dependencies, project scaffolding, or build targets:

- **NO Next.js**
- **NO React**
- **NO TypeScript** (except as a build-tool language when unavoidable; prefer Rust tooling)
- **NO Prisma**
- **NO local JSON databases**
- **NO Python**
- **NO Go**

Permitted and expected technologies include:

- **Rust** (edition 2024, workspace resolver 2)
- **WebAssembly (WASM)**
- **Axum** for HTTP services
- **SQLx** for database access
- **Redis** for queues and caching
- **PostgreSQL** for relational storage
- **Tokio** for async runtime
- **Docker / Docker Compose** for environment parity

## Release Process

BKG follows a **sequential, gate-based release process**.

1. **Convoy work**: Features and fixes are grouped into convoys. Convoys represent a complete, coherent set of changes.
2. **Gate-driven**: Each release must pass defined gates (build, format, lint, tests, security scan, documentation) before proceeding. See `docs/RELEASE-EVIDENCE.md` for gate definitions and evidence templates.
3. **Sequential dispatch**: Agent work is dispatched in dependency order. Tasks that depend on infrastructure changes wait until those changes are reviewed and merged.
4. **Refinery review**: Every bead is reviewed by the refinery before the release gate is satisfied.
5. **No cherry-picking**: Do not manually cherry-pick commits across releases. Work from the correct feature branch for the current convoy.

## Key Directories and Their Purpose

| Directory | Purpose |
|-----------|---------|
| `apps/web/` | Axum web application. Serves the WASM client and exposes the API. |
| `apps/jobs/` | Background worker consuming Redis queues for live events and async tasks. |
| `packages/agents/` | Agent runtime and orchestration logic. |
| `packages/ai/` | AI-driven game behavior and NPC logic. |
| `packages/animation-engine/` | Sprite animation and tweening. |
| `packages/audio-engine/` | Spatial audio and sound effect handling. |
| `packages/auth/` | Authentication and authorization primitives. |
| `packages/config/` | Shared configuration and environment handling. |
| `packages/contracts/` | API types and service-to-service contracts. |
| `packages/database/` | SQLx connection pool, queries, and migrations. |
| `packages/game-docs/` | Game document and format parsing. |
| `packages/game-engine/` | Core ECS, game loop, and entity management. |
| `packages/level-engine/` | Tilemap and level serialization. |
| `packages/live-events/` | Real-time event broadcasting. |
| `packages/observability/` | Tracing, metrics, and structured logging. |
| `packages/pixel-engine/` | 2D pixel-perfect renderer. |
| `packages/testing/` | Test harnesses and fixtures. |
| `packages/ui/` | In-game UI components. |
| `packages/validation/` | Input validation and sanitization. |
| `packages/voice/` | Voice integration and audio capture. |
| `docs/` | All project documentation including release evidence. |
| `migrations/` | Versioned SQL migration files. |
| `scripts/` | Build, deploy, and maintenance scripts. |
| `tests/` | Integration and end-to-end test suites. |

## How to Run the Project Locally

### Prerequisites

- Rust toolchain (edition 2024)
- Docker and Docker Compose
- `make`

### Steps

```bash
# 1. Install Rust toolchain (stable)
rustup default stable

# 2. Start infrastructure services
make dev-up

# 3. Install dependencies and build workspace
make setup
make build

# 4. Run the web application with hot reload
make dev

# 5. In another terminal, run the background worker
make jobs

# 6. Run tests
make test

# 7. Run lints
make lint
```

### Makefile Targets

| Target | Description |
|--------|-------------|
| `make setup` | Install Rust dependencies and start Docker services |
| `make build` | Build the full Rust workspace |
| `make test` | Run all tests |
| `make lint` | Format check and Clippy |
| `make db:up` | Start Docker database services |
| `make db:down` | Stop Docker services |
| `make dev-up` | Start full development stack via Docker Compose |
| `make dev-down` | Stop development stack |
| `make dev-reset` | Reset volumes (data loss — use with care) |
| `make dev` | Run web app with watch |
| `make jobs` | Run jobs worker with watch |

### Environment Variables

Copy `dev-vars-example` to `.env` and configure local-safe defaults. Do not commit `.env`. Secrets are injected at runtime from environment variables, never from source code.

### Important Reminders

- Every change must compile and pass `cargo clippy -- -D warnings`.
- Write tests for new packages and critical paths.
- Update documentation (`docs/`, `README.md`) when behavior changes.
- Never introduce prohibited technologies even temporarily.
- Use the `validation` package for input sanitization.
- Use parameterized queries via SQLx; never concatenate strings into SQL.
