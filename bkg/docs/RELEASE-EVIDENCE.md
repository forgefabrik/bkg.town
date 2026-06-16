# Release Evidence Template

This document defines the structure and requirements for release evidence artifacts stored in `docs/release-evidence/`.

## Purpose

Release evidence demonstrates that a given release candidate has passed all required quality, security, and operational gates before deployment to a target environment. It provides an auditable trail for compliance and operational confidence.

## Directory Structure

```
docs/
└── release-evidence/
    ├── .gitkeep
    └── <release-tag>/
        ├── summary.md
        └── evidence.json
```

- `.gitkeep`: Preserves the directory in version control.
- `<release-tag>`: A directory named after the release tag (e.g., `v0.1.0`). Contains all evidence artifacts for that release.

## Evidence Checklist

Every release must demonstrate the following before the gate is considered passed:

| Gate | Description | Evidence Required |
|------|-------------|-------------------|
| Build | All workspace crates compile without errors | CI build logs or local `cargo build --workspace` output |
| Format | Code passes `cargo fmt -- --check` | CI job log or terminal capture |
| Lint | Clippy reports no warnings (`-D warnings`) | CI job log |
| Tests | All tests pass (`cargo test --workspace`) | CI job log including test counts |
| Security scan | `cargo audit` reports no vulnerabilities (or accepted findings documented) | CI job log |
| Documentation | All required docs exist and link correctly | File list and link-check result |
| Migration sanity | Migrations apply cleanly to a fresh database | CI job log |
| Performance baseline | Benchmark delta within acceptable threshold | Benchmark report (future) |

## Evidence Entry Template

Each release gate entry follows this structure:

### `summary.md`

```markdown
# Release Evidence: <release-tag>

**Date**: YYYY-MM-DD
**Commit**: <full SHA>
**Branch**: <branch name>
**Gate owner**: <agent or human reviewer>

## Gate Results

| Gate | Status | Notes |
|------|--------|-------|
| Build | Pass / Fail | |
| Format | Pass / Fail | |
| Lint | Pass / Fail | |
| Tests | Pass / Fail | |
| Security scan | Pass / Fail / Accepted | |
| Documentation | Pass / Fail | |
| Migration sanity | Pass / Fail | |

## Overall Status

**Passed**: Yes / No
**Blockers**: None or list of blocking findings
**Approved by**: <name> on <date>
```

### `evidence.json`

```json
{
  "release_tag": "<release-tag>",
  "commit_sha": "<full SHA>",
  "timestamp": "<ISO 8601 UTC>",
  "gates": {
    "build": { "status": "pass", "duration_ms": 0, "artifact_path": "" },
    "format": { "status": "pass", "duration_ms": 0 },
    "lint": { "status": "pass", "duration_ms": 0 },
    "tests": { "status": "pass", "duration_ms": 0, "passed": 0, "failed": 0 },
    "security_scan": { "status": "pass", "duration_ms": 0, "advisory_count": 0 },
    "documentation": { "status": "pass", "checks": {} },
    "migrations": { "status": "pass", "duration_ms": 0 }
  },
  "overall": "pass",
  "blockers": [],
  "approved_by": "",
  "approved_at": ""
}
```

## Usage

1. At the start of a release, create the `<release-tag>` directory under `docs/release-evidence/`.
2. Run the full CI gate suite locally or observe the CI run.
3. Populate `summary.md` and `evidence.json` with observed results.
4. Any failed or accepted findings require explicit owner sign-off and documented remediation plan.
5. A release may not proceed to deployment until all non-accepted gates pass and the overall status is `pass`.

## Links

- Full architecture documentation: `docs/ARCHITECTURE.md`
- Security policy: `docs/SECURITY.md`
- Release process: `AGENTS.md`
