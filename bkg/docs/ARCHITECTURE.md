# BKG Platform Architecture

## 1. System Overview

BKG is a Rust-first game development platform that enables creators to build, deploy, and scale browser-based games using WebAssembly (WASM). The platform provides a complete toolchain for game authoring, asset management, live events, and multiplayer coordination — all compiled to performant WASM modules that run in the browser.

### Core Principles

- **Rust everywhere**: All services, libraries, and performance-critical components are written in Rust to guarantee memory safety and optimal performance.
- **WASM for frontend**: The render layer targets WebAssembly, enabling near-native speed game logic in the browser without plugins.
- **Separation of concerns**: Game logic, engine mechanics, and platform services are decoupled through well-defined contracts.
- **Composability**: The package structure allows teams to compose game experiences from reusable engine and feature modules.
- **Security by default**: Input validation, secrets isolation, and audit logging are enforced at the architectural level.

## 2. Monorepo Structure

```
bkg/
├── apps/
│   ├── web/           # Axum web application + WASM frontend integration
│   └── jobs/          # Background worker for live events, queues, and async tasks
├── packages/
│   ├── agents/        # Agent runtime and orchestration
│   ├── ai/            # AI-driven game logic and NPC behavior
│   ├── animation-engine/  # Sprite and tween animation system
│   ├── audio-engine/  # Spatial audio and sound effect management
│   ├── auth/          # Authentication and authorization primitives
│   ├── config/        # Shared configuration and environment handling
│   ├── contracts/     # Service-to-service contracts (API types, serialization)
│   ├── database/      # Database access layer (SQLx), migrations, and connection pooling
│   ├── game-docs/     # Game format parsing and documentation tools
│   ├── game-engine/   # Core game loop, ECS, and entity management
│   ├── level-engine/  # Tilemaps, level parsing, and world serialization
│   ├── live-events/   # Real-time event broadcasting and subscription
│   ├── observability/ # Tracing, metrics, and structured logging
│   ├── pixel-engine/  # 2D pixel-perfect renderer and canvas abstraction
│   ├── testing/       # Test harnesses, fixtures, and integration helpers
│   ├── ui/            # Terminal-style and in-game UI components
│   ├── validation/    # Input validation, sanitization, and schema enforcement
│   └── voice/         # Voice integration and audio capture
├── docs/              # All project documentation
│   └── release-evidence/  # Per-release evidence artifacts
├── migrations/        # SQL migration files (SQLx)
├── scripts/           # Build, deploy, and operational scripts
└── tests/             # Integration and end-to-end test suites
```

### Directory Responsibilities

| Directory | Purpose |
|-----------|---------|
| `apps/web` | HTTP server (Axum) serving the WASM client, API routes, and webhooks. Primary user-facing service. |
| `apps/jobs` | Message-queue-driven worker process consuming Redis queues for long-running or scheduled tasks. |
| `packages/*` | Internal crates published within the Cargo workspace. Each is versioned and tested independently. |
| `docs/` | Architecture, security, onboarding, and release evidence. |
| `migrations/` | Versioned SQL schema migrations managed by SQLx. |
| `scripts/` | Shell and Rust utility scripts for setup, data loading, and maintenance. |
| `tests/` | Cross-cutting integration tests that require a full service stack. |

## 3. Service Architecture

### Web Application (`apps/web`)

The Axum-based web application serves as the primary API gateway and static asset server. It is responsible for:

- Serving the compiled WASM frontend bundle
- Providing REST and JSON-RPC endpoints consumed by the frontend
- Handling authentication flows and session management
- Proxying or delegating to specialized packages (e.g., `voice`, `ai`)

Communication with the jobs worker is asynchronous through Redis queues and PostgreSQL for shared state.

### Jobs Worker (`apps/jobs``)

The worker process handles event-driven and scheduled background workloads:

- Live event processing and fan-out (`live-events` package)
- Asset pipeline jobs (level compilation, sprite atlasing)
- AI inference queues (`ai` package)
- Scheduled maintenance tasks

The worker is horizontally scalable and stateless beyond Redis and PostgreSQL connections.

### API Boundaries

- **Public API**: Rate-limited, input-validated routes exposed through `apps/web`. All responses are JSON or binary WASM payloads.
- **Internal API**: Used by `apps/jobs` to enqueue work and query shared state. Not exposed publicly.
- **Module contracts**: Each `packages/*` crate exposes public APIs with internal modules kept private. Cross-package dependencies flow inward toward core packages (`config`, `contracts`, `validation`).

## 4. Data Flow Diagram

```
┌─────────────────────────────────────────────────────┐
│                    Browser (WASM)                    │
│  ┌──────────┐  ┌─────────────┐  ┌────────────────┐ │
│  │ pixel-   │  │ game-engine │  │   ui / input    │ │
│  │ engine   │◄─┤   (ECS)     │◄─┤   handling      │ │
│  └────┬─────┘  └──────┬──────┘  └────────────────┘ │
└───────┼───────────────┼────────────────────────────┘
        │  HTTP/REST     │  WebSocket (live-events)
        ▼               ▼
┌──────────────────────────────────────┐
│          apps/web (Axum)              │
│  ┌────────────┐  ┌────────────────┐  │
│  │   auth    │  │   API routes    │  │
│  └─────┬──────┘  └───────┬────────┘  │
│        │                 │              │
│        ▼                 ▼              │
│  ┌─────────────────────────────────┐   │
│  │     packages/* (logic layer)    │   │
│  └─────────────────────────────────┘   │
└──────────────┬──────────────┬──────────┘
               │              │
     ┌─────────▼──┐   ┌─────▼──────────┐
     │ PostgreSQL │   │     Redis      │
     │  (state)   │   │  (queues/cache)│
     └────────────┘   └────────────────┘
                                        ▲
                                        │ consumes
                              ┌────────▼────────────┐
                              │    apps/jobs         │
                              │  (background worker)│
                              └─────────────────────┘
```

## 5. Deployment Architecture

### Development

Docker Compose orchestrates the development stack:

- **PostgreSQL**: Primary relational datastore, running on the host network.
- **Redis**: Job queue backing and session cache.
- **MinIO**: S3-compatible object storage for game assets.
- **Local processes**: `apps/web` and `apps/jobs` run natively with hot-reload mounts for rapid iteration.

```bash
make dev-up   # Start infrastructure
make dev      # Run web server with watch
make jobs     # Run worker with watch
```

### Production Targets

- **Compute**: Container orchestration (Docker Swarm or Kubernetes) with separate replicas for `web` and `jobs` tiers.
- **Database**: Managed PostgreSQL with automated backups and read replicas.
- **Cache**: Managed Redis cluster with persistence enabled.
- **Storage**: S3-compatible service (MinIO or managed equivalent) for asset hosting.
- **Ingress**: TLS-terminating reverse proxy with WAF rules and DDoS mitigation.
- **Observability**: Centralized structured logging (OpenTelemetry), metrics scrape, and distributed tracing.

## 6. Technology Choices and Rationale

| Technology | Rationale |
|------------|-----------|
| **Rust** | Memory safety without garbage collection, zero-cost abstractions, and a mature async ecosystem. Critical for a platform where game logic must be deterministic and performant. |
| **WebAssembly (WASM)** | Enables Rust-compiled game logic to execute in the browser at near-native speed. WASM is the only portable, performant, sandboxed bytecode for the web. |
| **Axum** | Production-grade, Tokio-native web framework with strong type safety and first-class tower middleware support. |
| **SQLx** | Compile-time checked SQL queries with async support. Eliminates a large class of runtime errors without requiring an ORM. |
| **Redis** | Low-latency in-memory data store ideal for job queues, caching, and pub/sub live events. |
| **PostgreSQL** | ACID-compliant relational database with rich data types. Chosen for user profiles, game state persistence, and metadata. |
| **Docker Compose** | Provides reproducible development environments. The same Compose file for dev extends to staging via environment overrides. |
| **Tokio** | Industry-standard async runtime with excellent scheduling for both I/O-bound (web) and CPU-bound (game logic) workloads. |
| **MinIO** | Open-source, S3-compatible object storage. Essential for serving large game assets (sprites, audio, level data) with a standard API. |

### Why Not Other Stacks

- **No Next.js / React / TypeScript / Prisma / JSON-DB / Python / Go**: BKG is a Rust-native platform. WASM is the browser target, not a JS framework. Prisma and JSON-DB are rejected in favor of SQLx and PostgreSQL for type-safe, production-grade data management.
