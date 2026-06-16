# BKG: Rust + WASM Game Development Platform

BKG is an open-source game development platform built in Rust, targeting WebAssembly for high-performance browser games. It provides a complete toolchain — from game engine components and asset pipelines to live event systems and multiplayer coordination — all assembled from Rust crates compiled to WASM.

## Why BKG

Browser games today are often constrained by JavaScript performance or trapped behind plugin boundaries. BKG sidesteps both problems by compiling Rust code to WebAssembly, giving game developers near-native execution speed with the reach of the web.

- **Rust core**: Memory safety, zero-cost abstractions, and a powerful type system.
- **WASM deployment**: Write once in Rust, run in any modern browser without plugins.
- **Composable**: Mix and match game engine, audio, animation, and UI packages.
- **Production-ready**: Built-in observability, auth, and database integration.

## Quick Start

### Prerequisites

Install the following before getting started:

- **Rust** (stable toolchain, edition 2024): https://rustup.rs/
- **Docker** and **Docker Compose**: https://docs.docker.com/compose/install/
- **make**: Available on Linux and macOS via system package manager.

### Clone and Setup

```bash
git clone https://github.com/<org>/<bkg-repo>.git
cd bkg
cp dev-vars-example .env
make dev-up
make setup
```

### Run

```bash
# Terminal 1: Web application with hot reload
make dev

# Terminal 2: Background jobs worker
make jobs
```

Open `http://localhost:8080` (or the configured port) to see the running application.

### Test and Lint

```bash
make test   # Run all tests
make lint   # Format check + Clippy with warnings as errors
```

## Development Setup

### Rust Workspace

BKG is a Cargo workspace. The root `Cargo.toml` defines workspace members and shared dependencies. Each `packages/*` directory is an independent crate with its own `Cargo.toml`.

### Docker Compose

Development dependencies (PostgreSQL, Redis, MinIO) run in Docker Compose. Start them with `make dev-up`. Reset state with `make dev-reset`.

### Environment Variables

All configurable inputs are injected via environment variables. `dev-vars-example` documents every variable. Local overrides belong in `.env`, which is git-ignored.

## Project Structure

```
bkg/
├── apps/
│   ├── web/           # Axum web server + WASM frontend integration
│   └── jobs/          # Background worker for queues and async tasks
├── packages/
│   ├── agents/        # Agent runtime
│   ├── ai/            # AI-driven game logic
│   ├── animation-engine/  # Sprite and tween animation
│   ├── audio-engine/  # Spatial audio
│   ├── auth/          # Authentication primitives
│   ├── config/        # Shared configuration
│   ├── contracts/     # API types and serialization contracts
│   ├── database/      # SQLx data access layer
│   ├── game-docs/     # Game format tools
│   ├── game-engine/   # Core ECS and game loop
│   ├── level-engine/  # Tilemaps and world serialization
│   ├── live-events/   # Real-time event broadcasting
│   ├── observability/ # Tracing, metrics, logging
│   ├── pixel-engine/  # 2D pixel-perfect renderer
│   ├── testing/       # Test harnesses and fixtures
│   ├── ui/            # In-game UI components
│   ├── validation/    # Input validation and sanitization
│   └── voice/         # Voice integration
├── docs/              # Architecture, security, and release evidence
├── migrations/        # Versioned SQL migrations
├── scripts/           # Build and operational scripts
└── tests/             # Integration and end-to-end tests
```

## Documentation

| Document | Description |
|----------|-------------|
| `docs/ARCHITECTURE.md` | System overview, data flow, and deployment architecture |
| `docs/SECURITY.md` | Security policy, secrets management, threat model |
| `docs/RELEASE-EVIDENCE.md` | Release gate structure and evidence templates |
| `AGENTS.md` | This guide for contributors and agents working in the rig |

## Technology Stack

- **Language**: Rust (edition 2024)
- **Web framework**: Axum
- **Database**: PostgreSQL via SQLx
- **Cache / Queues**: Redis
- **Frontend**: WebAssembly (WASM) compiled from Rust
- **Asset storage**: MinIO (S3-compatible)

## Security

Security is a first-class concern. Please read `docs/SECURITY.md` before contributing. Key rules:

- Never commit secrets, keys, or tokens.
- Use environment variables for all configuration.
- Validate all inputs at the boundary.
- Use parameterized queries; never concatenate SQL.

## Contributing

See `AGENTS.md` for BKG-specific contribution guidelines, release processes, and how to run the project locally. General contribution guidelines and code of conduct will be added in a future release.

## License

See `LICENSE` file for details.
