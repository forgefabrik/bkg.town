# BKG Platform Security Documentation

## 1. Threat Model Overview

The BKG platform operates a multi-tier threat model:

### Assets to Protect
- **User accounts and credentials**: Authentication tokens, session identifiers, and personal data.
- **Game state and progression**: Persistent player data stored in PostgreSQL.
- **Platform integrity**: Game logic, asset pipeline, and server-side contracts.
- **Secrets**: Database credentials, Redis passwords, API keys, and signing keys.
- **Availability**: The platform must remain responsive under load and resistant to abuse.

### Threat Actors
- **External attackers**: Attempting account takeover, data exfiltration, or service disruption.
- **Malicious clients**: Tampered WASM modules or forged HTTP requests.
- **Privilege escalation**: Compromised service accounts or leaked credentials.
- **Supply chain**: Malicious dependencies or compromised build artifacts.

### Key Assumptions
- The transport layer is TLS-encrypted in production. Locally, HTTP is acceptable.
- The database and Redis are not publicly exposed; they are reachable only from within the application network.
- Secrets are injected via environment variables or a secrets manager, never embedded in source code or artifacts.

## 2. Authentication and Authorization Approach

BKG follows a token-based authentication model designed for stateless services:

- **Primary mechanism**: Short-lived access tokens (JWTs or opaque tokens signed with RS256) issued after credential verification.
- **Session persistence**: Refresh tokens stored as HTTP-only, Secure cookies with SameSite enforcement. Refresh tokens are long-lived and rotatable.
- **Authorization**: Role-based access control (RBAC) with `user`, `admin`, and `service` roles. Every handler enforces authorization via middleware extracted from the `auth` and `validation` packages.
- **WASM integration**: The frontend stores only an opaque session reference. All sensitive operations are performed server-side.

## 3. Secrets Management

### Rules
1. **Never commit secrets**: `.env` files, credentials, API keys, certificates, and private keys are listed in `.gitignore`.
2. **Environment variables**: All secrets are injected at runtime via environment variables. The `config` package provides typed access with validation.
3. **Development defaults**: `dev-vars-example` documents every required variable. Developers copy it to `.env` and fill in local-safe values.
4. **Production secrets**: Production deployments obtain secrets from a secrets manager or orchestration platform (e.g., Docker secrets, Kubernetes Secrets, Vault). Values are never checked into version control.
5. **Rotation**: Secrets are rotated on a defined schedule and immediately upon suspected compromise.

### Forbidden Patterns
- Hardcoding credentials in source code.
- Committing `.env` files.
- Logging secret values or headers.
- Transmitting secrets in URL query strings.

## 4. Input Validation Strategy

All input is considered untrusted. BKG uses a defense-in-depth validation strategy:

- **Schema validation**: Incoming payloads are deserialized into typed Rust structs using `serde` with strict settings. Unknown fields are rejected.
- **Semantic validation**: The `validation` package enforces business rules (e.g., name length, numeric bounds, enum membership) after structural parsing succeeds.
- **Allow-listing over block-listing**: Valid inputs are defined explicitly; anything not matching is rejected.
- **Unicode normalization**: All text inputs are normalized to NFC to prevent bypass via encoded look-alikes.
- **File uploads**: Uploaded assets are scanned for type, size, and content. Execution bits are stripped. Uploads are stored outside the web root with randomly generated names.

## 5. SQL Injection Prevention

- **Parameterized queries**: All database access uses prepared statements with bind parameters via SQLx. String concatenation into SQL is banned.
- **Compile-time verification**: SQLx verifies SQL syntax and table/column existence at compile time, catching typos before deployment.
- **Least-privilege connections**: The application database user has only the permissions required by the application (SELECT, INSERT, UPDATE, DELETE on designated tables). DDL rights are restricted to migration processes.
- **Migration review**: All SQL migrations are code-reviewed for injection vectors before merge.

## 6. XSS Prevention

- **Content security policy**: HTTP headers restrict script sources to the application origin. Inline scripts are blocked unless nonced.
- **Output encoding**: All dynamic content rendered in the WASM frontend is escaped at render time. The `ui` package provides a sanitiser for markdown and rich text.
- **CORS configuration**: The web application restricts Cross-Origin Resource Sharing to known origins. Credentials are not shared with third-party origins.
- **HTTP-only cookies**: Session identifiers are not accessible to JavaScript, limiting the impact of XSS even if rendering is compromised.

## 7. CSRF Protection

- **SameSite cookies**: Session cookies are set with `SameSite=Lax` or `Strict` to block cross-origin request forgery.
- **Anti-forgery tokens**: State-changing operations (POST, PUT, DELETE) require a token submitted via a custom header or form field. The token is tied to the session and rotated on use.
- **Idempotency keys**: For idempotent retry safety, mutations accept an idempotency key that prevents duplicate processing.
- **Origin validation**: Sensitive endpoints validate the `Origin` or `Referer` header against an allow-list.

## 8. Rate Limiting Approach

- **Token bucket algorithm**: Rate limits are enforced per user, per IP, and per endpoint using in-memory token buckets backed by Redis for distributed consistency.
- **Granular tiers**: Anonymous users receive stricter limits than authenticated users. Administrative endpoints have tightest limits.
- **Backpressure**: When limits are exceeded, the service returns `429 Too Many Requests` with a `Retry-After` header. Sustained abuse results in temporary IP or account suspension.
- **No reliance solely on client-side enforcement**: All rate-limiting logic runs server-side and cannot be bypassed by modifying client code.

## 9. Audit Logging Requirements

- **Security-relevant events**: Authentication success/failure, permission changes, admin actions, token issuance and revocation, and data export operations are logged immutably.
- **Log format**: Structured JSON logs with fields: `timestamp`, `actor_id`, `action`, `resource`, `outcome`, `source_ip`, `user_agent`, and `trace_id`.
- **Retention**: Security logs are retained for a minimum of 90 days, or as required by applicable regulation, in append-only storage.
- **Correlation**: A distributed `trace_id` is propagated across all services to allow end-to-end request reconstruction.
- **Tamper resistance**: Production audit logs are shipped to an external store with write-once semantics and access controlled separately from the application.

## 10. Security Review Process

1. **Design review**: Any change affecting authentication, authorization, cryptography, or data handling undergoes a security design review before implementation.
2. **Code review**: Security-sensitive code requires review from at least one engineer familiar with secure coding practices.
3. **Dependency audit**: Dependencies are audited for known vulnerabilities during CI. The `cargo audit` tool flags crates with published CVEs. Vulnerable dependencies must be updated or accepted with documented risk.
4. **Penetration testing**: Periodic external penetration testing is conducted before major releases and after significant architecture changes.
5. **Sign-off**: A security owner approves each release gate. Release gates without security sign-off cannot progress.

## 11. Vulnerability Reporting

BKG maintains a responsible disclosure policy:

- **Reporting channel**: Security vulnerabilities should be reported to `security@bkg.example` (replace with actual address). Do not file public issues for security bugs.
- **Expected timeline**: The security team acknowledges reports within 72 hours. A detailed response and remediation plan are provided within 14 days.
- **Scope**: The policy covers the BKG platform, its services, and official SDKs. Third-party integrations are excluded unless the vulnerability lies within BKG-controlled code.
- **Safe harbor**: Researchers acting in good faith and following responsible disclosure are exempt from legal action.
- **Recognition**: Coordinated disclosure allows for researcher credit in the release notes upon fix publication.

## 12. Additional Security Practices

- **Dependency pinning**: `Cargo.lock` is committed for applications. Crates are audited before upgrade.
- **Build reproducibility**: Release builds are reproducible and signed. The CI pipeline publishes SBOMs (Software Bill of Materials).
- **Least privilege**: Services run as non-root users in containers. Filesystem access is read-only wherever possible.
- **Network segmentation**: Services communicate on an internal Docker network. Only `apps/web` is exposed externally. `apps/jobs` and infrastructure services have no public ports.
- **Incident response**: A runbook exists for common security incidents (credential leak, DDoS, data breach). Runbooks are reviewed quarterly.
