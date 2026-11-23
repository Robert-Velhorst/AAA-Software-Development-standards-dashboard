# AAA — Software Development Standards Dashboard (`AAA-Software-Development-standards-dashboard`): Master Technical & Feature Specification

| Field | Value |
| --- | --- |
| **Repo ID** | `AAA` |
| **Repository** | `Robert-Velhorst/AAA-Software-Development-standards-dashboard` ([GitHub](https://github.com/Robert-Velhorst/AAA-Software-Development-standards-dashboard)) |
| **Canonical GitHub Path** | `docs/MASTER_PLAN.md` |
| **Canonical Drive Doc** | `2026-11-23 \| NOB \| AAA \| Software Development Standards Dashboard \| Master Technical & Feature Specification` (Internal Private Google Doc (redacted in public repository)) |
| **Document Track** | `Master Technical & Feature Specification` |
| **Authoritative Owner Classification (2026-11-20)** | Internal Engineering Governance Dashboard (Public Repo During Active Dev) / Open-Source Software Development Standards & Compliance Dashboard (Apache-2.0) |
| **Consolidation / Portfolio Role** | Standalone Engineering Governance & Standards Control Plane (Active Public Apache-2.0 Repo; Zero Consolidation or Retirement) |
| **Pricing / Governance Model** | N/A — Non-commercial internal engineering governance & open-source compliance dashboard (Apache-2.0; zero commercial SaaS pricing; Hetzner self-hosted cost-frugality posture) |
| **Hosting Target** | Hetzner EU (self-hosted authenticated operator access; Vercel & unapproved serverless hosting permanently removed via PR `#3`) |
| **As-Of Date** | `2026-11-23` |
| **Current Stage & Readiness** | `01 - Empty Skeleton (0%)` — `Spec Only` (0% code readiness; planning & governance docs only) |
| **Feature Completeness** | `0%` (`0/6` proposed checklist capabilities in `dev/FEATURES.md`; `7` open backlog issues `#5`-`#11`) |
| **Codebase Scale** | `13` tracked repository blobs/files, `0` LOC, `Markdown Stub Only` (`0/21` 4-Pillar verification layers confirmed) |
| **Merged Prior Sources** | `2026-11-15 \| NOB \| AAA \| Executive Summary (Operational Charter)`, `2026-11-20 Authoritative Owner Direction (/grill-me Locked Direction)`, `PROJECT_DIRECTION.md`, `DEPLOYMENT_TARGET.md`, `README.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `LICENSE` (Apache-2.0), `.github/pull_request_template.md`, `.github/dependabot.yml`, `.github/ISSUE_TEMPLATE/*`, GitHub Issues `#5`-`#11` |

---

## 1. Operational Charter, Mission & Authoritative Owner Direction (2026-11-20)

### 1.1 Mission & Operational Purpose

`AAA` (`Robert-Velhorst/AAA-Software-Development-standards-dashboard`) is a **Greenfield Operational Charter** designed to serve as an automated software development standards, compliance, and engineering-hygiene control plane across multi-repository software portfolios. Rather than relying on manual status spreadsheets, ad-hoc shell scripts, or periodic point-in-time inventory sweeps that go stale within days, `AAA` continuously ingests repository signals—CI workflow pass rates, security and dependency advisories, license and documentation hygiene, deployment-target compliance, GitHub ProjectV2 progress, and optional external verification snapshots—into a durable, queryable, exception-first compliance dashboard.

Crucially, `AAA` operates under a **dual-context open-source and internal-governance mandate** locked on `2026-11-20`:

1. **Open-Source Public Codebase (`Apache-2.0`):** Because an external software developer is actively collaborating on the project, the repository itself remains intentionally **Public** under the **Apache License 2.0** (`LICENSE`). All source code, schemas, synthetic test fixtures, Docker/Caddy templates, and documentation MUST be completely generic, configurable, and free of any private portfolio data.
2. **Self-Hosted Internal Operator Deployment (Hetzner EU):** When deployed by an organization or engineering lead to monitor live portfolios (including private repositories), the running dashboard operates behind mandatory operator authentication on self-hosted **Hetzner EU** infrastructure. Private repository lists, internal audit datasets, GitHub tokens, and compliance telemetry exist exclusively in authenticated runtime storage and are strictly barred from entering version control.

### 1.2 Beneficiaries & Primary Operators

- **Engineering Lead / Portfolio Maintainer:** Uses `AAA` as a daily engineering control plane to spot regressions across dozens of repositories (for example, `40+` repositories spanning Greenfield prototypes, active MVPs, and production services) in seconds rather than hours.
- **External & Open-Source Contributors:** Develop, test, and extend `AAA` locally against synthetic mock repositories (`example-org/example-repo-a`, `example-org/portfolio-service-1`) without needing access to private production targets or credentials.
- **AI Coding Agents & CI Pipelines:** Consume deterministic JSON schemas, issue-priority rules, and machine-readable compliance reports (`docs/MASTER_PLAN.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`, `/api/v1/standards/*`) so automated quality checks and remediation workflows operate against an explicit contract.

### 1.3 Operational Value & Cost-Frugality Posture

Because `AAA` is governed strictly as an **Operational Charter** (`N/A` commercial SaaS pricing; zero multi-tenant billing or subscription tiers), its return on investment is measured purely in **engineering hours recovered**, **security/compliance drift prevented**, and **infrastructure frugality**:

- **Time Saved (Planning Hypothesis — Validation Gate `VG-01`):** Manual cross-portfolio hygiene reviews across `40+` repositories typically consume `2-4` hours per audit cycle and miss regressions between cycles. Automated ingestion reduces portfolio triage to a sub-`5` minute daily exception check while keeping historical compliance snapshots intact.
- **Risk Reduction:** Surfaces unresolved dependency advisories, unprotected default branches, missing `SECURITY.md` or `LICENSE` files, missing CI workflows, stale documentation, and unauthorized hosting drift (such as re-introduced serverless/Vercel configs prohibited by `DEPLOYMENT_TARGET.md`) immediately after commits land.
- **Infrastructure Cost-Frugality Target:** Designed as a lightweight, single-container or two-container Hetzner EU workload (`<= 256 MB` steady-state RAM, SQLite WAL embedded storage with zero managed-database fees). Can run alongside existing services on an existing Hetzner node (`EUR 0` incremental infra cost) or on a dedicated entry-level Hetzner cloud instance (`~EUR 4-7/month` planning estimate), with zero paid SaaS dependencies.

### 1.4 Authoritative 2026-11-20 Locked Decisions

Every engineering, packaging, and governance decision in this specification honors all locked directives from `2026-11-20` (`PROJECT_DIRECTION.md` commit `3762c49` and the internal `/grill-me` Operational Charter):

1. **Repo Visibility (`2026-11-20`):** Keep `AAA` **Public (`Apache-2.0`)** during active development so the external developer can contribute directly via standard GitHub pull requests.
2. **Strict Public/Private Security Boundary:** Never commit private repository names, internal audit counts, private Drive URLs, internal server IP addresses, personal email addresses, production backups, or access tokens into git history, tests, screenshots, or documentation.
3. **Hosting Target (`DEPLOYMENT_TARGET.md`, PR `#3` commit `084a164`):** Production hosting is locked to **Hetzner EU** behind authenticated operator access. Vercel and unapproved serverless or public-tunnel hosting are permanently banned for production deployments.
4. **Build Sequencing Discipline:** Resolve foundational specification, standards schema, CI baseline (`#5 [S0-01]`), auth/token safety (`#6 [S1-01]`), ingestion/persistence (`#7 [S3-01]`), UI (`#8 [S5-01]`), Hetzner packaging (`#9 [S7-01]`), and test/accessibility verification (`#10 [S8-01]`) **before** undertaking premature transport/performance optimizations (`#11 [SPEED-01]`).

---

## 2. Historical Source Reconciliation & Prior-Plan Assessment Ledger

As of `2026-11-23`, `AAA` has zero historical commercial business plans in Google Drive; all planning context originates from the internal `2026-11-15 / 2026-11-20` Operational Charter (`00_live_exec_summary_2026-11-20.md`), the repository's `2026-10` and `2026-11-20` governance files, and the `7` structured GitHub issues (`#5`-`#11`) opened on `2026-11-13`. Every source artifact is reconciled below.

| Legacy Source (Title & Date) | Concept / Requirement / Figure | Assessment (Retained / Adapted / Deferred to v2+ / Superseded) | Reconciliation Rationale & Where Integrated |
| --- | --- | --- | --- |
| `2026-11-15 \| NOB \| AAA \| Software Development Standards Dashboard \| Executive Summary (Operational Charter)` & `2026-11-20` `/grill-me` Locked Direction (Internal Private Google Doc (redacted in public repository)) | Greenfield `0%` status (`10` files pre-`11-20`, `0` LOC); internal governance posture; stay Public Apache-2.0 for external developer; strict exclusion of private repo lists/audit outputs/tokens/IPs; Hetzner EU authenticated target; SQLite persistence (`#7`); `30-90` day gate plan; Risk #1 premature optimization on `#11`; Risk #2 potential duplication with external static JSON portfolio inventory scripts; Risk #3 GitHub API rate limits & PAT scope. | **Retained & Operationalized** | Serves as the primary governance baseline across Sections 1, 3, 4, 5, 6, and 7. File count reconciled from `10` (`2026-11-15`) to `13` (`2026-11-23`) following commits `3762c49` and `559853d`. External JSON snapshot ingestion adapter explicitly reconciles Risk #2 (Section 4.2 & 5.4). |
| `PROJECT_DIRECTION.md` (`2026-11-20`, commit `3762c49`) | Frames `AAA` for the public repo as an Open-Source Software Development Standards & Compliance Dashboard (`Apache-2.0`), tracking CI pass rates, security advisories, docs/license hygiene, and Hetzner readiness behind self-hosted authenticated access. | **Retained (Reconciled)** | Harmonized with the internal charter in Section 1.1: same software, `Apache-2.0` public source code, operated privately on Hetzner EU with zero private data in version control. |
| `DEPLOYMENT_TARGET.md` (`2026-10-13` `ca41c87` & `2026-10-18` PR `#3` `084a164`) | Mandates Hetzner production target; permanently removes Vercel integrations; prohibits unapproved serverless/public-tunnel production deployments; requires documented infra, DB migration, DNS/TLS, secrets, monitoring, backups, and rollback prior to cutover. | **Retained (Hard Constraint)** | Integrated into Section 1.4, Section 4.2 (`FEAT-07`), and Section 5.5 deployment/cutover checklist. |
| `README.md` (`2026-07-25` initial 46-byte 1-line stub -> `2026-11-20` `3762c49` 12-line / 733-byte header) | Initial 1-line stub evolved into an Authoritative Direction banner linking `PROJECT_DIRECTION.md`, `dev/FEATURES.md`, and `dev/TEST-RESULTS.md`, but still lacks architecture overview, stack quickstart, and contributor onboarding. | **Superseded / Expansion Required** | Retained links to `PROJECT_DIRECTION.md` and `dev/*`; expanding `README.md` with full local synthetic quickstart and `docs/MASTER_PLAN.md` pointer is scheduled in `DIR-01` (`#5 [S0-01]`). |
| `dev/FEATURES.md` (`2026-11-20`, commit `559853d`) | Lists `6` proposed checklist items: CI pass-rate dashboard, security advisory tracking, docs/license hygiene tracking, Hetzner readiness tracking, self-hosted authenticated operator access, isolated runtime data & private repo access. All `6` unchecked. | **Retained** | All `6` capabilities mapped 1:1 into `FEAT-02` through `FEAT-08` and `FEAT-10`/`FEAT-11` in Section 4.2. |
| `dev/TEST-RESULTS.md` (`2026-11-20`, commit `559853d`) | Confirms zero GitHub Actions workflow runs, zero executable test entry points, and doc-link validation only at revision `3762c4972faf`. | **Retained (Baseline Fact)** | Anchors Section 6 build reality (`0%` test coverage, `No CI`, `0/21` 4-Pillar layers confirmed). |
| `LICENSE` (`2026-07-25`), `SECURITY.md` (`2026-10-17` PR `#1`), `CONTRIBUTING.md` (`2026-10-16` PR `#2`), `CODE_OF_CONDUCT.md`, `.github/*` | Establishes `Apache-2.0` licensing, private vulnerability disclosure, synthetic-example rule in PRs, Dependabot config, and PR risk checklist. Notes factual discrepancy where automated dossier summary text (`what_is_built`) mistakenly wrote `"MIT license"`, and `CODE_OF_CONDUCT.md` line 19 contains a maintainer personal email string. | **Retained & Audited** | Verified `Apache-2.0` as canonical license (superseding `"MIT"` prose artifact in dossier summary). Added `DIR-00` hygiene task to replace raw personal email reference in `CODE_OF_CONDUCT.md` with a dedicated non-personal conduct alias or GitHub private reporting route while preserving contributor safety. |
| GitHub Issues `#5` (`[S0-01]`), `#6` (`[S1-01]`), `#7` (`[S3-01]`), `#8` (`[S5-01]`), `#9` (`[S7-01]`), `#10` (`[S8-01]`) (`2026-11-13`) | Structured engineering roadmap issues covering product spec/contract/CI, auth/least-privilege tokens/security headers, GitHub/CI/ProjectV2 ingestion + durable storage, compliance UI/drilldown, Hetzner deploy/backups/monitoring, and unit/integration/Playwright/WCAG 2.2 AA tests. All have `labels: []`. | **Retained (Sequenced)** | Directly drives Section 4, Section 5, and Section 6 Directives `DIR-01` through `DIR-07`. Issue label hygiene remediation captured in `DIR-00`. |
| GitHub Issue `#11` (`[SPEED-01]`, `2026-11-13`) | Demands Zero-Wait architecture (local-first SWR, SSE push, sub-`10ms` DB queries, Hetzner HTTP/3, CI latency gates) inside the MVP scaffold. | **Adapted / Deferred to Gate 3** | Per `2026-11-20` Operational Charter Risk #1, deferring full SWR/SSE/HTTP/3/latency-gate implementation until after Gate 2 end-to-end compliance scoring avoids premature complexity on a `0-LOC` codebase. However, SQLite WAL + covering indexes + clean SSE-friendly boundaries are baked into Section 5 so Gate 3 (`DIR-08`) adds `#11` cleanly without rewrites. |
| External Portfolio Audit Dossier Schema (`four_pillar_matrix_summary` 21-layer verification model) | Evaluates repositories across Pillar 1 (`p1_*` code/hygiene), Pillar 2 (`p2_*` performance/load), Pillar 3 (`p3_*` resource/observability), and Pillar 4 (`p4_*` security/AI safety/licenses) alongside static JSON snapshots. | **Adapted** | Integrated into `AAA`'s `PortfolioSnapshotImport` schema (`FEAT-09`, Section 5.3 & 5.4) so `AAA` ingests external 4-Pillar and local worktree JSON audits rather than duplicating local CLI scanners. |

---

## 3. Problem Domain, Operators, Workflows & Non-Negotiable Boundaries

### 3.1 Operational Friction Solved

Multi-repository engineering teams accumulate silent technical debt faster than manual reviews can detect it:

1. **Invisible CI & Security Decay:** Repositories pass an initial prototype sprint and then accumulate failing scheduled builds, disabled workflows, or critical npm/pip/Go advisories without an engineer opening each repo tab individually.
2. **Governance & Documentation Drift:** Files such as `LICENSE`, `SECURITY.md`, `DEPLOYMENT_TARGET.md`, `PROJECT_DIRECTION.md`, and `docs/MASTER_PLAN.md` fall out of sync, or contributors introduce unapproved hosting providers (e.g., `vercel.json`) despite explicit architecture rules.
3. **Unlabeled & Stale Roadmaps:** Tracking issues use naming conventions (`[S0-01]`, `[S5-01]`) in titles while leaving GitHub `labels` empty (`roadmap_s_open: null`), breaking automated stage tracking across portfolios.
4. **Public/Private Collaboration Leakage Risk:** When an open-source contributor or coding agent assists on tooling, sharing raw portfolio audit sheets exposes private project names, infrastructure IPs, and security weaknesses.
5. **Local-Only Blind Spots:** Purely GitHub-API dashboards cannot see dirty local git worktrees or offline 4-Pillar verification suites unless an authenticated snapshot import bridge captures them.

### 3.2 Operator Ergonomics & Workflow Principles

- **Exception-First Triage:** The default landing screen answers *"What needs engineering attention right now?"*—surfacing critical advisories, CI breaks, deployment-target drift, and stale sync health before green compliance badges.
- **Deterministic Explainability:** Every repository score (`0-100`) and pass/warn/fail badge traces back to explicit, human-readable rule evaluations (e.g., `DOC-002: SECURITY.md missing on default branch`) rather than opaque heuristics.
- **Zero-Friction Keyboard & Screen-Reader Accessibility (`#10 [S8-01]`):** Target **WCAG 2.2 AA** compliance—semantic HTML landmarks, visible focus rings, keyboard-only table sorting/drilldown, accessible color contrast independent of red/green color alone (explicit text status pills + icons).
- **Synthetic-First Local Development:** Any external contributor clones `AAA`, runs one command (`npm run dev:synthetic` or equivalent), and works against realistic, 100% synthetic example repositories (`example-org/example-repo-a`, `example-org/portfolio-service-1`) stored in a local gitignored SQLite file.

### 3.3 Legal, Platform ToS, Privacy & Security Boundaries

1. **Public-Repo Sanitization Gate (Non-Negotiable):** Because `AAA` is a public `Apache-2.0` repository, **zero** private repository names, private organization repo lists, internal audit numbers, internal server IP addresses, personal email addresses, production backups, or access tokens may ever be committed. CI MUST enforce automated secret scanning (`gitleaks`) and pattern hygiene checks on every PR.
2. **GitHub Platform ToS & Rate-Limit Stewardship:** All GitHub REST and GraphQL ingestion MUST authenticate via a least-privilege GitHub App installation token or fine-grained read-only PAT, use `User-Agent` headers, honor `ETag` / `If-None-Match` conditional caching (304 responses cost zero primary rate-limit quota), batch metadata via GraphQL where appropriate, and immediately honor `Retry-After` / `X-RateLimit-Remaining` backoff floors.
3. **Least-Privilege Read-Only Execution Boundary (`#6 [S1-01]`):** `AAA` possesses **zero write authority** over monitored repositories. Tokens MUST NOT hold `contents:write`, `administration:write`, `packages:write`, or deletion permissions. `AAA` never pushes commits, opens PRs automatically, or modifies remote infrastructure.
4. **Privacy & GDPR Minimization:** `AAA` audits *repository artifacts and system states*, NOT individual developer performance. Commit author personal emails and IP addresses are excluded from persistent compliance tables; authentication rate-limit counters hash/truncate client IPs transiently in memory/short TTL stores and session audit logs store only operator IDs and timestamps.
5. **Fail-Closed Operator Authentication (`#6 [S1-01]`):** In production (`NODE_ENV=production` or `AAA_ENV=production`), the application MUST refuse to bind or serve API/UI routes if `AAA_SESSION_SECRET` or operator credentials are unset, weak, or defaulting to development bypasses.
6. **Zero Financial Authority:** `AAA` connects to zero payment gateways, invoicing APIs, or commercial billing engines.

### 3.4 Explicit Non-Goals

- **Not a Commercial Multi-Tenant SaaS:** No user self-signup, Stripe integration, tenant billing plans, or public anonymous dashboard exposure.
- **Not a CI/CD Execution Engine:** `AAA` ingests workflow statuses from GitHub Actions and external test reports; it does not provision runners to build external repositories.
- **Not an Autonomous Code Mutator:** Remediation hints show exact commands or missing files for human engineers or authorized local workflows to apply deliberately; `AAA` never auto-commits to tracked repositories.
- **Not Serverless / Vercel:** Permanently excluded per `DEPLOYMENT_TARGET.md` and PR `#3`.

---

## 4. Exhaustive Feature Specification & System Mechanics (How the Tool Works)

### 4.1 End-to-End Operational Mechanics & Execution Flows

Because `AAA` currently contains `0` LOC, the following operational mechanics define the exact runtime behavior to be implemented across Gates 1-3 (`#5`-`#11`).

#### Flow A: Fail-Closed Bootstrap & Runtime Configuration
1. On process start, the server reads environment variables and mounts the runtime config directory (e.g., `/data` on Hetzner, `./.local-dev` locally, both excluded from git via `.gitignore`).
2. Startup validation asserts:
   - `AAA_ENV=production` requires non-empty `AAA_SESSION_SECRET` (`>= 32` random bytes), valid `AAA_OPERATOR_PASSWORD_HASH` (Argon2id/scrypt) or configured OIDC provider, and a reachable `AAA_TARGETS_PATH` (or initialized `repositories` table). Missing any required security variable aborts startup with exit code `1`.
   - `AAA_ENV=synthetic` (development/CI only) disables outbound GitHub calls and seeds synthetic fixture repositories (`example-org/example-repo-a`, etc.) into a local ephemeral SQLite database.
3. SQLite opens in WAL mode (`PRAGMA journal_mode = WAL; PRAGMA foreign_keys = ON; PRAGMA busy_timeout = 5000;`), applies versioned SQL migrations cleanly inside a transaction, and binds strictly to loopback (`127.0.0.1:8080` in Docker behind Caddy TLS).

#### Flow B: Operator Authentication & Access Control
1. Unauthenticated requests to `/`, `/api/v1/dashboard/*`, `/api/v1/repos/*`, or `/api/v1/events/stream` receive `401 Unauthorized` (API) or redirect to `/login` (browser). Only `/api/healthz` (returning minimal `{"status":"ok"}` without version/repo leakage) and `/login` are unauthenticated.
2. Operator submits credentials to `POST /api/v1/auth/login` (rate-limited: max `5` attempts per `15` minutes per IP + exponential lockout).
3. On verification, the server issues an `HttpOnly`, `Secure`, `SameSite=Strict` session cookie backed by a server-side hashed session token in `operator_sessions` (default `12h` idle / `7d` absolute expiry) plus a synchronizer CSRF token for all `POST`/`PUT`/`PATCH`/`DELETE` routes.

#### Flow C: GitHub Repository, CI, Security & ProjectV2 Ingestion (`#7 [S3-01]`)
1. Triggered either by the internal cron scheduler (default every `15` minutes for fast CI/PR checks, every `60` minutes for full docs/advisories/ProjectV2 sweeps) or manually via `POST /api/v1/sync/run` (operator UI button / CLI).
2. If `INGESTION_PAUSED=true`, scheduled runs log a skipped entry and return safely.
3. The ingestion worker loads active target repositories from runtime `targets.yaml` / `repositories` table (never hardcoded in source).
4. For each repository (bounded concurrency, default `3` workers):
   - Checks remaining GitHub API rate limit (`X-RateLimit-Remaining`); if below `150`, pauses non-urgent jobs until reset timestamp and marks `sync_runs.status = 'rate_limited_partial'`.
   - Sends `GET /repos/{owner}/{repo}` with stored `etag`; HTTP `304 Not Modified` skips redundant payload parsing.
   - Fetches branch protection status (gracefully handles `403` when token lacks admin access, recording `unknown_insufficient_scope` rather than crashing).
   - Fetches recent GitHub Actions workflow runs (`/actions/runs?per_page=20`) to compute `ci_pass_rate_20` and `last_ci_status`.
   - Fetches Dependabot / vulnerability alerts (`/dependabot/alerts?state=open&per_page=100`) grouped by `critical`, `high`, `medium`, `low`.
   - Checks existence/metadata of standard governance files on the default branch (`LICENSE`, `README.md`, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `DEPLOYMENT_TARGET.md`, `PROJECT_DIRECTION.md`, `docs/MASTER_PLAN.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`, and checks for forbidden drift files like `vercel.json`).
   - Fetches open issues (`GET /repos/{owner}/{repo}/issues?state=open`) to detect untagged roadmap issues (`labels.length === 0` despite `[S*-01]` title prefix).
   - Queries GraphQL ProjectV2 items linked to the configured organization/user project board (optional per target config).
5. The Standards Rule Engine evaluates each repository against declarative rules in `standards_rules`, computes deterministic weighted compliance score (`0-100`) and pillar sub-scores, and commits a snapshot atomically inside a SQLite transaction. If one repository returns `404` or transient `5xx`, the worker records `repo_sync_error` for that single repository and continues the batch without losing healthy data.

#### Flow D: External Snapshot & 4-Pillar Audit Import (`PortfolioSnapshotImport`)
1. Because GitHub APIs cannot observe local uncommitted git worktree changes or private runtime 4-Pillar test executions (`p1_*`..`p4_*`), external CI jobs or local collector CLI scripts push signed/authenticated JSON payloads to `POST /api/v1/imports/snapshot` (authenticated via dedicated scoped machine API token or operator session).
2. Payload validates strictly against `PortfolioSnapshotImportV1` (Zod schema).
3. Validated data updates `four_pillar_audits` and optional `local_worktree_state` (`clean` / `dirty` + timestamp) inside SQLite, factoring into the repository's overall readiness view with explicit source attribution (`source: "github_api" | "snapshot_import"`).

#### Flow E: Compliance Dashboard, Drilldown & Triage (`#8 [S5-01]`)
1. Operator opens the web UI:
   - **KPI Strip:** Total tracked repos, Mean Compliance Score, Repos with Critical/High Advisories, Failing CI Repos, Hetzner Drift Violations, Stale/Error Sync Warnings.
   - **Filterable Portfolio Matrix:** Sort/filter by compliance tier (`Red 0-59`, `Amber 60-84`, `Green 85-100`), hosting compliance, open advisories, CI status, or stage/category tag.
   - **Per-Repository Drilldown (`/repos/:slug`):** Shows complete rule-by-rule checklist (Pass / Warn / Fail / Not Applicable / Insufficient Scope), recent 20 CI workflow runs, open Dependabot advisories by package & severity, ProjectV2 status items, 21-layer 4-Pillar audit grid (if imported), 30-day compliance score trend chart, and copyable remediation guidance (e.g., `"Add SECURITY.md using repository template"`).
2. In Gate 3 (`#11 [SPEED-01]`), live sync completion pushes incremental events over `GET /api/v1/events/stream` (SSE) so open operator tabs update smoothly via SWR without manual reloads.

### 4.2 Complete Feature Capability Matrix

| Feature ID | Module / Subsystem | Exact Behavior & Operator Flow | Status | Codebase Anchors | Target Acceptance Criteria |
| --- | --- | --- | --- | --- | --- |
| `FEAT-01` | Standards Schema & Rule Engine (`#5 [S0-01]`) | Declarative, versioned rule catalog (`schema_version: "1.0"`) evaluating CI, Security, Docs/License, Hetzner Readiness, and Roadmap hygiene into deterministic `0-100` scores with per-rule evidence. | `Unbuilt Spec` | Planned: `packages/schema/src/standards.ts`, `apps/server/src/engine/evaluator.ts` (Issue `#5`) | Rules validated via Zod; 100% deterministic unit-tested scoring across synthetic pass/warn/fail fixtures; zero hardcoded private repo names. |
| `FEAT-02` | Operator Auth, Sessions & Security Headers (`#6 [S1-01]`) | Argon2id/scrypt operator login, rate-limited `/auth/login`, `HttpOnly/Secure/SameSite=Strict` cookies, CSRF protection, strict CSP/HSTS/XFO headers, fail-closed prod boot checks. | `Unbuilt Spec` | Planned: `apps/server/src/auth/*`, `apps/server/src/plugins/security.ts` (Issue `#6`, `dev/FEATURES.md`) | Unauthenticated requests to any `/api/v1/*` route (except `/api/healthz` & `/auth/login`) return `401`; prod boot exits non-zero if `AAA_SESSION_SECRET` missing; security headers verified by integration tests. |
| `FEAT-03` | Least-Privilege Token Vault & Runtime Target Registry (`#6 [S1-01]`) | Reads repository allowlist and read-only GitHub PAT / GitHub App installation credentials exclusively from Hetzner runtime config/env; blocks token exposure in API responses or logs. | `Unbuilt Spec` | Planned: `apps/server/src/config/targets.ts`, `apps/server/src/github/auth.ts` (Issue `#6`, `PROJECT_DIRECTION.md`) | Runtime secret redaction filter prevents token leaks in logs/JSON; GitHub token scope verifier warns/alerts if overly broad write/admin permissions are detected. |
| `FEAT-04` | Repository Metadata, License & Doc Hygiene Collector (`#7 [S3-01]`) | Checks SPDX license match (`Apache-2.0`, `MIT`, etc.), `README.md` non-stub size/freshness, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `PROJECT_DIRECTION.md`, `docs/MASTER_PLAN.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`, and branch protection. | `Unbuilt Spec` | Planned: `apps/server/src/github/collectors/docs.ts` (Issue `#7`, `dev/FEATURES.md`) | Accurately detects missing/stubbed docs and SPDX license on synthetic repos using `ETag` conditional caching. |
| `FEAT-05` | CI Pass-Rate & GitHub Actions Collector (`#7 [S3-01]`) | Polls recent GitHub Actions runs per repo, calculates rolling `N=20` pass rate, consecutive failure count, and flags `No CI` repositories. | `Unbuilt Spec` | Planned: `apps/server/src/github/collectors/ci.ts` (Issue `#7`, `dev/FEATURES.md`) | Correctly calculates pass %, latest conclusion, and workflow count across mocked Actions API responses including empty-CI repos. |
| `FEAT-06` | Security Advisory & Alert Collector (`#7 [S3-01]`) | Ingests open Dependabot alerts (and optional code/secret-scanning summaries if authorized), categorizing counts by `critical`, `high`, `medium`, `low` and age. | `Unbuilt Spec` | Planned: `apps/server/src/github/collectors/security.ts` (Issue `#7`, `dev/FEATURES.md`) | Correctly maps severity counts and degrades cleanly with explicit `insufficient_scope` status if repository security alerts API returns `403`. |
| `FEAT-07` | Hetzner Deployment Target & Drift Validator (`DEPLOYMENT_TARGET.md`) | Verifies `DEPLOYMENT_TARGET.md` presence, scans repo tree for prohibited deployment artifacts (`vercel.json`, `.vercel/`, unapproved serverless configs), and tracks Docker/Compose/backup readiness flags. | `Unbuilt Spec` | Planned: `apps/server/src/github/collectors/deployment.ts` (`DEPLOYMENT_TARGET.md`, `dev/FEATURES.md`) | Flags `vercel.json` or missing `DEPLOYMENT_TARGET.md` as explicit compliance violations on applicable service repos; supports `not_applicable` override for pure libraries/CLI tools. |
| `FEAT-08` | GitHub ProjectV2 & Issue/Roadmap Hygiene Collector (`#7 [S3-01]`) | Queries GraphQL ProjectV2 board statuses alongside open issue/PR counts; flags unlabeled `[S*-01]` roadmap issues (`labels.length === 0`) and stale PRs. | `Unbuilt Spec` | Planned: `apps/server/src/github/collectors/projectv2.ts` (Issue `#7`) | GraphQL query batches fields within rate budget; accurately surfaces `unlabeled_roadmap_issues` count when issues match `^\[S\d+-\d+\]` without GitHub labels. |
| `FEAT-09` | External Snapshot & 4-Pillar Audit JSON Importer | Authenticated `POST /api/v1/imports/snapshot` endpoint + CLI ingesting external JSON audit payloads (21-layer `p1_*`-`p4_*` matrix + local git worktree dirty/clean states). | `Unbuilt Spec` | Planned: `apps/server/src/imports/snapshot.ts`, `packages/schema/src/snapshot.ts` (Charter Risk #2 resolution) | Validates `PortfolioSnapshotImportV1` strictly; rejects malformed JSON (`400`) and unknown repo tokens (`403`); merges cleanly without overwriting live GitHub API timestamps. |
| `FEAT-10` | Compliance Dashboard Portfolio Matrix UI (`#8 [S5-01]`) | Authenticated operator view displaying KPI summary cards, filter/sort portfolio table, exception triage queue, and manual sync trigger with fresh/stale timestamp banner. | `Unbuilt Spec` | Planned: `apps/web/src/pages/DashboardPage.tsx` (Issue `#8`, `dev/FEATURES.md`) | Renders synthetic 20-repo portfolio cleanly at desktop (`1440px`) and mobile (`375px`); zero console errors; Playwright + `axe-core` WCAG 2.2 AA pass. |
| `FEAT-11` | Per-Repository Drilldown & Trend History (`#8 [S5-01]`) | Detailed view per repository: rule evaluations with remediation steps, CI history, open advisories, ProjectV2 link, 4-Pillar 21-layer grid, and historical score trend. | `Unbuilt Spec` | Planned: `apps/web/src/pages/RepoDetailPage.tsx` (Issue `#8`) | Clicking any row opens `/repos/:slug` with full rule breakdown and 30-day score history persisted across server restarts. |
| `FEAT-12` | Hetzner Docker Runtime, Caddy TLS, Backups & Monitoring (`#9 [S7-01]`) | Multi-stage non-root Docker build, `compose.hetzner.yml`, Caddy reverse proxy with HTTPS, automated SQLite `.backup` cron + restore verification script, `/metrics` & healthchecks. | `Unbuilt Spec` | Planned: `Dockerfile`, `ops/hetzner/compose.hetzner.yml`, `ops/hetzner/Caddyfile`, `ops/hetzner/backup.sh` (Issue `#9`, `DEPLOYMENT_TARGET.md`) | `docker compose up` passes healthcheck cleanly; backup + restore script restores DB into temporary container with checksum match verified. |
| `FEAT-13` | Unit, Integration, Playwright E2E & WCAG 2.2 AA Suite (`#10 [S8-01]`) | Automated Vitest/unit suites, API integration tests against mocked GitHub HTTP server, Playwright E2E flows, and `axe-core` accessibility verification in CI. | `Unbuilt Spec` | Planned: `apps/server/tests/*`, `apps/web/e2e/*`, `.github/workflows/ci.yml` (Issue `#10`, `dev/TEST-RESULTS.md`) | CI runs green on PRs using 100% synthetic data; zero `axe` critical/serious violations; `>= 80%` statement coverage on scoring and ingestion core. |
| `FEAT-14` | Zero-Wait SWR/SSE Push, Sub-10ms DB, HTTP/3 & Latency Gates (`#11 [SPEED-01]`) | Gate 3 optimization layer: SSE live sync push (`/api/v1/events/stream`), SWR stale-while-revalidate client caching, SQLite covering-index benchmark (`p95 <= 10ms`), Caddy HTTP/3 QUIC, CI latency regression gate. | `Unbuilt Spec` (Deferred to Gate 3) | Planned: `apps/server/src/events/sse.ts`, `apps/server/tests/perf.bench.ts` (Issue `#11`) | Deferred until `FEAT-01`-`FEAT-13` are verified live; once active, `p95` SQLite dashboard read query stays under `10ms` over `100` repos x `180` daily snapshots (`18,000` snapshot rows). |
| `FEAT-15` | Public-Repo Governance, Policies & Issue/PR Templates | Established `Apache-2.0` license, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `DEPLOYMENT_TARGET.md`, `PROJECT_DIRECTION.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`, `.github/*`. | `Built & Verified` (Doc hygiene follow-ups open) | `LICENSE`, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `DEPLOYMENT_TARGET.md`, `PROJECT_DIRECTION.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`, `.github/*` | Verified present at `559853d`; follow-up `DIR-00` cleans conduct contact alias, adds issue labels `#5`-`#11`, and enables `main` branch protection. |

### 4.3 Safety, Fail-Closed Controls, Governance & Autonomy Gates

1. **Fail-Closed Startup Guard:** If `AAA_ENV=production` and any security prerequisite (`AAA_SESSION_SECRET` entropy, operator credential hash, non-root runtime check) fails, the server logs a structured error and exits immediately (`exit 1`) rather than booting degraded or unauthenticated.
2. **Public-Data Isolation Enforcement:**
   - Git repository `.gitignore` permanently ignores `.env*`, `*.db`, `*.sqlite*`, `runtime/`, `targets.yaml`, `targets.json`, and `snapshots/`.
   - Automated CI pre-commit/PR check runs `gitleaks` plus a regex sanitization guard confirming no real IPv4/private host strings, personal email literals, or forbidden token prefixes appear in tracked source/test files.
3. **Ingestion Emergency Kill-Switch & Rate-Limit Circuit Breaker:**
   - Environment flag `AAA_INGESTION_PAUSED=true` (or operator UI toggle `"Pause Background Sync"`) halts all GitHub polling immediately while keeping cached dashboard reads online.
   - Circuit breaker automatically opens for `60` minutes if GitHub API `X-RateLimit-Remaining <= 150` or secondary rate-limit `403`/`429` occurs twice consecutively, preventing IP/token throttling.
4. **Outbound Network Allowlist:** Collector HTTP client rejects redirects or base URLs pointing outside `https://api.github.com` (unless an explicit operator-configured GitHub Enterprise host is set in runtime env), eliminating SSRF risk from malformed target entries.
5. **Read-Only Non-Mutation Guarantee:** No API endpoint, background job, CLI flag, or MCP tool in `AAA` implements `git push`, `POST /repos/.../pulls`, `PATCH /repos/...`, or any write operation to external GitHub repositories.
6. **Staleness Transparency Guard:** If any repository's last successful ingestion exceeds `2x` the configured sync interval (e.g., more than `2` hours old), the UI displays an unmistakable warning badge (`STALE DATA — Last synced Xh ago`) so stale green compliance scores never mislead operators.

---

## 5. Technical Architecture & Coding-Agent Implementation Blueprint

### 5.1 System Architecture, Stack & Deployment Topology

Per the `2026-11-23` dossier (`0 LOC`), the runtime implementation stack has not yet been committed to git. **Ratifying the implementation stack via ADR-0001 is the first task of `#5 [S0-01]` (`DIR-01`).** To give coding agents an unambiguous, zero-guesswork target while respecting Hetzner cost-frugality (`<= 256 MB` RAM), SQLite WAL persistence (`#7`), Playwright E2E compatibility (`#10`), external-developer ergonomics, and Gate 3 Zero-Wait readiness (`#11`), the **Recommended Primary Baseline Stack** is a **Unified TypeScript Monorepo**:

- **Runtime & Backend API:** `Node.js 22 LTS` + `Fastify 5` (typed REST + native SSE streaming, ultra-low memory overhead, built-in schema validation) + `Zod` (shared contract validation between server, ingestion worker, and frontend).
- **Database Engine:** Embedded `SQLite 3` via `better-sqlite3` (synchronous C-level bindings ideal for sub-10ms WAL queries without external DB container overhead) + versioned `.sql` migration runner.
- **GitHub & Ingestion Clients:** Native `fetch` / `@octokit/rest` (REST with `ETag` store) + `@octokit/graphql` (batched ProjectV2 queries) running on a lightweight in-process `setInterval` / `node-cron` worker queue with bounded concurrency (zero Redis/RabbitMQ dependency).
- **Frontend UI:** `React 19` + `TypeScript` + `Vite` SPA (served directly as static immutable assets by `Fastify` behind `Caddy`, or cleanly decoupled from Vercel/Next.js serverless lock-in) + lightweight semantic CSS / Tailwind CSS + `lucide-react` icons.
- **Reverse Proxy & Hetzner Edge:** `Caddy 2` inside Docker Compose on Hetzner EU (automatic Let's Encrypt TLS, HTTP/3 QUIC out-of-the-box for `#11 [SPEED-01]`, strict security headers).

```text
+-----------------------------------------------------------------------------+
|                    HETZNER EU VPS (Authenticated Operator)                  |
|                                                                             |
|  +-------------------+        HTTPS / HTTP3         +--------------------+  |
|  |  Operator Browser | <--------------------------> |   Caddy 2 Proxy    |  |
|  |  (React + Vite)   |     CSP, HSTS, Auth Cookie   | (TLS + Security    |  |
|  +-------------------+                              |  Headers + RateLim)|  |
|                                                     +---------+----------+  |
|                                                               | 127.0.0.1   |
|  +------------------------------------------------------------v----------+  |
|  |                AAA Container (Node.js 22 + Fastify 5)                 |  |
|  |                                                                       |  |
|  |  +-------------------+   +-------------------+   +-----------------+  |  |
|  |  | Auth & CSRF Layer |   | REST + SSE API    |   | Snapshot Import |  |  |
|  |  | (Argon2id/Cookie) |   | (/api/v1/*)       |   | (4-Pillar JSON) |  |  |
|  |  +-------------------+   +---------+---------+   +--------+--------+  |  |
|  |                                    |                      |           |  |
|  |  +---------------------------------v----------------------v--------+  |  |
|  |  |              Standards Rule Engine & Scorer (Zod)               |  |  |
|  |  +---------------------------------^-------------------------------+  |  |
|  |                                    |                                  |  |
|  |  +---------------------------------+-------------------------------+  |  |
|  |  |   GitHub Collector Worker (REST w/ ETag + GraphQL ProjectV2)    |  |  |
|  |  +--------+------------------------+-------------------------------+  |  |
|  +-----------|------------------------|----------------------------------+  |
|              |                        |                                     |
|  +-----------v-----------+  +---------v-------------------------------+     |
|  |  Runtime Volume /data |  |  External GitHub API (api.github.com)   |     |
|  |  - aaa.sqlite (WAL)   |  |  (Read-Only App Token / Fine PAT;       |     |
|  |  - targets.yaml       |  |   Mocked in Synthetic Dev & CI Mode)    |     |
|  |  - encrypted backups  |  +-----------------------------------------+     |
|  +-----------------------+                                                  |
+-----------------------------------------------------------------------------+
```

*Alternative Note:* If the maintainer prefers a `Go` backend (`chi` + `modernc.org/sqlite`), `#5 [S0-01]` ADR-0001 must explicitly swap `apps/server/` from Node/Fastify to Go while preserving the **exact same** SQLite schema (`Section 5.3`), HTTP/SSE contracts (`Section 5.4`), and React/Playwright frontend (`apps/web/`).

### 5.2 Repository Structure & Module Map

Current tracked repository (`13` files as of `2026-11-23`) vs target implementation structure:

```text
AAA-Software-Development-standards-dashboard/
|-- .github/
|   |-- ISSUE_TEMPLATE/
|   |   |-- bug_report.yml              # [EXISTING] Bug report template
|   |   `-- feature_request.yml         # [EXISTING] Feature request template
|   |-- dependabot.yml                  # [EXISTING] Dependency update config
|   |-- pull_request_template.md        # [EXISTING] PR checklist (secrets/docs/tests)
|   `-- workflows/
|       |-- ci.yml                      # [PLANNED DIR-01] P1/P2/P3/P4 verification CI
|       `-- container-publish.yml       # [PLANNED DIR-06] Tagged GHCR image + Trivy scan
|-- dev/
|   |-- FEATURES.md                     # [EXISTING] Feature delivery tracker
|   `-- TEST-RESULTS.md                 # [EXISTING] Test & CI evidence log
|-- docs/
|   |-- MASTER_PLAN.md                  # [PLANNED TARGET] Canonical Master Spec (this doc)
|   |-- HETZNER_DEPLOY.md               # [PLANNED DIR-06] Cutover, backup & rollback guide
|   `-- adr/
|       `-- 0001-runtime-stack.md       # [PLANNED DIR-01] Ratified stack & SQLite ADR
|-- packages/
|   `-- schema/                         # [PLANNED DIR-01] Shared Zod contracts & rule catalog
|       |-- package.json
|       |-- rules/default-rules.yaml      # Generic declarative engineering standards rules
|       `-- src/
|           |-- index.ts
|           |-- standards.ts              # Rule, Evaluation, Score schemas
|           |-- snapshot.ts               # PortfolioSnapshotImportV1 (4-Pillar + worktree)
|           `-- fixtures/synthetic.ts     # 100% synthetic demo repos for dev & E2E
|-- apps/
|   |-- server/                         # [PLANNED DIR-01..04] Fastify API + SQLite + Collector
|   |   |-- package.json
|   |   |-- src/
|   |   |   |-- index.ts                # Entrypoint & fail-closed env bootstrap
|   |   |   |-- app.ts                  # Fastify builder + security headers + static UI
|   |   |   |-- config/env.ts           # Strict Zod env parser (prod vs synthetic mode)
|   |   |   |-- config/targets.ts       # Runtime targets.yaml loader (outside git)
|   |   |   |-- db/
|   |   |   |   |-- client.ts           # SQLite WAL connection + pragmas
|   |   |   |   |-- migrate.ts          # Transactional SQL migration runner
|   |   |   |   `-- migrations/0001_init.sql
|   |   |   |-- auth/
|   |   |   |   |-- session.ts          # Argon2id verify, HttpOnly cookies, CSRF
|   |   |   |   `-- middleware.ts       # Auth + rate-limit guards
|   |   |   |-- github/
|   |   |   |   |-- client.ts           # ETag cache + rate-limit circuit breaker
|   |   |   |   |-- collectors/         # docs.ts, ci.ts, security.ts, deployment.ts, projectv2.ts
|   |   |   |   `-- sync-runner.ts      # Bounded batch ingestion orchestrator
|   |   |   |-- engine/
|   |   |   |   `-- evaluator.ts        # Deterministic weighted standards scoring
|   |   |   |-- imports/
|   |   |   |   `-- snapshot.ts         # External JSON & 4-Pillar audit ingestion
|   |   |   |-- events/
|   |   |   |   `-- sse.ts              # [GATE 3 DIR-08] Live SSE event bus
|   |   |   `-- routes/                 # health, auth, dashboard, repos, sync, imports, standards
|   |   `-- tests/                      # Vitest unit, DB migration & mock-GitHub integration tests
|   `-- web/                            # [PLANNED DIR-05] React + Vite + TypeScript UI
|       |-- package.json
|       |-- src/
|       |   |-- App.tsx
|       |   |-- api/client.ts           # Typed fetch wrapper + CSRF + SWR cache (Gate 3)
|       |   |-- pages/                  # LoginPage, DashboardPage, RepoDetailPage, StandardsPage
|       |   `-- components/             # ComplianceBadge, PillarGrid, TrendSparkline, SyncBanner
|       `-- e2e/                        # [PLANNED DIR-07] Playwright + axe-core WCAG 2.2 AA
|-- ops/
|   `-- hetzner/                        # [PLANNED DIR-06]
|       |-- Dockerfile                  # Multi-stage non-root production image
|       |-- compose.hetzner.yml         # AAA + Caddy + backup sidecar/cron
|       |-- Caddyfile                   # TLS, HTTP/3, HSTS/CSP security headers
|       |-- backup.sh                   # SQLite online .backup + retention + verification
|       `-- targets.example.yaml        # Synthetic example target inventory template
|-- CODE_OF_CONDUCT.md                  # [EXISTING] Conduct policy (audit contact alias in DIR-00)
|-- CONTRIBUTING.md                     # [EXISTING] Contribution workflow & synthetic rule
|-- DEPLOYMENT_TARGET.md                # [EXISTING] Hetzner-only deployment mandate
|-- LICENSE                             # [EXISTING] Apache License 2.0
|-- PROJECT_DIRECTION.md                # [EXISTING] 2026-11-20 locked public direction
|-- README.md                           # [EXISTING] Direction header (expand in DIR-01)
`-- SECURITY.md                         # [EXISTING] Private vulnerability reporting policy
```

### 5.3 Data Schema, Persistence, Secrets & Backup/Erasure

#### Core SQLite DDL (`apps/server/src/db/migrations/0001_init.sql`)

Designed explicitly with covering indexes so dashboard aggregation and drilldown queries remain under `10ms` even across `100+` repositories and `180+` historical daily snapshots (`#11 [SPEED-01]` readiness):

```sql
PRAGMA journal_mode = WAL;
PRAGMA foreign_keys = ON;

CREATE TABLE IF NOT EXISTS repositories (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  slug TEXT NOT NULL UNIQUE,                 -- e.g. 'example-org/example-repo-a'
  display_name TEXT NOT NULL,
  visibility TEXT NOT NULL CHECK (visibility IN ('public', 'private', 'internal')),
  repo_category TEXT NOT NULL DEFAULT 'service', -- 'service' | 'library' | 'cli' | 'spec'
  default_branch TEXT NOT NULL DEFAULT 'main',
  expected_hosting TEXT NOT NULL DEFAULT 'hetzner', -- 'hetzner' | 'local' | 'na'
  archived INTEGER NOT NULL DEFAULT 0,
  enabled INTEGER NOT NULL DEFAULT 1,
  etag_repo TEXT,
  etag_issues TEXT,
  last_synced_at TEXT,
  last_sync_status TEXT NOT NULL DEFAULT 'pending', -- 'ok' | 'error' | 'rate_limited' | 'pending'
  last_sync_error TEXT,
  latest_score INTEGER CHECK (latest_score BETWEEN 0 AND 100),
  latest_tier TEXT CHECK (latest_tier IN ('green', 'amber', 'red', 'unknown')) DEFAULT 'unknown',
  created_at TEXT NOT NULL DEFAULT (strftime('%Y-%m-%dT%H:%M:%fZ', 'now')),
  updated_at TEXT NOT NULL DEFAULT (strftime('%Y-%m-%dT%H:%M:%fZ', 'now'))
);

CREATE TABLE IF NOT EXISTS sync_runs (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  trigger_type TEXT NOT NULL CHECK (trigger_type IN ('scheduled', 'manual', 'cli')),
  started_at TEXT NOT NULL,
  finished_at TEXT,
  status TEXT NOT NULL CHECK (status IN ('running', 'completed', 'partial', 'failed', 'paused')),
  repos_targeted INTEGER NOT NULL DEFAULT 0,
  repos_succeeded INTEGER NOT NULL DEFAULT 0,
  repos_failed INTEGER NOT NULL DEFAULT 0,
  rate_limit_remaining INTEGER,
  notes TEXT
);

CREATE TABLE IF NOT EXISTS repo_snapshots (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  repo_id INTEGER NOT NULL REFERENCES repositories(id) ON DELETE CASCADE,
  sync_run_id INTEGER REFERENCES sync_runs(id) ON DELETE SET NULL,
  captured_at TEXT NOT NULL,
  overall_score INTEGER NOT NULL CHECK (overall_score BETWEEN 0 AND 100),
  ci_score INTEGER NOT NULL CHECK (ci_score BETWEEN 0 AND 100),
  security_score INTEGER NOT NULL CHECK (security_score BETWEEN 0 AND 100),
  docs_license_score INTEGER NOT NULL CHECK (docs_license_score BETWEEN 0 AND 100),
  deployment_score INTEGER NOT NULL CHECK (deployment_score BETWEEN 0 AND 100),
  ci_pass_rate_20 REAL,                     -- 0.0 to 100.0, NULL if No CI
  open_advisories_critical INTEGER NOT NULL DEFAULT 0,
  open_advisories_high INTEGER NOT NULL DEFAULT 0,
  open_advisories_medium INTEGER NOT NULL DEFAULT 0,
  open_advisories_low INTEGER NOT NULL DEFAULT 0,
  spdx_license TEXT,
  branch_protected TEXT NOT NULL DEFAULT 'unknown', -- 'protected' | 'unprotected' | 'unknown'
  unlabeled_roadmap_issues INTEGER NOT NULL DEFAULT 0,
  has_vercel_drift INTEGER NOT NULL DEFAULT 0,
  worktree_state TEXT NOT NULL DEFAULT 'unknown'    -- 'clean' | 'dirty' | 'unknown'
);

CREATE INDEX IF NOT EXISTS idx_repo_snapshots_repo_captured
  ON repo_snapshots(repo_id, captured_at DESC);

CREATE TABLE IF NOT EXISTS rule_evaluations (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  snapshot_id INTEGER NOT NULL REFERENCES repo_snapshots(id) ON DELETE CASCADE,
  rule_id TEXT NOT NULL,                     -- e.g. 'SEC-001', 'DOC-002', 'DEP-001'
  pillar TEXT NOT NULL,                      -- 'ci' | 'security' | 'docs' | 'deployment' | 'roadmap'
  severity TEXT NOT NULL CHECK (severity IN ('critical', 'high', 'medium', 'low')),
  status TEXT NOT NULL CHECK (status IN ('pass', 'warn', 'fail', 'na', 'insufficient_scope')),
  weight INTEGER NOT NULL,
  message TEXT NOT NULL,
  remediation_hint TEXT
);

CREATE INDEX IF NOT EXISTS idx_rule_evaluations_snapshot
  ON rule_evaluations(snapshot_id, status);

CREATE TABLE IF NOT EXISTS ci_workflow_runs (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  repo_id INTEGER NOT NULL REFERENCES repositories(id) ON DELETE CASCADE,
  github_run_id INTEGER NOT NULL,
  workflow_name TEXT NOT NULL,
  head_branch TEXT NOT NULL,
  conclusion TEXT,                           -- 'success' | 'failure' | 'cancelled' | 'skipped' | null
  run_started_at TEXT NOT NULL,
  html_url TEXT NOT NULL,
  UNIQUE(repo_id, github_run_id)
);

CREATE INDEX IF NOT EXISTS idx_ci_workflow_runs_repo_started
  ON ci_workflow_runs(repo_id, run_started_at DESC);

CREATE TABLE IF NOT EXISTS security_advisories (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  repo_id INTEGER NOT NULL REFERENCES repositories(id) ON DELETE CASCADE,
  alert_number INTEGER NOT NULL,
  package_name TEXT NOT NULL,
  ecosystem TEXT NOT NULL,
  severity TEXT NOT NULL CHECK (severity IN ('critical', 'high', 'medium', 'low')),
  state TEXT NOT NULL CHECK (state IN ('open', 'fixed', 'dismissed')),
  cve_id TEXT,
  first_seen_at TEXT NOT NULL,
  html_url TEXT NOT NULL,
  UNIQUE(repo_id, alert_number)
);

CREATE INDEX IF NOT EXISTS idx_security_advisories_repo_state
  ON security_advisories(repo_id, state, severity);

CREATE TABLE IF NOT EXISTS four_pillar_audits (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  repo_id INTEGER NOT NULL REFERENCES repositories(id) ON DELETE CASCADE,
  imported_at TEXT NOT NULL,
  source_tool TEXT NOT NULL,
  confirmed_layers INTEGER NOT NULL,
  needed_layers INTEGER NOT NULL,
  p1_summary TEXT NOT NULL,
  p2_summary TEXT NOT NULL,
  p3_summary TEXT NOT NULL,
  p4_summary TEXT NOT NULL,
  cells_json TEXT NOT NULL                   -- JSON object matching 21-layer matrix keys
);

CREATE INDEX IF NOT EXISTS idx_four_pillar_repo_imported
  ON four_pillar_audits(repo_id, imported_at DESC);

CREATE TABLE IF NOT EXISTS project_v2_items (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  repo_id INTEGER NOT NULL REFERENCES repositories(id) ON DELETE CASCADE,
  project_title TEXT NOT NULL,
  item_id TEXT NOT NULL,
  item_title TEXT NOT NULL,
  status_field TEXT,
  priority_field TEXT,
  updated_at TEXT NOT NULL,
  UNIQUE(repo_id, item_id)
);

CREATE TABLE IF NOT EXISTS operator_sessions (
  id TEXT PRIMARY KEY,                       -- SHA-256 hash of random 32-byte session token
  operator_id TEXT NOT NULL,
  csrf_token TEXT NOT NULL,
  expires_at TEXT NOT NULL,
  created_at TEXT NOT NULL DEFAULT (strftime('%Y-%m-%dT%H:%M:%fZ', 'now'))
);

CREATE INDEX IF NOT EXISTS idx_operator_sessions_expires
  ON operator_sessions(expires_at);

CREATE TABLE IF NOT EXISTS audit_events (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  actor TEXT NOT NULL,                       -- 'operator' | 'scheduler' | 'snapshot-token'
  action TEXT NOT NULL,                      -- 'login_success' | 'login_failed' | 'manual_sync' | 'snapshot_import'
  target_slug TEXT,
  outcome TEXT NOT NULL,
  occurred_at TEXT NOT NULL DEFAULT (strftime('%Y-%m-%dT%H:%M:%fZ', 'now'))
);
```

#### Declarative Standards Rules Baseline (`packages/schema/rules/default-rules.yaml` Contract)

Every rule carries an immutable `rule_id`, applicable `repo_category` filter (so pure spec or library repos are not penalized for missing Dockerfiles), severity, weight, and deterministic evaluation logic:

- `CI-001` (`ci`, `high`, weight `15`): Default branch has at least one active GitHub Actions workflow (`fail` if `No CI` on non-spec repos).
- `CI-002` (`ci`, `high`, weight `15`): Rolling last-`20` default-branch CI pass rate `>= 90%` (`warn` at `70-89%`, `fail` below `70%`).
- `SEC-001` (`security`, `critical`, weight `20`): Zero open `critical` Dependabot advisories (`fail` if `>= 1`).
- `SEC-002` (`security`, `high`, weight `10`): Zero open `high` Dependabot advisories (`warn` at `1-2`, `fail` `>= 3`).
- `SEC-003` (`security`, `medium`, weight `5`): `SECURITY.md` present on default branch and `branch_protection` enabled (`warn` if unprotected).
- `DOC-001` (`docs`, `high`, weight `10`): Valid SPDX `LICENSE` file present (`Apache-2.0` or approved OSI license).
- `DOC-002` (`docs`, `medium`, weight `10`): Non-stub `README.md` (`>= 500` bytes), `CONTRIBUTING.md`, and `docs/MASTER_PLAN.md` present.
- `DOC-003` (`docs`, `low`, weight `5`): `dev/FEATURES.md` and `dev/TEST-RESULTS.md` present with non-empty verification evidence.
- `DEP-001` (`deployment`, `high`, weight `10`, applies to `service` repos): `DEPLOYMENT_TARGET.md` present and strictly specifies Hetzner / approved local tooling; **zero** `vercel.json` or `.vercel/` directories (`critical fail` if Vercel drift detected).
- `RDM-001` (`roadmap`, `low`, weight `5`): Structured milestone/stage issues (`[S*-01]`) carry non-empty GitHub labels (`warn` if `unlabeled_roadmap_issues >= 1`).

#### Secrets, Backup & Data Retention Policy

- **Secrets Isolation:** `GITHUB_TOKEN` (or GitHub App `APP_ID` + `PRIVATE_KEY_PEM`), `AAA_SESSION_SECRET`, `AAA_OPERATOR_PASSWORD_HASH`, and `AAA_SNAPSHOT_IMPORT_TOKEN_HASH` live exclusively in `/run/secrets/` or `0600` runtime `.env` on Hetzner. They are **never** persisted inside `aaa.sqlite`.
- **Automated Backup & Restore:** `ops/hetzner/backup.sh` runs nightly via systemd timer or container cron, invoking `sqlite3 /data/aaa.sqlite ".backup '/backups/aaa-$(date -u +%F).sqlite'"`, compressing with `zstd`, encrypting via `age` or `restic` to off-box storage, pruning local backups older than `14` days (remote older than `30` days), and verifying integrity via `PRAGMA integrity_check;`.
- **Retention & Erasure:** Raw `sync_runs` and `audit_events` older than `180` days are automatically vacuumed; expired `operator_sessions` are purged hourly. Deleting a repository from runtime `targets.yaml` and executing `DELETE /api/v1/repos/:slug` cascades across all snapshots, advisories, and evaluations cleanly.

### 5.4 API, MCP, IPC, CLI & External Connector Contracts

#### HTTP REST & SSE API Contract (`apps/server`)

All endpoints under `/api/v1/*` (except `/api/v1/auth/login`) require a valid authenticated session cookie (plus `X-CSRF-Token` header on state mutations) or, exclusively for `/api/v1/imports/snapshot`, a scoped `Authorization: Bearer {AAA_SNAPSHOT_IMPORT_TOKEN}` header.

| Method & Path | Purpose | Request / Query Contract | Response Shape / Status Codes |
| --- | --- | --- | --- |
| `GET /api/healthz` | Unauthenticated liveness probe for Caddy/Docker | None | `200 {"status":"ok","db":"ok"}` (zero sensitive details) |
| `POST /api/v1/auth/login` | Authenticate operator | `{"username":"operator","password":"..."}` | `200 {"operator":"...","csrfToken":"..."}` + `Set-Cookie`; `401` invalid; `429` rate-limited |
| `POST /api/v1/auth/logout` | Destroy current session | `X-CSRF-Token` | `204 No Content` |
| `GET /api/v1/auth/me` | Verify active operator session | Session cookie | `200 {"authenticated":true,"operator":"...","csrfToken":"..."}` |
| `GET /api/v1/dashboard/summary` | KPI strip, score histogram, sync freshness banner | `?category=&tier=` | `200 {"totalRepos":N,"avgScore":N,"criticalAlerts":N,"failingCi":N,"vercelDrift":N,"staleRepos":N,"lastSyncRun":{...}}` |
| `GET /api/v1/repos` | Filterable portfolio matrix table | `?tier=red\|amber\|green&category=&q=&sort=score\|advisories\|name` | `200 {"items":[RepoSummary],"total":N}` |
| `GET /api/v1/repos/:owner/:name` | Full per-repo drilldown, rule evals, CI, CVEs, 4-pillar grid | `?days=30` | `200 {"repo":{...},"latestSnapshot":{...},"evaluations":[...],"ciRuns":[...],"advisories":[...],"projectItems":[...],"fourPillar":{...},"history":[...]}` |
| `POST /api/v1/sync/run` | Trigger manual portfolio ingestion sweep | `{"repoSlugs":["optional-subset"]}` + `X-CSRF-Token` | `202 {"syncRunId":123,"status":"running"}`; `409` if already running; `423` if `INGESTION_PAUSED` |
| `POST /api/v1/imports/snapshot` | External 4-pillar & local worktree JSON snapshot import | `PortfolioSnapshotImportV1` JSON payload | `200 {"imported":N,"updatedSlugs":[...]}`; `400` Zod schema error; `401/403` auth failure |
| `GET /api/v1/standards/rules` | Inspect active declarative rule catalog | None | `200 {"schemaVersion":"1.0","rules":[...]}` |
| `GET /api/v1/events/stream` | **[Gate 3 `#11`]** Real-time SSE progress & score updates | `Accept: text/event-stream` | Events: `sync_started`, `repo_updated`, `sync_completed`, `heartbeat` (`30s`) |

#### External JSON Import Schema (`PortfolioSnapshotImportV1`)

Reconciles `00_live_exec_summary_2026-11-20.md` Risk #2 cleanly so external CLI/audit pipelines feed local-worktree and 21-layer verification matrices into `AAA` without duplicating scanners:

```json
{
  "schema_version": "1.0",
  "source_tool": "portfolio-audit-cli",
  "generated_at": "2026-11-23T17:30:00Z",
  "repositories": [
    {
      "slug": "example-org/example-repo-a",
      "worktree_state": "clean",
      "four_pillar": {
        "needed_layers": 21,
        "confirmed_layers": 18,
        "p1_summary": "6/6 Confirmed",
        "p2_summary": "3/3 Confirmed",
        "p3_summary": "4/5 Confirmed",
        "p4_summary": "5/7 Confirmed",
        "cells": {
          "p1_repo": "Yes — Confirmed",
          "p4_secrets": "Yes — gitleaks CI green"
        }
      }
    }
  ]
}
```

#### CLI & Optional Read-Only MCP Interface

- **CLI (`aaa-cli`):** `npm run sync:once` (single deterministic headless sync for cron/CI testing), `npm run seed:synthetic` (populate synthetic demo portfolio), `npm run import:snapshot -- --file ./sample.json` (validate & import JSON snapshot).
- **Optional Read-Only MCP Server (Future Extension):** If exposed for local developer agents behind an authenticated operator token, exposes strictly read-only tools: `get_portfolio_summary()`, `get_repo_compliance(slug)`, and `list_failing_rules(severity)`. Zero mutating tools.

### 5.5 Hosting Target, CI/CD, Packaging & 4-Pillar Verification Standards

- **Production Hetzner EU Packaging (`ops/hetzner/`):**
  - Multi-stage `Dockerfile`: Stage 1 compiles TypeScript packages and Vite bundle (`node:22-alpine`), Stage 2 runs minimal production runtime under non-root `node` UID `10001` with `NODE_ENV=production`, no devDependencies, `HEALTHCHECK` hitting `127.0.0.1:8080/api/healthz`.
  - `compose.hetzner.yml`: Binds app container internally to a private Docker bridge network; only `Caddy 2` exposes ports `80/443` (TCP + UDP for HTTP/3 QUIC). Mounts named persistent volume `/data` (`aaa.sqlite` + read-only mounted `targets.yaml`).
  - `Caddyfile`: Enforces automatic TLS, HTTP/3, HSTS (`max-age=31536000`), strict CSP (`default-src 'self'; frame-ancestors 'none'`), `X-Content-Type-Options: nosniff`, and gzip/zstd compression.
- **CI/CD & 4-Pillar Alignment (`.github/workflows/ci.yml`):**
  - **Pillar 1 (Code Quality & Hygiene):** `eslint`, `tsc --noEmit`, `prettier --check`, `knip` (dead code check), SQL migration dry-run on temp SQLite DB, doc-link validation on `README.md` / `docs/MASTER_PLAN.md` / `dev/*`.
  - **Pillar 2 (Performance & Load):** Vite bundle size budget check (`<= 250 KB` initial JS gzipped); Gate 3 (`#11`) adds Vitest SQLite benchmark verifying `p95 <= 10ms` across `18,000` seeded snapshot rows and Playwright Cold-Load / LCP check.
  - **Pillar 3 (Resource & Observability):** Docker build verification, `/api/healthz` and Prometheus `/metrics` endpoint smoke test, container memory limit test (`<= 256 MB` under synthetic 50-repo load).
  - **Pillar 4 (Security, Safety & Licenses):** `gitleaks` secret scan, custom public-repo sanitization check (ensuring zero personal emails, raw private IPs, or sensitive patterns in committed code/fixtures), `npm audit --audit-level=high` / OSV-Scanner, Trivy container scan, Playwright `axe-core` WCAG 2.2 AA audit, and Apache-2.0 dependency license compatibility verification (`license-checker`).

---

## 6. Build Reality (2026-11-23), Gap Analysis & Coding-Agent Task Backlog

### 6.1 Honest Build Reality Inventory (`2026-11-23`)

- **Built & Verified (`13` files, `0` LOC):**
  - Governance & Legal: `LICENSE` (verified `Apache-2.0`), `SECURITY.md` (`#1`, `8fb2e0f`), `CONTRIBUTING.md` (`#2`, `35d2371`), `CODE_OF_CONDUCT.md`.
  - Operational Direction & Deployment Policy: `DEPLOYMENT_TARGET.md` (`ca41c87`, PR `#3` `084a164` removing Vercel), `PROJECT_DIRECTION.md` (`3762c49`), `README.md` (`3762c49`, 12-line direction header).
  - Issue/PR Scaffolding & Evidence Logs: `.github/ISSUE_TEMPLATE/bug_report.yml`, `.github/ISSUE_TEMPLATE/feature_request.yml`, `.github/dependabot.yml`, `.github/pull_request_template.md`, `dev/FEATURES.md` (`559853d`), `dev/TEST-RESULTS.md` (`559853d`).
- **Built Local / Unverified Live:** `None` (`0` LOC).
- **Partial / Mocked:** `None` (`0/6` checklist capabilities in `dev/FEATURES.md` implemented).
- **Missing (`100%` of Software Implementation & CI):**
  - Application manifest (`package.json`), lockfile, TypeScript configs, and stack ADR (`docs/adr/0001-runtime-stack.md`).
  - Database schema, migration runner, and SQLite persistence (`0/1` tables).
  - Operator authentication, CSRF/session store, security headers, and least-privilege GitHub token handler.
  - GitHub REST/GraphQL/ProjectV2 collectors, Standards Evaluator engine, and Snapshot Import API.
  - Dashboard web UI, per-repo drilldown, and WCAG 2.2 AA components.
  - Hetzner Docker/Caddy packaging, backup/restore automation, and cutover runbook.
  - CI workflows (`.github/workflows/ci.yml`), automated tests, and 4-Pillar checks (`0/21` confirmed; `No CI`).
- **Immediate Repository Hygiene & Governance Gaps:**
  - `branch_protection` on `main` is currently `Unprotected`.
  - All `7` open GitHub issues (`#5`-`#11`) have empty `labels: []`, causing automated stage parsers to report `roadmap_s_open: null`.
  - `CODE_OF_CONDUCT.md` line 19 contains a personal maintainer email address that should be reviewed/replaced with a role-based conduct alias or GitHub private disclosure path to keep the public repo fully sanitized.
  - External dossier prose (`what_is_built`) contains stale wording (`"MIT license"`, `"single-line README stub"`); canonical git truth is `Apache-2.0` (`LICENSE`) and the `12`-line `2026-11-20` `README.md`.

### 6.2 Coding-Agent Implementation Directives

Execute the following directives strictly in priority order. Never proceed to `DIR-08` until `DIR-00` through `DIR-07` pass verification. Every test fixture and screenshot MUST use 100% synthetic repository names (`example-org/example-repo-a`, `example-org/portfolio-service-1`, etc.).

#### `DIR-00`: Immediate Repository Governance & Sanitization Hygiene (Pre-Code Gate)
- **Target:** Repository settings + `CODE_OF_CONDUCT.md` + GitHub issues `#5`-`#11` + `docs/MASTER_PLAN.md`.
- **Implementation:**
  1. Copy this specification into `docs/MASTER_PLAN.md` in the repository after verifying zero sensitive strings exist.
  2. Replace any personal email reference in `CODE_OF_CONDUCT.md` with a dedicated non-personal conduct contact alias or link to GitHub private reporting instructions.
  3. Apply structured stage labels (`stage:S0-01`, `stage:S1-01`, `stage:S3-01`, `stage:S5-01`, `stage:S7-01`, `stage:S8-01`, `perf:SPEED-01`) to open issues `#5`-`#11`.
  4. Enable GitHub branch protection on `main` requiring pull requests and green status checks once `DIR-01` lands CI.
- **Verification:** Confirm `gh issue list --json number,labels` shows non-empty labels on `#5`-`#11` and `rg` check confirms zero personal email/private repo patterns across tracked files.

#### `DIR-01`: Product Spec Ratification, Standards Schema & CI Baseline (`#5 [S0-01]`)
- **Target Files:** `docs/adr/0001-runtime-stack.md`, `README.md`, `package.json`, `packages/schema/*`, `.github/workflows/ci.yml`, `.gitignore`.
- **Implementation:**
  1. Author `docs/adr/0001-runtime-stack.md` ratifying `Node.js 22 LTS + Fastify 5 + SQLite WAL + React 19 + Vite + Zod`.
  2. Expand `README.md` with system overview, architecture diagram, synthetic local quickstart, security boundary warning, and link to `docs/MASTER_PLAN.md`.
  3. Initialize npm workspaces (`packages/schema`, `apps/server`, `apps/web`), strict `tsconfig.base.json`, ESLint, Prettier, `knip`, and `.gitignore` (blocking `.env*`, `*.sqlite*`, `targets.*`, `runtime/`).
  4. Implement `packages/schema/src/standards.ts`, `snapshot.ts`, `rules/default-rules.yaml`, and deterministic synthetic fixtures (`fixtures/synthetic.ts`).
  5. Wire `.github/workflows/ci.yml` executing `eslint`, `tsc --noEmit`, `prettier --check`, `vitest`, `gitleaks`, and public-repo sanitization regex checks.
- **Verification:** `npm ci && npm run lint && npm run typecheck && npm test` exits `0` cleanly in GitHub Actions.

#### `DIR-02`: Authentication, Fail-Closed Guards, Security Headers & Secret Isolation (`#6 [S1-01]`)
- **Target Files:** `apps/server/src/config/env.ts`, `apps/server/src/auth/*`, `apps/server/src/plugins/security.ts`, `apps/server/src/db/migrations/0001_init.sql`.
- **Implementation:**
  1. Implement strict `env.ts` Zod validator enforcing fail-closed startup in `production` when `AAA_SESSION_SECRET` or `AAA_OPERATOR_PASSWORD_HASH` is absent.
  2. Implement SQLite WAL client (`better-sqlite3`), migration runner, and full `0001_init.sql` schema.
  3. Build Argon2id/scrypt login handler (`POST /api/v1/auth/login`), IP rate limiting, `HttpOnly`/`Secure`/`SameSite=Strict` cookie sessions, CSRF validation middleware, and strict Fastify security headers.
  4. Implement runtime `targets.yaml` loader and log/JSON redactor stripping bearer tokens or secrets before serialization.
- **Verification:** Vitest integration tests confirm: (a) prod boot throws on missing secret, (b) unauthenticated `/api/v1/dashboard/summary` returns `401`, (c) CSRF-missing `POST` returns `403`, (d) login lockout activates after `5` bad attempts, and (e) CSP/HSTS/XFO headers exist on responses.

#### `DIR-03`: GitHub REST/GraphQL, CI, Advisory, Deployment Drift & ProjectV2 Ingestion (`#7 [S3-01]`)
- **Target Files:** `apps/server/src/github/*`, `apps/server/src/engine/evaluator.ts`, `apps/server/src/routes/sync.ts`.
- **Implementation:**
  1. Build GitHub HTTP client supporting `ETag` caching, `X-RateLimit-Remaining <= 150` circuit breaker, outbound host allowlist (`api.github.com`), and read-only scope check.
  2. Implement all `5` collectors (`docs.ts`, `ci.ts`, `security.ts`, `deployment.ts`, `projectv2.ts`) with graceful `403` `insufficient_scope` fallback.
  3. Wire deterministic `evaluator.ts` scoring repositories against `default-rules.yaml` and writing atomic snapshots into `repo_snapshots` and `rule_evaluations`.
  4. Implement `sync-runner.ts` with isolated per-repo error capture and scheduled + manual `POST /api/v1/sync/run` endpoints.
- **Verification:** Integration suite running against a local mock GitHub HTTP/GraphQL server validates `304 Not Modified` caching, rate-limit circuit-breaker activation, `vercel.json` drift detection, unlabeled `[S*-01]` issue detection, and `100%` deterministic compliance scores.

#### `DIR-04`: External Portfolio Snapshot & 4-Pillar Audit JSON Importer
- **Target Files:** `apps/server/src/imports/snapshot.ts`, `apps/server/src/routes/imports.ts`.
- **Implementation:**
  1. Implement `POST /api/v1/imports/snapshot` authenticated via `AAA_SNAPSHOT_IMPORT_TOKEN_HASH` (timing-safe comparison) or operator session + CSRF.
  2. Validate `PortfolioSnapshotImportV1` payloads via Zod, upsert `four_pillar_audits` and `worktree_state`, and preserve independent timestamps from GitHub API syncs.
  3. Add CLI entrypoint `npm run import:snapshot -- --file {path}` for local/CI batch imports.
- **Verification:** Integration test confirms valid synthetic 21-layer payload persists and reflects in `/api/v1/repos/:owner/:name`, while invalid schemas return `400` and invalid bearer tokens return `401`.

#### `DIR-05`: Standards Compliance Dashboard UI & Per-Repo Drilldown (`#8 [S5-01]`)
- **Target Files:** `apps/web/src/*`, `apps/server/src/routes/dashboard.ts`, `apps/server/src/routes/repos.ts`.
- **Implementation:**
  1. Implement `/api/v1/dashboard/summary`, `/api/v1/repos`, `/api/v1/repos/:owner/:name`, and `/api/v1/standards/rules` endpoints.
  2. Build responsive, keyboard-accessible React UI: Login view, Portfolio KPI strip, Stale-Sync alert banner, filterable/sortable Compliance Matrix table, and Repository Drilldown page showing rule checklist + remediation hints, CI runs, Dependabot advisories, 4-Pillar 21-layer grid, and historical trend chart.
  3. Serve production Vite static build cleanly from Fastify in production mode.
- **Verification:** `vite build` succeeds cleanly with zero TypeScript errors and zero unused exports (`knip`).

#### `DIR-06`: Hetzner Production Container, Caddy TLS, Backups & Monitoring (`#9 [S7-01]`)
- **Target Files:** `ops/hetzner/Dockerfile`, `ops/hetzner/compose.hetzner.yml`, `ops/hetzner/Caddyfile`, `ops/hetzner/backup.sh`, `ops/hetzner/targets.example.yaml`, `docs/HETZNER_DEPLOY.md`.
- **Implementation:**
  1. Author multi-stage non-root `Dockerfile` (`USER 10001`), `compose.hetzner.yml`, and `Caddyfile` with TLS + security headers.
  2. Implement `ops/hetzner/backup.sh` using SQLite online `.backup`, `PRAGMA integrity_check`, and off-box encrypted upload hook + verified restore test script.
  3. Expose sanitized Prometheus `/metrics` (protected behind internal docker network or auth token: sync duration, repo counts by tier, rate-limit remaining, HTTP latency histograms).
  4. Write complete `docs/HETZNER_DEPLOY.md` covering architecture, DNS/TLS, secret injection, migration safety, backup restore drills, and rollback procedure per `DEPLOYMENT_TARGET.md`.
- **Verification:** `docker build` + Trivy image scan passes zero critical OS CVEs; `docker compose -f ops/hetzner/compose.hetzner.yml up -d` passes `/api/healthz`; backup/restore smoke test restores synthetic DB cleanly; `dev/TEST-RESULTS.md` updated with command logs.

#### `DIR-07`: Playwright E2E & WCAG 2.2 AA Accessibility Verification (`#10 [S8-01]`)
- **Target Files:** `apps/web/e2e/*.spec.ts`, `.github/workflows/ci.yml`.
- **Implementation:**
  1. Write Playwright E2E suite booting the app in `AAA_ENV=synthetic` mode against seeded synthetic repositories: login flow, dashboard filtering/sorting, manual sync trigger against mock GitHub server, per-repo drilldown, and logout.
  2. Integrate `@axe-core/playwright` across every page (`login`, `dashboard`, `repo detail`, `standards`) asserting zero WCAG 2.2 AA critical/serious violations at desktop (`1440x900`) and mobile (`375x812`).
- **Verification:** `npx playwright test` passes 100% in CI; update `dev/FEATURES.md` checkboxes and `dev/TEST-RESULTS.md` with exact revision and workflow evidence.

#### `DIR-08`: Gate 3 Optimization — Zero-Wait SWR, SSE Live Push, Sub-10ms Queries & HTTP/3 (`#11 [SPEED-01]`)
- **Target Files:** `apps/server/src/events/sse.ts`, `apps/server/tests/perf.bench.ts`, `apps/web/src/api/client.ts`, `ops/hetzner/Caddyfile`, `.github/workflows/ci.yml`.
- **Implementation (ONLY after `DIR-01`-`DIR-07` pass):**
  1. Implement authenticated `GET /api/v1/events/stream` SSE emitter broadcasting incremental `repo_updated` and `sync_completed` events.
  2. Add client-side stale-while-revalidate caching + SSE reconnection hook in `apps/web`.
  3. Benchmark SQLite read queries against a `100`-repo x `180`-day synthetic dataset (`18,000` snapshots), adding any missing covering indexes so `p95 <= 10ms`.
  4. Verify `Caddyfile` HTTP/3 (`443/udp`) listener and add CI latency regression check (`perf.bench.ts`).
- **Verification:** `npm run bench:db` reports `p95 <= 10ms`; Playwright verifies SSE updates UI live without page reload when sync fires.

---

## 7. Risk Register, Constraints & Portfolio Cross-References

### 7.1 Risk Register

| Category | Risk & Observed Evidence | Severity | Mitigation & Hard Gate |
| --- | --- | --- | --- |
| **Execution / Scope** | **Premature Optimization Trap:** Issue `#11 [SPEED-01]` specifies SWR, SSE, sub-`10ms` DB queries, HTTP/3, and CI latency gates before `#5 [S0-01]`'s core schema or any code (`0 LOC`) exists. | `High` | **Hard Gate:** Sequenced strictly into Gate 3 (`DIR-08`), after `DIR-01`-`DIR-07` establish working schema, auth, ingestion, UI, Hetzner deployment, and tests. |
| **Security / Privacy** | **Public-Repo Leakage:** `AAA` is a public `Apache-2.0` repo with external developer access. Committing private repo names, internal IPs, personal emails (note existing `CODE_OF_CONDUCT.md` line 19), or PATs leaks sensitive infrastructure. | `Critical` | **Hard Gate:** `DIR-00` cleans conduct contact; `.gitignore` blocks runtime configs; CI runs `gitleaks` + public-repo pattern check; all tests/fixtures strictly synthetic. |
| **Security / Auth** | **Unauthenticated Exposure or Over-Privileged PAT:** Deploying dashboard on Hetzner without fail-closed auth or granting write/admin GitHub scopes compromises tracked private repositories. | `Critical` | **Hard Gate:** Prod boot aborts if `AAA_SESSION_SECRET` / operator hash unset (`DIR-02`); read-only GitHub permissions only; zero mutating remote endpoints. |
| **Architecture / Process** | **Duplication With Existing Inventory Scripts:** External JSON portfolio audits already evaluate repositories (`four_pillar_matrix_summary`), risking conflicting duplicate scoring tools. | `Medium` | **Mitigation:** Explicit `PortfolioSnapshotImportV1` adapter (`FEAT-09`, `DIR-04`) ingests external local-worktree and 4-Pillar JSON audits directly into `AAA`. |
| **External API** | **GitHub API Rate-Limit Exhaustion:** Polling `40+` repositories continuously across metadata, Actions, alerts, issues, and ProjectV2 can trip secondary rate limits. | `Medium` | **Mitigation:** `ETag`/`If-None-Match` conditional caching (`304` zero-cost), GraphQL batching, bounded concurrency (`3`), and automatic circuit breaker at `remaining <= 150`. |
| **Governance / CI** | **Unprotected `main` & Zero Automated Checks:** `branch_protection` is `Unprotected`, `ci_status` is `No CI`, and issues `#5`-`#11` have `labels: []` (`roadmap_s_open: null`). | `High` | **Hard Gate:** `DIR-00` labels issues and `DIR-01` wires mandatory CI; enable `main` branch protection requiring green CI before merges. |
| **Operational Trust** | **Silent Sync Failures Masking Decay:** Stale green scores mislead operators if background GitHub polling fails silently due to expired tokens or network outages. | `Medium` | **Mitigation:** Per-repo `last_sync_status`, persistent `STALE DATA` warning banner whenever age exceeds `2x` sync interval, and `/metrics` sync-failure alerts. |
| **Onboarding** | **External Developer Friction:** `README.md` currently holds only `12` lines (`733` bytes) and `0 LOC`, giving contributors insufficient architectural guidance. | `Medium` | **Mitigation:** Land `docs/MASTER_PLAN.md` (`this spec`), `docs/adr/0001-runtime-stack.md`, synthetic local dev script, and expanded `README.md` in `DIR-01`. |

### 7.2 Portfolio Relationships & Generic Integration Contracts

Because `AAA` is a public `Apache-2.0` repository, all downstream integration contracts are defined strictly in **repository-agnostic, configurable terms** rather than hardcoding any specific private repository identifiers:

1. **Monitored Portfolio Repositories (`example-repo-a`, `portfolio-service-1`, etc.):**
   - **Contract:** Configured dynamically at runtime via `targets.yaml` on Hetzner EU (never in git). Every tracked repository is expected to maintain standardized governance files (`LICENSE`, `README.md`, `SECURITY.md`, `DEPLOYMENT_TARGET.md` for deployable services, `PROJECT_DIRECTION.md`, `docs/MASTER_PLAN.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`) and active CI workflows.
   - **Flow:** `AAA` pulls read-only state via GitHub REST/GraphQL (`DIR-03`); `AAA` pushes zero modifications back to monitored repositories.
2. **External 4-Pillar & Local Worktree Verification Pipelines (`portfolio-audit-cli`):**
   - **Contract:** Any external inventory or 4-Pillar security/quality audit runner (evaluating the 21-layer `p1_*` through `p4_*` verification matrix and local clean/dirty git worktree states) submits structured JSON matching `PortfolioSnapshotImportV1` to `POST /api/v1/imports/snapshot` (`DIR-04`) using a dedicated scoped bearer token.
   - **Flow:** External runner -> authenticated JSON POST -> `AAA` `four_pillar_audits` & `worktree_state` persistence -> unified per-repo drilldown view alongside live GitHub CI/CVE telemetry.
3. **Shared Hetzner EU Operations & Monitoring Stack:**
   - **Contract:** `AAA` exposes unauthenticated minimal `/api/healthz` for container/reverse-proxy liveness and authenticated/internal `/metrics` (Prometheus format) for central Hetzner observability dashboards and alerting, plus standard nightly `sqlite3 .backup` artifacts compatible with off-box encrypted backup pipelines (`DIR-06`).
4. **AI Coding Agents & Automated Governance Workflows:**
   - **Contract:** Agents read `docs/MASTER_PLAN.md`, `dev/FEATURES.md`, and `dev/TEST-RESULTS.md` directly from git (and optionally query read-only `/api/v1/repos/:owner/:name` when authorized on trusted operator infrastructure) to prioritize remediation tasks using deterministic rule IDs (`CI-001`, `SEC-001`, `DEP-001`, `RDM-001`).
