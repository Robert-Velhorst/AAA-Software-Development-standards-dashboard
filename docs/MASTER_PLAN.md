# AAA — Software Development Standards Dashboard (`AAA-Software-Development-standards-dashboard`): Master Technical & Feature Specification

| Field | Value |
| --- | --- |
| **Repo ID** | `AAA` |
| **Repository** | `Robert-Velhorst/AAA-Software-Development-standards-dashboard` ([GitHub](https://github.com/Robert-Velhorst/AAA-Software-Development-standards-dashboard)) |
| **Canonical GitHub Path** | `docs/MASTER_PLAN.md` |
| **Canonical Drive Doc** | `Public Repository Specification (Private Internal Drive Link Redacted)` (`Internal Private Technical Doc (redacted in public repository)`) |
| **Document Track** | `Operational Charter` (`Master Technical & Feature Specification`) |
| **Authoritative Owner Classification (`2026-11-25` / `2026-11-26` Verified)** | Open-Source **100% Passive Read-Only Compliance Scoreboard** (`Apache-2.0`; Public Repo During Active Dev) |
| **Consolidation / Portfolio Role** | Standalone Passive Compliance Scoreboard Control Plane (Active Public Apache-2.0 Repo; Zero GitHub Write Permissions, Zero Issue Creation, Zero Coding-Agent Orchestration) |
| **Pricing / Governance Model** | `N/A` — Non-commercial open-source engineering compliance scoreboard (`Apache-2.0`; zero SaaS billing; **`EUR 0.00/mo` variable LLM/SaaS cap**; **`EUR 0.00/mo` colocated or `<= EUR 10–20/mo` dedicated Hetzner EU VPS ceiling `[Planning Hypothesis (RA)]`**) |
| **Target Stack (`Provisional Default Pending #5 ADR-0001`)** | `Node.js 22 LTS + Fastify 5 + SQLite WAL (better-sqlite3) + React 19 + Vite + Caddy 2` (provisional primary baseline pending formal ratification in `#5 [S0-01]` `ADR-0001`; optional `Go` backend swap preserves identical schema and HTTP/SSE contracts; validated strictly against synthetic fixtures) |
| **Hosting Target** | Hetzner EU (self-hosted authenticated operator access behind Caddy TLS; Vercel and unapproved serverless/tunnel hosting permanently banned via `DEPLOYMENT_TARGET.md` and PR `#3` commit `084a164`) |
| **As-Of Date** | `2026-11-26` (synced to `detailed_repo_status.json` and live GitHub telemetry at `HEAD c5cec63` / `2026-11-25T22:38:57Z`) |
| **Current Stage & Readiness** | `01 - Empty Skeleton (0%)` — `Spec Only` (`0%` overall completion, `0%` raw subsystem readiness; Backend `0%`, Frontend `0%`, Data `0%`, Integrations `0%`, QA/Ops `0%`; Auth `N/A (Local Tool / Spec)`; `ci_status: No CI`; `4-Pillar: Not Run (App Not Built Yet)` (`0/21` confirmed; `17` Applicable / `4` N/A under provisional Node.js 22 default); `Speed: Not Run (0/4)`; `Resource: Not Run`; `main` branch `Unprotected`) |
| **Feature Completeness** | `0%` (`0` built runtime modules; `dev/FEATURES.md` tracks `0` working / `0` partial / `50` to build / `9` intentionally not automated across `59` capability rows; `118` open issues in `detailed_repo_status.json` (`121` GitHub REST `open_issues_count` incl. PR/sync delta), `5` closed superseded `#24`, `#46`, `#47`, `#52`, `#53`, `1` open PR, `3` branches; `CODE_OF_CONDUCT.md:19` and issue `#30` scrubbed `2026-11-25`) |
| **Codebase Scale** | `14` tracked repository files (`6` root `.md` files, `0` source files, `0` test files, `0` total LOC) — `Markdown Stub Only` |
| **Merged Prior Sources** | `detailed_repo_status.json` (`2026-11-26`), `live_commits_20261126.json` (`HEAD c5cec63`), Internal Operational Charter (`2026-11-15` / `2026-11-20` locked direction, redacted for public repository), `2026-11-25` Alignment (`PROJECT_DIRECTION.md`, `docs/MASTER_PLAN.md`, `dev/FEATURES.md`), `DEPLOYMENT_TARGET.md` (`ca41c87`, PR `#3` `084a164`), `README.md` (`3762c49`), `dev/TEST-RESULTS.md` (`559853d`), `SECURITY.md` (`#1`), `CONTRIBUTING.md` (`#2`), `CODE_OF_CONDUCT.md` (sanitized `2026-11-25`), `LICENSE` (`Apache-2.0`), `.github/*`, and GitHub Issues `#5`–`#55` (incl. scrubbed `#30`) |

---

## 1. Operational Charter, Mission & Authoritative Owner Direction (`2026-11-26` Alignment)

### 1.1 Mission & Operational Purpose

`AAA` (`Robert-Velhorst/AAA-Software-Development-standards-dashboard`) is a **Greenfield Operational Charter** serving strictly as a **100% passive, read-only software development standards & compliance scoreboard** across multi-repository portfolios. Rather than relying on manual status spreadsheets or stale point-in-time inventory sweeps, `AAA` ingests read-only repository signals—CI workflow pass rates, security and dependency advisories, license and documentation hygiene, deployment-target drift, GitHub ProjectV2 / unlabeled-issue visibility, and external 4-Pillar verification snapshots (`PortfolioSnapshotImportV1`)—into a durable, queryable, exception-first compliance dashboard built on a provisional **`Node.js 22 LTS + Fastify 5 + SQLite WAL + React 19 + Caddy 2`** baseline (pending `#5 [S0-01]` `ADR-0001` ratification).

Crucially, `AAA` operates under a **dual-context open-source and strict read-only boundary** locked on `2026-11-20`, sharpened on `2026-11-25` (`c5cec63`), and verified on `2026-11-26`:

1. **Open-Source Public Codebase (`Apache-2.0`, Zero Private Data Leakage):** Because external software developers collaborate on the project, the repository stays intentionally **Public** under **Apache License 2.0** (`LICENSE`). All source code, schemas, synthetic test fixtures (`example-org/*`), Docker/Caddy templates, issues, and documentation MUST be 100% generic and strictly free of private repo names, internal IP addresses, private external doc IDs/links, or personal email literals.
2. **Self-Hosted Internal Operator Deployment (Hetzner EU):** When deployed to monitor real portfolios, the running scoreboard operates behind mandatory fail-closed operator authentication on self-hosted **Hetzner EU** infrastructure. Private repository lists, internal audit datasets, read-only GitHub tokens, and compliance telemetry exist exclusively in authenticated runtime storage and never enter version control.
3. **100% Passive Read-Only Boundary (Zero Writes, Zero Agent Orchestration):** Separate external orchestrators own autonomous coding-agent execution, backlog queues, and sprint forecasting. `AAA` holds **zero GitHub write permissions**, performs **zero GitHub issue creation or PR creation**, and runs **zero coding-agent orchestration or feature-completeness forecasting** (`#24`, `#46`, `#47`, `#52`, `#53` closed as superseded `2026-11-25`).

### 1.2 Beneficiaries & Primary Operators

- **Engineering Lead / Portfolio Maintainer:** Uses `AAA` as a daily read-only compliance scoreboard to spot CI breaks, critical advisories, docs/license drift, unlabeled roadmap issues, and Hetzner violations in `<= 5` minutes (`VG-01`).
- **External & Open-Source Contributors:** Develop, test, and extend `AAA` locally against deterministic synthetic mock repositories (`example-org/example-repo-a`, `example-org/portfolio-service-1`) without needing access to private targets or credentials.
- **External Governance Readers & Optional Read-Only Feed Consumers:** Consume deterministic pass/warn/fail scores and rule IDs (`DOC-002`, `DEP-001`) from `docs/MASTER_PLAN.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`, or read-only `/api/v1/*` endpoints without granting `AAA` write or orchestration authority.

### 1.3 Authoritative `2026-11-25` Locked Decisions & `2026-11-26` Sanitization Confirmation

Every engineering, packaging, and governance decision in this specification honors all locked directives from `2026-11-20` and `2026-11-25`, plus `2026-11-26` public sanitization verification:

1. **Repo Visibility (`2026-11-20` / `2026-11-25`):** Keep `AAA` **Public (`Apache-2.0`)** during active development so external contributors can submit PRs cleanly against synthetic fixtures.
2. **Strict Public/Private Security Boundary (`DIR-00`, Live Scrub Confirmed `2026-11-26`):** Never commit private repository names, internal audit counts, private Drive links/IDs, internal server IP addresses, personal email addresses, production backups, or access tokens into git history, tests, screenshots, issues, or documentation. **Live Verification (`2026-11-25/26`):** Both `CODE_OF_CONDUCT.md` line 19 (former maintainer personal email literal) AND public GitHub issue `#30` (former internal organization reference) were scrubbed on live GitHub, leaving **`0` private leaks across all `125` repository issues**. Automated CI `gitleaks` + regex checks (`[FEAT-HYG-01]`) remain required before code merges.
3. **100% Passive Read-Only Scoreboard ONLY (`2026-11-25`):** Keep **zero GitHub write permissions, zero issue creation, zero PR creation, zero coding-agent orchestration, and zero feature-completeness creep**. Build `FEAT-01`–`FEAT-14` strictly against synthetic fixtures.
4. **Hosting Target (`DEPLOYMENT_TARGET.md`, PR `#3` commit `084a164`):** Production hosting is locked to **Hetzner EU** behind authenticated operator access and Caddy TLS. Vercel and unapproved serverless or public-tunnel hosting are permanently banned for production deployments.
5. **Stack Ratification & OIDC Scoping (`2026-11-26` Audit Fix):** Mark `Node.js 22 LTS + Fastify 5 + SQLite WAL + React 19 + Vite + Caddy 2` as the **Provisional Primary Default Stack** pending formal ratification in `#5 [S0-01]` `ADR-0001` (preserving the documented `Go` backend swap option). Explicitly lock **`v1` authentication** to Argon2id/scrypt + `operator_sessions` (`#6`, `#34`) and **defer OIDC/SSO federation to `v2+`**.
6. **Build Sequencing Discipline:** Resolve governance/sanitization (`DIR-00` / `[FEAT-HYG-01]`), stack ratification/schema/CI baseline (`#5 [S0-01]`), fail-closed auth/token safety (`#6 [S1-01]`), read-only ingestion/persistence (`#7 [S3-01]`, `[FEAT-ING-10]`), snapshot import (`DIR-04`), compliance scoreboard UI + `VG-01` verification (`#8 [S5-01]`, `[FEAT-UI-01]`), Hetzner packaging (`#9 [S7-01]`), and Playwright/WCAG 2.2 AA verification (`#10 [S8-01]`) **before** undertaking Gate 3 transport/latency optimizations (`#11 [SPEED-01]`, `[FEAT-EVT-01]`).

### 1.4 Hard Monthly EUR Cost Ceilings & Quantified Operator Leverage Targets

Because `AAA` is governed strictly as a non-commercial **Operational Charter** (`N/A` SaaS billing), operational return is enforced through hard monthly EUR expenditure ceilings and measurable operator time/error-reduction gates (`VG-01`):

#### Hard Monthly EUR Cost Ceilings

| Cost Layer | Hard Ceiling / Range | Classification | Enforcement Mechanism |
| --- | --- | :---: | --- |
| **Variable LLM / AI API Spend** | **`EUR 0.00 / month`** | `VF` | `AAA` executes zero LLM calls; compliance evaluation is 100% deterministic rule logic (`default-rules.yaml`). |
| **Variable External SaaS / Managed DB / Auth Fees** | **`EUR 0.00 / month`** | `VF` | Embedded `SQLite WAL`, self-contained Argon2id/scrypt `v1` auth, and GitHub REST/GraphQL conditional `ETag` polling (`304` zero-cost). |
| **Fixed Hetzner EU Runtime Infrastructure** | **`EUR 0.00 / month` incremental** (colocated on existing Hetzner EU node) OR **`<= EUR 10–20 / month`** (dedicated `CX22`/`CPX11` `~EUR 4–7/mo` + off-box backup slice `<= EUR 3.81/mo`) | `Planning Hypothesis (RA)` | Verify exact Hetzner checkout tariff in `DIR-06` (`docs/HETZNER_DEPLOY.md`) prior to dedicated VPS provisioning; container RAM strictly capped at `<= 256 MB` steady-state. |
| **Combined Production Total Monthly Ceiling** | **`EUR 0.00 / mo` (colocated) to `<= EUR 20.00 / mo` (dedicated)** | `Planning Hypothesis (RA)` | Enforced via Gate `G5` container memory/storage limits and zero paid SaaS vendor dependencies. |

#### Quantified Operator Leverage Targets (`VG-01` `[Planning Hypothesis (RA)]`)

| Leverage Dimension | Pre-`AAA` Manual Baseline | Target Post-Cutover Outcome (`RA`) | Verification Path |
| --- | --- | --- | --- |
| **Cross-Portfolio Hygiene Triage Time (`VG-01`)** | `2–4 hours` per manual multi-repo audit cycle (`120–240 min`) | **`<= 5 minutes`** daily exception check (`>= 85%` triage time reduction `[Planning Hypothesis (RA)]`) | Timed synthetic portfolio triage walkthrough in **`DIR-05` / `DIR-07`** (Gate `G4` `VG-01`) |
| **Mean Time to Detect CI / Advisory / Drift Regression** | `7–30 days` between manual inventory sweeps | **`<= 15–60 minutes`** (automated conditional polling cadence `[Planning Hypothesis (RA)]`) | `sync_runs` scheduler timestamps & `STALE DATA` banner tests (`DIR-03`) |
| **Hosting Drift, Secret Leak & Unlabeled Issue Escape Rate** | Unprotected `main`, ad-hoc label gaps (`labels: []`), manual `vercel.json` checks | **`0` undetected Vercel drift commits**, **`0` private-data/secret leaks** in public Git, **`100%` unlabeled roadmap issue detection** (`[Planning Hypothesis (RA)]`) | `CI` (`gitleaks` + regex guard), `DEP-001`, `RDM-001`, `standardsctl check-pr` (`DIR-00`, `DIR-01`, `DIR-03`) |

---

## 2. Historical Source Reconciliation, Telemetry Drift & Prior-Plan Assessment Ledger

### 2.1 Complete Source Reconciliation Ledger

As of `2026-11-26`, `AAA` has zero historical commercial business plans in Google Drive; all planning context originates from the internal `2026-11-15` Operational Charter / `2026-11-20` locked direction (`Internal Private Technical Doc (redacted in public repository)`), the repository's governance files, `2026-11-25` alignment commits (`5319714`..`c5cec63`), and the `2026-11-26` DRS/commit telemetry. Every source artifact is reconciled below without leaking private identifiers.

| Legacy Source (Title & Date) | Concept / Requirement / Figure | Assessment (`Retained` / `Adapted` / `Deferred to v2+` / `Superseded`) | Reconciliation Rationale & Where Integrated |
| --- | --- | --- | --- |
| `detailed_repo_status.json` & `live_commits_20261126.json` (`2026-11-26`, `HEAD c5cec63`) | Stage `01` (`0%` overall / `0%` raw); `14` files, `0` LOC, `6` root `.md`s, `ci_status: No CI`, `branch_protection: Unprotected`, `4-Pillar: Not Run (0/21)`, `118` open issues (`121` REST API `open_issues_count`), `5` closed, `1` PR, `3` branches; commits `559853d` -> `c5cec63` | **Retained (Tech Telemetry) / Prose Error Caught (§2.2)** | Technical metrics govern Header, §5.5, §6.1, §7.2, and `_meta/AAA.json`. Erroneous DRS `"single-line README stub, MIT license, seven issues"` text is explicitly corrected to **`Apache-2.0`**, `12`-line `README.md`, and `118` open issues (§2.2). |
| Internal Operational Charter (`2026-11-15`) & `2026-11-20` Locked Direction (`Internal Private Technical Doc (redacted in public repository)`) | Greenfield `0%` baseline (`10` pre-Nov-20 files, `0` LOC); remain Public `Apache-2.0` for external collaboration; zero private repo lists/audit outputs/tokens/IPs in public Git; Hetzner EU target; SQLite persistence (`#7`); Risk #1 premature `#11` optimization; Risk #2 static JSON duplication; Risk #3 rate limits & PAT scope | **Retained & Sanitized (`2026-11-26`)** | Governs Sections 1, 3, 4, 5, 6, and 7. All internal label tokens, private Doc URLs, and raw portfolio counts scrubbed for public `docs/MASTER_PLAN.md` safety. External JSON import (`FEAT-09`, §5.4) resolves Risk #2. |
| `PROJECT_DIRECTION.md`, `docs/MASTER_PLAN.md`, `dev/FEATURES.md` (`2026-11-25` Alignment, commits `8086bf5`, `c5cec63`) | Locks **100% Passive Read-Only Compliance Scoreboard ONLY**; bans GitHub write permissions, issue/PR creation, and coding-agent orchestration; retires `#24`, `#46`, `#47`, `#52`, `#53`; expands capability catalog to `59` rows (`50` to build, `9` excluded); aligns `Node 22 + Fastify 5 + SQLite + React 19 + Caddy` on synthetic fixtures | **Retained (Authoritative) / OIDC & Stack Notes Adapted** | Authoritative scope baseline across §1–§7. OIDC reference in `dev/FEATURES.md` (`#34`) is explicitly scoped/deferred to **`v2+`** (§2.2, §4.1, §5.3), and the stack is marked provisional pending `#5` `ADR-0001`. |
| `DEPLOYMENT_TARGET.md` (`2026-10-13` `ca41c87` & `2026-10-18` PR `#3` `084a164`) | Mandates Hetzner EU production target; permanently removes Vercel; prohibits unapproved serverless/public-tunnel production deployments; requires documented infra, DB migration, DNS/TLS, secrets, monitoring, backups, and rollback prior to cutover | **Retained (Hard Constraint)** | Integrated into §1.3, §4.2 (`HET-01..04` / `FEAT-07`), §5.5, and §6.2 `DIR-06`. |
| `README.md` (`2026-07-25` 1-line stub -> `2026-11-20` `3762c49` `12`-line / `733`-byte header) | Direction banner linking `PROJECT_DIRECTION.md`, `dev/FEATURES.md`, and `dev/TEST-RESULTS.md`, but still lacks architecture overview, synthetic local quickstart, and `docs/MASTER_PLAN.md` pointer | **Adapted / Expansion Required** | Retained direction links; full quickstart expansion scheduled in `DIR-01` (`#5 [S0-01]`). |
| `dev/TEST-RESULTS.md` (`2026-11-20`, commit `559853d`) | Confirms `0` GitHub Actions runs, `0` executable test entry points, and doc-link validation only at revision `3762c4972faf` | **Retained (Baseline Fact)** | Anchors §6.1 build reality (`0%` test coverage, `No CI`, `0/21` 4-Pillar layers confirmed). |
| `LICENSE` (`Apache-2.0`), `SECURITY.md` (`#1`), `CONTRIBUTING.md` (`#2`), `CODE_OF_CONDUCT.md` (sanitized `2026-11-25`), `.github/*` | Establishes `Apache-2.0` licensing, private vulnerability disclosure, synthetic-example rule in PRs, Dependabot config, and PR risk checklist | **Retained & Sanitized (`2026-11-25`)** | Verified `Apache-2.0` canonical license. Personal maintainer email removed from `CODE_OF_CONDUCT.md:19` (`2026-11-25`) and public issue `#30` scrubbed (`0` leaks across `125` issues); automated CI guard + `#5`–`#11` labels + `main` protection tracked in `[FEAT-HYG-01]`. |
| GitHub Issues `#5`–`#10` (`2026-11-13`) & `#13`–`#55` (`2026-11-23/25`, excl. closed `#24`, `#46`, `#47`, `#52`, `#53`) | Core roadmap (`[S0-01]`..`[S8-01]`), expanded 5-product capability backlog, and 5 gap-closure capabilities (`[FEAT-HYG-01]`, `[FEAT-ING-10]`, `[FEAT-REM-03]`, `[FEAT-UI-01]`, `[FEAT-EVT-01]`). Note `#5`–`#11` still carry `labels: []` | **Retained (Sequenced)** | Directly drives §4.2, §5, and §6.2 `DIR-00` through `DIR-07`. Issue label remediation captured in `DIR-00`. |
| GitHub Issue `#11` (`[SPEED-01]`, `2026-11-13`) & `[FEAT-EVT-01]` | Zero-Wait architecture (local-first SWR, SSE push, sub-`10ms` DB queries, Hetzner HTTP/3, CI latency gates) | **Adapted / Deferred to Gate 3 (`DIR-08`)** | Avoids premature complexity on `0` LOC; SQLite WAL + covering indexes + SSE-friendly API boundaries are baked into §5 so `DIR-08` adds `#11` cleanly after `DIR-01`–`DIR-07`. |
| External Portfolio 21-Layer Verification Schema (`p1_*`–`p4_*` matrix) | Evaluates repositories across 4 pillars (`6 + 3 + 5 + 7 = 21` layers) alongside static JSON snapshots | **Adapted** | Integrated into `PortfolioSnapshotImportV1` (`FEAT-09` / `ING-08`, §5.4) and explicitly mapped with `N/A` exclusions (`17` Applicable / `4` N/A) in §5.5. |

### 2.2 Telemetry & `2026-11-26` DRS Discrepancy Reconciliation

1. **Erroneous DRS Prose Corrected (`Apache-2.0` & `12`-Line `README.md`, Not `"MIT / 1-Line Stub"`):** `detailed_repo_status.json` `what_is_built` and `status_summary` still contain stale prose claiming `"single-line README stub, MIT license, and seven open ... tracking issues"`. **Verified Fact (`VF-01`):** Root `LICENSE` is **`Apache-2.0`** (201 lines), `README.md` is a `12`-line (`733`-byte) direction header since `3762c49`, and `open_issues` stands at **`118`** (`121` in `live_commits_20261126.json`), not `7`.
2. **Issue & Capability Arithmetic Reconciled (`118` vs `121` vs `50`/`59`):**
   - `detailed_repo_status.json` reports **`118` open issues**, **`5` closed superseded issues** (`#24`, `#46`, `#47`, `#52`, `#53`), **`1` open PR**, **`3` branches**, and **`14` total files** (`0` LOC).
   - `live_commits_20261126.json` reports **`121` `open_issues_count`** (GitHub REST API includes the open PR + incremental audit/tracking issue sync delta across `125` total repository issue numbers).
   - `dev/FEATURES.md` (`2026-11-25`) tracks **`59` functional capability rows**: **`50` To Build** (`#5`–`#11`, `#13`–`#23`, `#25`–`#45`, `#48`–`#51`, `#54`–`#55`, plus `[FEAT-HYG-01]`, `[FEAT-ING-10]`, `[FEAT-REM-03]`, `[FEAT-UI-01]`, `[FEAT-EVT-01]`) + **`9` Intentionally Not Automated** (`SEC-03`, `HET-03`, `OPS-06`, `REM-03`, and superseded `#24`, `#46`, `#47`, `#52`, `#53`), while additional open GitHub issues cover 4-Pillar/Speed/Resource/audit verification tracking items bringing the open tracker total to `118` (`121` GitHub API total).
3. **Public-Repo Sanitization Confirmed Live (`CODE_OF_CONDUCT.md:19` & Issue `#30`):** On `2026-11-25`, both the former personal email literal in `CODE_OF_CONDUCT.md:19` and internal organization name references in public issue `#30` were scrubbed on live GitHub, yielding **`0` private leaks across all `125` issues**. Remaining `DIR-00` hygiene items (`[FEAT-HYG-01]`: automated CI `gitleaks` + regex guard, labeling `#5`–`#11`, enabling `main` branch protection) remain open until code lands.
4. **Provisional Stack & `v2+` OIDC Deferment Reconciled:** Previous drafts stated `#5` `ADR-0001` must still ratify the stack while hardcoding Node 22/Fastify paths and referencing `"configured OIDC provider"` alongside a static `AAA_OPERATOR_PASSWORD_HASH` table. **Resolution:** All Node.js 22 / Fastify 5 / SQLite / React 19 paths in §§4–6 are explicitly marked **Provisional Primary Default pending `#5` `ADR-0001` ratification**, and **OIDC / SSO federation (`#34`) is formally deferred to `v2+`** (`v1` ships fail-closed Argon2id/scrypt + `operator_sessions` only).

---

## 3. Problem Domain, Operators, Workflows & Non-Negotiable Boundaries

### 3.1 Operational Friction Solved

Multi-repository engineering teams accumulate silent technical debt faster than manual reviews can detect it:

1. **Invisible CI & Security Decay:** Repositories pass an initial prototype sprint and then accumulate failing scheduled builds, disabled workflows, or critical dependency advisories without an engineer opening each repo tab individually.
2. **Governance & Documentation Drift:** Files such as `LICENSE`, `SECURITY.md`, `DEPLOYMENT_TARGET.md`, `PROJECT_DIRECTION.md`, and `docs/MASTER_PLAN.md` fall out of sync, or contributors introduce unapproved hosting providers (e.g., `vercel.json`) despite explicit architecture rules.
3. **Unlabeled & Stale Roadmaps:** Tracking issues use naming conventions (`[S0-01]`, `[S5-01]`) in titles while leaving GitHub `labels` empty (`roadmap_s_open: null`), breaking automated stage tracking across portfolios.
4. **Public/Private Collaboration Leakage Risk:** When an open-source contributor or coding agent assists on tooling, sharing raw portfolio audit sheets exposes private project names, infrastructure IPs, and security weaknesses.
5. **Local-Only Blind Spots:** Purely GitHub-API dashboards cannot see dirty local git worktrees or offline 4-Pillar verification suites unless an authenticated snapshot import bridge captures them.

### 3.2 Operator Ergonomics & Workflow Principles

- **Exception-First Triage (`VG-01`):** The default landing screen answers *"What needs engineering attention right now?"*—surfacing critical advisories, CI breaks, deployment-target drift, and stale sync health before green compliance badges so daily triage completes in `<= 5` minutes.
- **Deterministic Explainability:** Every repository score (`0–100`) and pass/warn/fail badge traces back to explicit, human-readable rule evaluations (e.g., `DOC-002: SECURITY.md missing on default branch`) rather than opaque heuristics or LLM scores.
- **Zero-Friction Keyboard & Screen-Reader Accessibility (`#10 [S8-01]`):** Target **WCAG 2.2 AA** compliance—semantic HTML landmarks, visible focus rings, keyboard-only table sorting/drilldown (`Ctrl/Cmd+K`, `/`, `j/k`), accessible color contrast independent of red/green color alone (explicit text status pills + icons), and NL/EN UI labels (`#30`).
- **Synthetic-First Local Development:** Any external contributor clones `AAA`, runs one command (`npm run dev:synthetic` or equivalent), and works against realistic, 100% synthetic example repositories (`example-org/example-repo-a`, `example-org/portfolio-service-1`) stored in a local gitignored SQLite file.

### 3.3 Legal, Platform ToS, Privacy (GDPR) & Security Boundaries

1. **Public-Repo Sanitization Gate (Non-Negotiable):** Because `AAA` is a public `Apache-2.0` repository, **zero** private repository names, private organization repo lists, internal audit numbers, internal server IP addresses, personal email addresses, production backups, or access tokens may ever be committed. CI MUST enforce automated secret scanning (`gitleaks`) and pattern hygiene checks on every PR.
2. **GitHub Platform ToS & Rate-Limit Stewardship:** All GitHub REST and GraphQL ingestion MUST authenticate via a least-privilege GitHub App installation token or fine-grained read-only PAT, use `User-Agent` headers, honor `ETag` / `If-None-Match` conditional caching (`304` responses cost zero primary rate-limit quota), batch metadata via GraphQL where appropriate, and immediately honor `Retry-After` / `X-RateLimit-Remaining` backoff floors.
3. **Least-Privilege Read-Only Execution Boundary (`#6 [S1-01]`):** `AAA` possesses **zero write authority** over monitored repositories. Tokens MUST NOT hold `contents:write`, `administration:write`, `packages:write`, or deletion permissions. `AAA` never pushes commits, opens PRs automatically, or modifies remote infrastructure.
4. **Privacy & GDPR Minimization:** `AAA` audits *repository artifacts and system states*, NOT individual developer performance. Commit author personal emails and IP addresses are excluded from persistent compliance tables; authentication rate-limit counters hash/truncate client IPs transiently in memory/short TTL stores and session audit logs store only operator IDs and timestamps.
5. **Fail-Closed Operator Authentication (`#6 [S1-01]`):** In production (`NODE_ENV=production` or `AAA_ENV=production`), the application MUST refuse to bind or serve API/UI routes if `AAA_SESSION_SECRET` or `AAA_OPERATOR_PASSWORD_HASH` is unset, weak, or defaulting to development bypasses.
6. **Zero Financial Authority:** `AAA` connects to zero payment gateways, invoicing APIs, or commercial billing engines.

### 3.4 Explicit Non-Goals (`2026-11-26` Locked Boundary)

- **Not a Commercial Multi-Tenant SaaS:** No user self-signup, Stripe integration, tenant billing plans, or public anonymous dashboard exposure (`OPS-06`).
- **Not a CI/CD Execution Engine:** `AAA` ingests workflow statuses from GitHub Actions and external 4-Pillar test reports; it does not provision runners to build external repositories.
- **Zero GitHub Write Permissions & Zero Issue/PR Creation:** `AAA` holds read-only GitHub permissions ONLY (`#24` issue creation & `#53` PR-blueprint automation retired `2026-11-25`). Copyable local remediation hints (`[FEAT-REM-03]`) help human operators fix issues manually without remote API writes.
- **Zero Coding-Agent Orchestration & Zero Feature-Completeness Creep:** Separate external orchestrators own agent dispatch, execution queues (`01..N`), sprint effort forecasting, and agent readiness scoring (`#46`, `#47`, `#52` retired `2026-11-25`). `AAA` stays strictly a passive read-only compliance scoreboard.
- **Not Serverless / Vercel:** Permanently excluded per `DEPLOYMENT_TARGET.md` and PR `#3` (`HET-03`).

---

## 4. Exhaustive Feature Specification & System Mechanics

### 4.1 End-to-End Operational Mechanics & Execution Flows

Because `AAA` currently contains `0` LOC, the following operational mechanics define the exact runtime behavior to be implemented across Directives `DIR-00`–`DIR-08` (`#5`–`#11`).

#### Flow A: Fail-Closed Bootstrap & Runtime Configuration
1. On process start, the server reads environment variables and mounts the runtime config directory (`/data` on Hetzner, `./.local-dev` locally, both excluded from git via `.gitignore`).
2. Startup validation asserts:
   - `AAA_ENV=production` (`v1`): requires non-empty `AAA_SESSION_SECRET` (`>= 32` random bytes), valid `AAA_OPERATOR_PASSWORD_HASH` (Argon2id/scrypt), and a reachable `AAA_TARGETS_PATH` (or initialized `repositories` table). Missing any required security variable aborts startup with exit code `1`. *(OIDC federation is explicitly deferred to `v2+`.)*
   - `AAA_ENV=synthetic` (development/CI/demo only): disables outbound GitHub calls and seeds synthetic fixture repositories (`example-org/example-repo-a`, etc.) into a local ephemeral SQLite database clearly badged `DEMO SANDBOX`.
3. SQLite opens in WAL mode (`PRAGMA journal_mode = WAL; PRAGMA foreign_keys = ON; PRAGMA busy_timeout = 5000;`), applies versioned SQL migrations cleanly inside a transaction, and binds strictly to loopback (`127.0.0.1:8080` in Docker behind Caddy TLS).

#### Flow B: Operator Authentication & Access Control (`v1` Argon2id/scrypt; OIDC Deferred to `v2+`)
1. Unauthenticated requests to `/`, `/api/v1/dashboard/*`, `/api/v1/repos/*`, or `/api/v1/events/stream` receive `401 Unauthorized` (API) or redirect to `/login` (browser). Only `/api/healthz` (returning minimal `{"status":"ok","db":"ok"}` without version/repo leakage) and `/login` are unauthenticated.
2. Operator submits credentials to `POST /api/v1/auth/login` (rate-limited: max `5` attempts per `15` minutes per IP + exponential lockout).
3. On Argon2id/scrypt hash verification, the server issues an `HttpOnly`, `Secure`, `SameSite=Strict` session cookie backed by a server-side SHA-256 hashed session token in `operator_sessions` (default `12h` idle / `7d` absolute expiry) plus a synchronizer CSRF token for all `POST`/`PUT`/`PATCH`/`DELETE` routes.
4. `v2+` OIDC extension path (out of scope for `v1` MVP): adds `OIDC_ISSUER_URL`, `OIDC_CLIENT_ID`, `OIDC_CLIENT_SECRET`, and `OIDC_REDIRECT_URI` with PKCE `GET /api/v1/auth/oidc/login` + `GET /api/v1/auth/oidc/callback` and `oidc_subject` column migration on `operator_sessions`.

#### Flow C: GitHub Repository, CI, Security & ProjectV2 Ingestion (`#7 [S3-01]`)
1. Triggered either by the internal scheduler (default every `15` minutes for fast CI/PR checks, every `60` minutes for full docs/advisories/ProjectV2 sweeps) or manually via `POST /api/v1/sync/run` (operator UI button / CLI).
2. If `AAA_INGESTION_PAUSED=true`, scheduled runs log a skipped entry and return safely.
3. The ingestion worker loads active target repositories from runtime `targets.yaml` / `repositories` table (never hardcoded in source).
4. For each repository (bounded concurrency, default `3` workers):
   - Checks remaining GitHub API rate limit (`X-RateLimit-Remaining`); if `<= 150`, pauses non-urgent jobs until reset timestamp and marks `sync_runs.status = 'rate_limited_partial'`.
   - Sends `GET /repos/{owner}/{repo}` with stored `etag`; HTTP `304 Not Modified` skips redundant payload parsing.
   - Fetches branch protection status (gracefully handles `403` when token lacks admin access, recording `unknown_insufficient_scope` rather than crashing).
   - Fetches recent GitHub Actions workflow runs (`/actions/runs?per_page=20`) to compute `ci_pass_rate_20` and `last_ci_status`.
   - Fetches Dependabot / vulnerability alerts (`/dependabot/alerts?state=open&per_page=100`) grouped by `critical`, `high`, `medium`, `low`.
   - Checks existence/metadata of standard governance files on the default branch (`LICENSE`, `README.md`, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `DEPLOYMENT_TARGET.md`, `PROJECT_DIRECTION.md`, `docs/MASTER_PLAN.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`) and detects forbidden hosting drift (`vercel.json`, `.vercel/`).
   - Fetches open issues (`GET /repos/{owner}/{repo}/issues?state=open`) to detect untagged roadmap issues (`labels.length === 0` despite `[S*-01]` title prefix).
   - Queries GraphQL ProjectV2 items linked to the configured project board (optional per target config).
5. The Standards Rule Engine evaluates each repository against declarative rules in `default-rules.yaml`, computes deterministic weighted compliance scores (`0–100`) and pillar sub-scores, and commits a snapshot atomically inside SQLite. Single-repo `404` or `5xx` errors quarantine cleanly into `repo_sync_error` without aborting sibling repos.

#### Flow D: External Snapshot & 4-Pillar Audit Import (`PortfolioSnapshotImportV1`)
1. Because GitHub APIs cannot observe local uncommitted git worktree changes or offline 4-Pillar verification suites (`p1_*`..`p4_*`), external CI jobs or local collector CLI scripts push authenticated JSON payloads to `POST /api/v1/imports/snapshot` using a dedicated scoped machine bearer token (`AAA_SNAPSHOT_IMPORT_TOKEN_HASH`) or operator session + CSRF.
2. Payload validates strictly against `PortfolioSnapshotImportV1` (Zod schema).
3. Validated data updates `four_pillar_audits` and `worktree_state` (`clean` / `dirty`) inside SQLite with explicit source attribution (`github_api` vs `snapshot_import`).

#### Flow E: Compliance Dashboard, Drilldown & `VG-01` Triage (`#8 [S5-01]`)
1. Operator opens the web UI:
   - **KPI Strip:** Total tracked repos, Mean Compliance Score, Repos with Critical/High Advisories, Failing CI Repos, Hetzner Drift Violations, Stale/Error Sync Warnings.
   - **Filterable Portfolio Matrix:** Sort/filter by compliance tier (`Red 0–59`, `Amber 60–84`, `Green 85–100`), hosting compliance, open advisories, CI status, or stage/category tag.
   - **Per-Repository Drilldown (`/repos/{owner}/{name}`):** Shows complete rule-by-rule checklist (`Pass` / `Warn` / `Fail` / `Not Applicable` / `Insufficient Scope`), recent `20` CI workflow runs, open Dependabot advisories, ProjectV2 status items, `21`-layer 4-Pillar audit grid (`17` Applicable / `4` N/A), `30`-day score trend chart, and passive copyable remediation hints (`[FEAT-REM-03]`, e.g., `"Add SECURITY.md using repository template"`).
2. In Gate 3 (`#11 [SPEED-01]`, `[FEAT-EVT-01]`), live sync completion pushes incremental events over `GET /api/v1/events/stream` (SSE) so open operator tabs update smoothly via SWR without manual reloads.

### 4.2 Feature Capability Matrix (Master Epics & `2026-11-25` `dev/FEATURES.md` Catalog)

#### Master Architectural Epics (`FEAT-01`–`FEAT-15`)

| Feature ID | Module / Subsystem | Exact Behavior & Operator Flow | Status (`2026-11-26`) | Provisional Codebase Anchors (`Pending #5 ADR-0001`) | Target Acceptance Criteria |
| --- | --- | --- | --- | --- | --- |
| `FEAT-01` | Standards Schema & Rule Engine (`#5 [S0-01]`, `STD-01..06`, `ARC-01`) | Declarative, versioned rule catalog (`schema_version: "1.0"`) evaluating CI, Security, Docs/License, Hetzner Readiness, and Roadmap hygiene into deterministic `0–100` scores with `N/A` support | `Unbuilt Spec` | `packages/schema/src/standards.ts`, `apps/server/src/engine/evaluator.ts` (`#5`, `#13`, `#31`) | Rules validated via Zod; 100% deterministic unit-tested scoring across synthetic pass/warn/fail/`na` fixtures; zero hardcoded private repo names |
| `FEAT-02` | Operator Auth, Sessions & Security Headers (`#6 [S1-01]`, `SEC-01`, `SEC-04`) | `v1` Argon2id/scrypt operator login, rate-limited `/auth/login`, `HttpOnly`/`Secure`/`SameSite=Strict` cookies, CSRF protection, CSP/HSTS/XFO headers, fail-closed prod boot *(OIDC deferred to `v2+`)* | `Unbuilt Spec` | `apps/server/src/auth/*`, `apps/server/src/plugins/security.ts` (`#6`, `#34`, `dev/FEATURES.md`) | Unauthenticated requests to `/api/v1/*` (except `/auth/login`) return `401`; prod boot exits `1` if `AAA_SESSION_SECRET` missing; security headers verified in CI |
| `FEAT-03` | Least-Privilege Token Vault & Runtime Target Registry (`#6 [S1-01]`, `SEC-02`, `SEC-05`) | Reads repository allowlist and read-only GitHub PAT / App credentials exclusively from Hetzner `/run/secrets/` or `0600` runtime config; SSRF allowlist (`api.github.com`); redacts tokens in logs/JSON | `Unbuilt Spec` | `apps/server/src/config/targets.ts`, `apps/server/src/github/auth.ts` (`#6`, `#25`, `#35`) | Runtime redaction filter blocks token leaks; permission scope check alerts if write/admin token scopes appear |
| `FEAT-04` | Repository Metadata, License & Doc Hygiene Collector (`#7 [S3-01]`, `STD-03`, `AGT-03..04`) | Checks SPDX `LICENSE`, non-stub `README.md`, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `PROJECT_DIRECTION.md`, `docs/MASTER_PLAN.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`, branch protection, and passive docs/agent-config drift (`#48`, `#49`) | `Unbuilt Spec` | `apps/server/src/github/collectors/docs.ts` (`#7`, `#14`, `#21`, `#48`, `#49`) | Accurately detects missing/stubbed docs, license drift, and unprotected branches on synthetic repos using `ETag` caching |
| `FEAT-05` | CI Pass-Rate & GitHub Actions Collector (`#7 [S3-01]`, `[FEAT-ING-10]`, `ING-10..11`) | Polls recent GitHub Actions runs per repo, calculates rolling `N=20` pass rate, consecutive failure count, flake/duration telemetry (`#39`), and flags `No CI` repos | `Unbuilt Spec` | `apps/server/src/github/collectors/ci.ts` (`#7`, `#39`, `[FEAT-ING-10]`) | Correctly calculates pass %, latest conclusion, and `No CI` status across mocked Actions API responses |
| `FEAT-06` | Security Advisory & SBOM/SARIF Collector (`#7 [S3-01]`, `#18`, `ING-03`) | Ingests open Dependabot alerts, SARIF, and CycloneDX/SPDX SBOM feeds (`#18`), grouping by `critical`, `high`, `medium`, `low` and blast radius | `Unbuilt Spec` | `apps/server/src/github/collectors/security.ts` (`#7`, `#18`) | Maps severity counts and degrades cleanly with `insufficient_scope` status if repository alerts API returns `403` |
| `FEAT-07` | Hetzner Deployment Target & Drift Validator (`DEPLOYMENT_TARGET.md`, `#22`, `HET-01`) | Verifies `DEPLOYMENT_TARGET.md`, flags prohibited `vercel.json`/`.vercel/`/tunnel drift, tracks non-root `Dockerfile`/TLS readiness with `not_applicable` override for pure libs/specs | `Unbuilt Spec` | `apps/server/src/github/collectors/deployment.ts` (`#22`) | Flags `vercel.json` or missing `DEPLOYMENT_TARGET.md` on applicable services while respecting `na` categories |
| `FEAT-08` | GitHub ProjectV2 & Issue/Roadmap Hygiene Collector (`#7 [S3-01]`, `#36`, `ING-07`) | Queries GraphQL ProjectV2 boards and open issues/PRs; surfaces unlabeled `[S*-01]`/`[FEAT-*]` roadmap issues (`labels.length === 0`) without mutating remote boards | `Unbuilt Spec` | `apps/server/src/github/collectors/projectv2.ts` (`#7`, `#36`) | Batches GraphQL queries within rate budget and reports accurate `unlabeled_roadmap_issues` counts |
| `FEAT-09` | External Snapshot & 4-Pillar Audit JSON Importer (`#37`, `ING-04`, `ING-08`) | Authenticated `POST /api/v1/imports/snapshot` endpoint + CLI ingesting `PortfolioSnapshotImportV1` payloads (21-layer `p1_*`–`p4_*` matrix + local worktree clean/dirty state) | `Unbuilt Spec` | `apps/server/src/imports/snapshot.ts`, `packages/schema/src/snapshot.ts` (`#19`, `#37`) | Validates via Zod; rejects malformed JSON (`400`) and bad bearer tokens (`401`/`403`); preserves GitHub sync timestamps |
| `FEAT-10` | Compliance Dashboard Portfolio Matrix UI (`#8 [S5-01]`, `[FEAT-UI-01]`, `UIX-01`, `UIX-03`, `UIX-05..07`) | Authenticated React 19 UI showing KPI strip, Red/Amber/Green matrix, `STALE DATA` banner, `AAA_DEMO_MODE=true` synthetic sandbox (`#30`, `#32`), `NL`/`EN` UI, and `Ctrl/Cmd+K` palette (`#55`) | `Unbuilt Spec` | `apps/web/src/pages/DashboardPage.tsx` (`#8`, `#16`, `#30`, `#32`, `#55`, `[FEAT-UI-01]`) | Renders 20-repo synthetic portfolio at `1440px` & `375px` with zero console errors; daily triage completes in `<= 5 min` (`VG-01`) |
| `FEAT-11` | Per-Repository Drilldown & Copyable Remediation Hints (`#8 [S5-01]`, `[FEAT-REM-03]`, `REM-01`, `REM-05`, `UIX-02`) | `/repos/{owner}/{name}` rule evaluations, **passive copyable remediation hints** (`[FEAT-REM-03]`, zero GitHub writes), time-boxed waivers (`#23`), CI/CVE lists, 21-layer grid, and `30`-day trend (`#26`) | `Unbuilt Spec` | `apps/web/src/pages/RepoDetailPage.tsx` (`#8`, `#23`, `#26`, `[FEAT-REM-03]`) | Full rule breakdown + copyable CLI snippets + `30`-day history persisted across restarts without mutating GitHub |
| `FEAT-12` | Hetzner Docker Runtime, Caddy TLS, Backups & Monitoring (`#9 [S7-01]`, `#40`, `#41`, `HET-02`, `HET-04..05`) | Multi-stage non-root `Dockerfile` (`USER 10001`), `compose.hetzner.yml`, Caddy TLS/HTTPS, automated SQLite `.backup` + restore drill, protected Prometheus `/metrics` | `Unbuilt Spec` | `ops/hetzner/{Dockerfile,compose.hetzner.yml,Caddyfile,backup.sh}` (`#9`, `#40`, `#41`) | `docker compose up` passes `/api/healthz`; backup + restore script verifies SHA-256 & `PRAGMA integrity_check`; container RAM `<= 256 MB` |
| `FEAT-13` | Unit, Integration, Playwright E2E & WCAG 2.2 AA Suite (`#10 [S8-01]`, `#42`, `#43`, `QAL-01..03`) | Vitest unit/integration suites against mock GitHub server, Playwright E2E flows, `@axe-core/playwright` WCAG 2.2 AA audit, `gitleaks`, Trivy, and `standardsctl` (`#28`, `#44`) | `Unbuilt Spec` | `apps/server/tests/*`, `apps/web/e2e/*`, `.github/workflows/ci.yml` (`#10`, `#42`, `#43`) | CI green on synthetic fixtures; `0` `axe` critical/serious violations; `>= 80%` core coverage; `<= 250 KB` gzipped Vite JS |
| `FEAT-14` | Zero-Wait SWR/SSE Push, Sub-10ms DB, HTTP/3 & Latency Gates (`#11 [SPEED-01]`, `[FEAT-EVT-01]`, `UIX-04`, `UIX-08`) | Gate 3 optimization layer: SSE live sync push (`/api/v1/events/stream`), SWR cache, covering-index SQLite benchmark (`p95 <= 10ms` over `18,000` rows), HTTP/3 QUIC, CI perf gate | `Unbuilt Spec` *(Deferred to Gate 3)* | `apps/server/src/events/sse.ts`, `apps/server/tests/perf.bench.ts` (`#11`, `[FEAT-EVT-01]`) | Strictly deferred until `DIR-01`–`DIR-07` pass; `p95 <= 10ms` over `100` repos x `180` snapshots verified in CI |
| `FEAT-15` | Public-Repo Governance, Sanitization Gate & Issue Labels (`DIR-00`, `[FEAT-HYG-01]`, `STD-08`) | `Apache-2.0` `LICENSE`, `SECURITY.md`, `CONTRIBUTING.md`, `DEPLOYMENT_TARGET.md`, `PROJECT_DIRECTION.md`, `dev/*`; **live scrub of `CODE_OF_CONDUCT.md:19` & issue `#30` completed `2026-11-25`**; `[FEAT-HYG-01]` adds CI guard, `#5`–`#11` labels, `main` protection | `Partial` *(`CODE_OF_CONDUCT.md` & `#30` scrubbed; `[FEAT-HYG-01]` CI/labels/protection open)* | `LICENSE`, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `[FEAT-HYG-01]` | `0` private leaks across `125` issues verified; `[FEAT-HYG-01]` labels `#5`–`#11`, enforces regex + `gitleaks` CI check, and locks `main` |

#### `2026-11-25` `dev/FEATURES.md` 59-Capability Rollup (`0` Built / `50` To Build / `9` Intentionally Excluded)

| `dev/FEATURES.md` Section | Capability IDs & Linked Issues | Status Rollup | Boundary / Alignment Note |
| --- | --- | --- | --- |
| **1. Standards, Rules & Lifecycle** | `STD-01` (`#5`), `STD-02` (`#13`), `STD-03` (`#14`), `STD-04` (`#15`), `STD-05` (`#16`), `STD-06` (`#44`), `STD-07` (`#45`), `STD-08` (`[FEAT-HYG-01]`) | `8` To Build (`CODE_OF_CONDUCT.md` & `#30` live-scrubbed) | Declarative `default-rules.yaml` with explicit `N/A` category rules (`STD-02`) and read-only PR check (`STD-06`) |
| **2. Telemetry, Scans & Data Import** | `ING-01` (`#7`), `ING-02` (`#17`), `ING-03` (`#18`), `ING-04` (`#19`), `ING-05` (`#20`), `ING-06` (`#21`), `ING-07` (`#36`), `ING-08` (`#37`), `ING-09` (`#38`), `ING-10` (`#39`), `ING-11` (`[FEAT-ING-10]`) | `11` To Build | Conditional `ETag`/`304`, GraphQL batching, SARIF/SBOM blast radius, `PortfolioSnapshotImportV1`, `STALE DATA` quarantine |
| **3. Security, Privacy & Access Control** | `SEC-01` (`#6`), `SEC-02` (`#25`), `SEC-04` (`#34`), `SEC-05` (`#35`); **`SEC-03`** *(never store secrets/private inventories in Git)* | `4` To Build + `1` Excluded (`SEC-03`) | `v1` locks Argon2id/scrypt + `operator_sessions` (`OIDC` deferred to `v2+`); read-only GitHub token vault + SSRF allowlist |
| **4. Hetzner Readiness, Waivers & Hints** | `HET-01` (`#22`), `HET-02` (`#9`), `HET-04` (`#40`), `HET-05` (`#41`), `REM-01` (`#23`), `REM-05` (`[FEAT-REM-03]`); **`HET-03`** *(no Vercel/tunnels)*, **`REM-02`** (`#24` closed), **`REM-03`** *(no remote writes)*, **`REM-04`** (`#53` closed) | `6` To Build + `4` Excluded (`HET-03`, `REM-02`, `REM-03`, `REM-04`) | `#24` (issue creation) & `#53` (PR blueprints) permanently retired; replaced exclusively by passive copyable hints (`REM-05`) |
| **5. Dashboard UI, Trends & UX** | `UIX-01` (`#8`), `UIX-02` (`#26`), `UIX-03` (`#30` scrubbed), `UIX-04` (`#11`), `UIX-05` (`#32`), `UIX-06` (`#55`), `UIX-07` (`[FEAT-UI-01]`), `UIX-08` (`[FEAT-EVT-01]`) | `8` To Build | `UIX-01`/`UIX-07` implement `VG-01` (`<= 5 min` triage); `UIX-04`/`UIX-08` gated behind `DIR-01`–`DIR-07` |
| **6. Notifications, Reports & CLI/API** | `OPS-01` (`#27`), `OPS-02` (`#28`), `OPS-03` (`#29`), `OPS-04` (`#54`); **`OPS-05`** (`#52` closed — no sprint/token forecasting), **`OPS-06`** *(no commercial billing)* | `4` To Build + `2` Excluded (`OPS-05`, `OPS-06`) | Read-only `standardsctl` CLI, formula-safe CSV/JSON/MD/PDF exports, weekly Fleet Delta Digest (`OPS-04`) |
| **7. QA, Tests & Open-Source Hygiene** | `QAL-01` (`#10`), `QAL-02` (`#42`), `QAL-03` (`#43`) | `3` To Build | Automated 4-Pillar CI self-check (`eslint`, `semgrep`, `gitleaks`, `trivy`, `axe-core` WCAG 2.2 AA, `<= 250 KB` JS) |
| **8. Passive Docs-Drift & Fleet Topology** | `AGT-03` (`#48`), `AGT-04` (`#49`), `INT-01` (`#50`), `INT-02` (`#51`); **`AGT-01`** (`#46` closed), **`AGT-02`** (`#47` closed) | `4` To Build + `2` Excluded (`AGT-01`, `AGT-02`) | Coding-agent readiness (`#46`) & execution queues (`#47`) retired; passive docs/config drift & dependency DAG retained |
| **9. Foundation & SQLite WAL Storage** | `ARC-01` (`#31`), `DAT-01` (`#33`) | `2` To Build | TypeScript monorepo (`Node 22 + Fastify 5 + better-sqlite3 + React 19 + Zod` provisional default) + `0001_init.sql` (`10` tables, `6` indexes) |

### 4.3 Safety, Fail-Closed Controls, Governance & Autonomy Gates

1. **Fail-Closed Startup Guard:** If `AAA_ENV=production` and any security prerequisite (`AAA_SESSION_SECRET` entropy, `AAA_OPERATOR_PASSWORD_HASH`, non-root runtime check) fails, the server logs a structured error and exits immediately (`exit 1`) rather than booting degraded or unauthenticated.
2. **Public-Data Isolation Enforcement:**
   - `.gitignore` permanently blocks `.env*`, `*.db`, `*.sqlite*`, `runtime/`, `targets.yaml`, `targets.json`, and `snapshots/`.
   - Automated CI pre-commit/PR check runs `gitleaks` plus a regex sanitization guard confirming zero private repo names, raw IPv4 literals, personal email literals, or forbidden token prefixes appear in tracked source/test files.
3. **Ingestion Emergency Kill-Switch & Rate-Limit Circuit Breaker:**
   - Environment flag `AAA_INGESTION_PAUSED=true` (or operator UI toggle `"Pause Background Sync"`) halts all GitHub polling immediately while keeping cached dashboard reads online (`HTTP 423` on manual trigger).
   - Circuit breaker automatically opens for `60` minutes if `X-RateLimit-Remaining <= 150` or secondary rate-limit `403`/`429` occurs twice consecutively.
4. **Outbound Network Allowlist:** Collector HTTP client rejects redirects or base URLs pointing outside `https://api.github.com` (unless an explicit operator-configured GitHub Enterprise host is set in runtime env), eliminating SSRF risk from malformed target entries.
5. **Read-Only Non-Mutation Guarantee:** No API endpoint, background job, CLI flag, or future read-only MCP tool in `AAA` implements `git push`, `POST /repos/.../issues`, `POST /repos/.../pulls`, `PATCH /repos/...`, or any write operation to external GitHub repositories.
6. **Staleness Transparency Guard:** If any repository's last successful ingestion exceeds `2x` the configured sync interval (e.g., more than `2` hours old), the UI displays an unmistakable warning badge (`STALE DATA — Last synced Xh ago`) so stale green scores never mislead operators.

---

## 5. Technical Architecture & Coding-Agent Implementation Blueprint

### 5.1 System Architecture, Provisional Stack & Deployment Topology

Because `AAA` currently stands at `0` LOC (`HEAD c5cec63`), no runtime stack is committed to Git yet. **Formal stack ratification via `docs/adr/0001-runtime-stack.md` is the first mandatory task of `#5 [S0-01]` (`DIR-01`).** To give coding agents an unambiguous implementation target while respecting Hetzner cost-frugality (`<= 256 MB` RAM), SQLite WAL persistence (`#7`), Playwright E2E compatibility (`#10`), external contributor ergonomics, and Gate 3 readiness (`#11`), the **Provisional Primary Default Stack (Pending `#5` `ADR-0001` Ratification)** is a **Unified TypeScript Monorepo**:

- **Runtime & Backend API (`Provisional Default`):** `Node.js 22 LTS` + `Fastify 5` (typed REST + native SSE streaming, low memory footprint, schema validation) + `Zod` (shared contracts between server, worker, and frontend).
- **Database Engine:** Embedded `SQLite 3` via `better-sqlite3` (synchronous C-level bindings ideal for `<= 10ms` WAL queries without external DB container fees) + versioned `.sql` migration runner.
- **GitHub & Ingestion Clients:** Native `fetch` / `@octokit/rest` (REST with `ETag` store) + `@octokit/graphql` (batched ProjectV2 queries) running on a lightweight in-process `setInterval` / `node-cron` worker queue with bounded concurrency (zero Redis/RabbitMQ dependency).
- **Frontend UI (`Provisional Default`):** `React 19` + `TypeScript` + `Vite` SPA (served directly as static immutable assets by `Fastify` behind `Caddy`, completely decoupled from Vercel/serverless lock-in) + lightweight semantic CSS / Tailwind CSS + `lucide-react` icons.
- **Reverse Proxy & Hetzner Edge:** `Caddy 2` inside Docker Compose on Hetzner EU (automatic Let's Encrypt TLS, HTTP/3 QUIC for `#11 [SPEED-01]`, strict security headers).

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
|  |      AAA Container (Provisional: Node.js 22 + Fastify 5)              |  |
|  |                                                                       |  |
|  |  +-------------------+   +-------------------+   +-----------------+  |  |
|  |  | v1 Auth & CSRF    |   | REST + SSE API    |   | Snapshot Import |  |  |
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

*ADR-0001 Alternative Backend Note:* If the maintainer selects a `Go` backend (`chi` + `modernc.org/sqlite`) during `#5 [S0-01]` `ADR-0001`, the Go server cleanly replaces `apps/server/` (and marks `p1_go` Applicable instead of `N/A` in §5.5) while preserving the **exact same** SQLite schema (§5.3), HTTP/SSE contracts (§5.4), and `apps/web/` React/Playwright frontend.

### 5.2 Repository Structure & Provisional Module Map

Current tracked repository (`14` files as of `2026-11-26` `HEAD c5cec63`) vs target provisional monorepo blueprint (paths under `apps/server/` and `packages/schema/` reflect the provisional Node.js 22 default pending `#5` `ADR-0001`):

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
|   |-- FEATURES.md                     # [EXISTING] 59-capability tracker (2026-11-25 aligned)
|   `-- TEST-RESULTS.md                 # [EXISTING] Test & CI evidence log
|-- docs/
|   |-- MASTER_PLAN.md                  # [EXISTING] Canonical Master Spec (this document)
|   |-- HETZNER_DEPLOY.md               # [PLANNED DIR-06] Cutover, backup & rollback guide
|   `-- adr/
|       `-- 0001-runtime-stack.md       # [PLANNED DIR-01] Ratifies Node 22 default or Go swap
|-- packages/                           # [PROVISIONAL DIR-01 — pending ADR-0001]
|   `-- schema/                         # Shared Zod contracts & rule catalog
|       |-- package.json
|       |-- rules/default-rules.yaml      # Generic declarative engineering standards rules
|       `-- src/
|           |-- index.ts
|           |-- standards.ts              # Rule, Evaluation, Score schemas
|           |-- snapshot.ts               # PortfolioSnapshotImportV1 (21-layer + worktree)
|           `-- fixtures/synthetic.ts     # 100% synthetic demo repos for dev & E2E
|-- apps/
|   |-- server/                         # [PROVISIONAL DIR-01..04 — Fastify 5 + SQLite WAL]
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
|   |   |   |   |-- session.ts          # Argon2id verify, HttpOnly cookies, CSRF (v1)
|   |   |   |   `-- middleware.ts       # Auth + IP rate-limit guards
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
|   `-- web/                            # [PLANNED DIR-05] React 19 + Vite + TypeScript UI
|       |-- package.json
|       |-- src/
|       |   |-- App.tsx
|       |   |-- api/client.ts           # Typed fetch wrapper + CSRF + SWR cache (Gate 3)
|       |   |-- pages/                  # LoginPage, DashboardPage, RepoDetailPage, StandardsPage
|       |   `-- components/             # ComplianceBadge, PillarGrid, TrendSparkline, SyncBanner
|       `-- e2e/                        # [PLANNED DIR-07] Playwright + axe-core WCAG 2.2 AA
|-- ops/
|   `-- hetzner/                        # [PLANNED DIR-06]
|       |-- Dockerfile                  # Multi-stage non-root production image (USER 10001)
|       |-- compose.hetzner.yml         # AAA + Caddy + backup sidecar/cron
|       |-- Caddyfile                   # TLS, HTTP/3, HSTS/CSP security headers
|       |-- backup.sh                   # SQLite online .backup + retention + verification
|       `-- targets.example.yaml        # Synthetic example target inventory template
|-- CODE_OF_CONDUCT.md                  # [EXISTING] Sanitized 2026-11-25 (personal email removed)
|-- CONTRIBUTING.md                     # [EXISTING] Contribution workflow & synthetic rule
|-- DEPLOYMENT_TARGET.md                # [EXISTING] Hetzner-only deployment mandate
|-- LICENSE                             # [EXISTING] Apache License 2.0 (verified)
|-- PROJECT_DIRECTION.md                # [EXISTING] 2026-11-25 locked passive read-only direction
|-- README.md                           # [EXISTING] 12-line direction header (expand in DIR-01)
`-- SECURITY.md                         # [EXISTING] Private vulnerability reporting policy
```

### 5.3 Data Schema, Persistence, Secrets & Backup/Erasure

#### Core SQLite DDL (`apps/server/src/db/migrations/0001_init.sql`)

Designed explicitly with `10` tables and `6` covering indexes so dashboard aggregation and drilldown queries remain `<= 10ms` even across `100` repositories and `180` historical daily snapshots (`18,000` snapshot rows for `#11 [SPEED-01]` readiness):

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
  operator_id TEXT NOT NULL,                 -- v1 static operator; v2+ OIDC adds auth_provider/oidc_subject via migration
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
- `CI-002` (`ci`, `high`, weight `15`): Rolling last-`20` default-branch CI pass rate `>= 90%` (`warn` at `70–89%`, `fail` below `70%`).
- `SEC-001` (`security`, `critical`, weight `20`): Zero open `critical` Dependabot advisories (`fail` if `>= 1`).
- `SEC-002` (`security`, `high`, weight `10`): Zero open `high` Dependabot advisories (`warn` at `1–2`, `fail` `>= 3`).
- `SEC-003` (`security`, `medium`, weight `5`): `SECURITY.md` present on default branch and `branch_protection` enabled (`warn` if unprotected).
- `DOC-001` (`docs`, `high`, weight `10`): Valid SPDX `LICENSE` file present (`Apache-2.0` or approved OSI license).
- `DOC-002` (`docs`, `medium`, weight `10`): Non-stub `README.md` (`>= 500` bytes), `CONTRIBUTING.md`, and `docs/MASTER_PLAN.md` present.
- `DOC-003` (`docs`, `low`, weight `5`): `dev/FEATURES.md` and `dev/TEST-RESULTS.md` present with non-empty verification evidence.
- `DEP-001` (`deployment`, `high`, weight `10`, applies to `service` repos; `na` for `library`/`cli`/`spec`): `DEPLOYMENT_TARGET.md` present and strictly specifies Hetzner / approved local tooling; **zero** `vercel.json` or `.vercel/` directories (`critical fail` if Vercel drift detected).
- `RDM-001` (`roadmap`, `low`, weight `5`): Structured milestone/stage issues (`[S*-01]`) carry non-empty GitHub labels (`warn` if `unlabeled_roadmap_issues >= 1`).

#### Secrets, Backup & Data Retention Policy

- **Secrets Isolation:** `GITHUB_TOKEN` (or GitHub App `APP_ID` + `PRIVATE_KEY_PEM`), `AAA_SESSION_SECRET`, `AAA_OPERATOR_PASSWORD_HASH`, and `AAA_SNAPSHOT_IMPORT_TOKEN_HASH` live exclusively in `/run/secrets/` or `0600` runtime `.env` on Hetzner. They are **never** persisted inside `aaa.sqlite`.
- **Automated Backup & Restore:** `ops/hetzner/backup.sh` runs nightly via systemd timer or container cron, invoking `sqlite3 /data/aaa.sqlite ".backup '/backups/aaa-$(date -u +%F).sqlite'"`, compressing with `zstd`, encrypting via `age` or `restic` to off-box storage, pruning local backups older than `14` days (remote older than `30` days), and verifying integrity via `PRAGMA integrity_check;`.
- **Retention & Erasure:** Raw `sync_runs` and `audit_events` older than `180` days are automatically vacuumed; expired `operator_sessions` are purged hourly. Deleting a repository from runtime `targets.yaml` and executing `DELETE /api/v1/repos/{owner}/{name}` cascades across all snapshots, advisories, and evaluations cleanly.

### 5.4 API, MCP, CLI & External Connector Contracts

#### HTTP REST & SSE API Contract (`v1` Argon2id; OIDC Deferred to `v2+`)

All endpoints under `/api/v1/*` (except `/api/v1/auth/login`) require a valid authenticated session cookie (plus `X-CSRF-Token` header on state mutations) or, exclusively for `/api/v1/imports/snapshot`, a scoped `Authorization: Bearer {AAA_SNAPSHOT_IMPORT_TOKEN}` header.

| Method & Path | Purpose | Request / Query Contract | Response Shape / Status Codes |
| --- | --- | --- | --- |
| `GET /api/healthz` | Unauthenticated liveness probe for Caddy/Docker | None | `200 {"status":"ok","db":"ok"}` (zero sensitive details) |
| `POST /api/v1/auth/login` | Authenticate `v1` operator | `{"username":"operator","password":"..."}` | `200 {"operator":"...","csrfToken":"..."}` + `Set-Cookie`; `401` invalid; `429` rate-limited |
| `POST /api/v1/auth/logout` | Destroy current session | `X-CSRF-Token` | `204 No Content` |
| `GET /api/v1/auth/me` | Verify active operator session | Session cookie | `200 {"authenticated":true,"operator":"...","csrfToken":"..."}` |
| `GET /api/v1/dashboard/summary` | KPI strip, score histogram, sync freshness banner | `?category=&tier=` | `200 {"totalRepos":N,"avgScore":N,"criticalAlerts":N,"failingCi":N,"vercelDrift":N,"staleRepos":N,"lastSyncRun":{...}}` |
| `GET /api/v1/repos` | Filterable portfolio matrix table | `?tier=red\|amber\|green&category=&q=&sort=score\|advisories\|name` | `200 {"items":[RepoSummary],"total":N}` |
| `GET /api/v1/repos/:owner/:name` | Full per-repo drilldown, rule evals, CI, CVEs, 4-pillar grid | `?days=30` | `200 {"repo":{...},"latestSnapshot":{...},"evaluations":[...],"ciRuns":[...],"advisories":[...],"projectItems":[...],"fourPillar":{...},"history":[...]}` |
| `DELETE /api/v1/repos/:owner/:name` | Cascade erase removed target repo | `X-CSRF-Token` | `204 No Content` (cascades snapshots, evaluations, advisories) |
| `POST /api/v1/sync/run` | Trigger manual read-only ingestion sweep | `{"repoSlugs":["optional-subset"]}` + `X-CSRF-Token` | `202 {"syncRunId":123,"status":"running"}`; `409` running; `423` `AAA_INGESTION_PAUSED` |
| `POST /api/v1/imports/snapshot` | External 4-pillar & local worktree JSON snapshot import | `PortfolioSnapshotImportV1` JSON payload | `200 {"imported":N,"updatedSlugs":[...]}`; `400` Zod schema error; `401`/`403` auth failure |
| `GET /api/v1/standards/rules` | Inspect active declarative rule catalog | None | `200 {"schemaVersion":"1.0","rules":[...]}` |
| `GET /api/v1/events/stream` | **[Gate 3 `#11`]** Real-time SSE progress & score updates | `Accept: text/event-stream` | Events: `sync_started`, `repo_updated`, `sync_completed`, `heartbeat` (`30s`) |

*(Deferred `v2+` Auth Contract Note: `GET /api/v1/auth/oidc/login` and `GET /api/v1/auth/oidc/callback` are reserved for `v2+` OIDC PKCE federation and remain unmounted in `v1`.)*

#### External JSON Import Schema (`PortfolioSnapshotImportV1`)

Reconciles external CLI/audit Risk #2 cleanly so external audit pipelines feed local-worktree and `21`-layer verification matrices into `AAA` without duplicating scanners:

```json
{
  "schema_version": "1.0",
  "source_tool": "portfolio-audit-cli",
  "generated_at": "2026-11-26T12:00:00Z",
  "repositories": [
    {
      "slug": "example-org/example-repo-a",
      "worktree_state": "clean",
      "four_pillar": {
        "needed_layers": 21,
        "confirmed_layers": 17,
        "na_layers": 4,
        "p1_summary": "4/4 Applicable (2 N/A)",
        "p2_summary": "3/3 Confirmed",
        "p3_summary": "4/4 Applicable (1 N/A)",
        "p4_summary": "6/6 Applicable (1 N/A)",
        "cells": {
          "p1_go": "N/A — Node.js 22 / TypeScript service",
          "p1_python": "N/A — No Python services",
          "p1_repo": "Yes — Confirmed",
          "p3_ai_routing": "N/A — Deterministic non-AI utility",
          "p4_secrets": "Yes — gitleaks CI green",
          "p4_ai_safety": "N/A — No generative AI execution"
        }
      }
    }
  ]
}
```

#### CLI & Optional Read-Only MCP Interface

- **CLI (`standardsctl` / `aaa-cli`):** `npm run sync:once` (deterministic headless sync), `npm run seed:synthetic` (populate synthetic demo portfolio), `npm run import:snapshot -- --file ./sample.json` (validate & import JSON snapshot), and `standardsctl check-pr` (`#44`, read-only pre-merge diff audit).
- **Optional Read-Only MCP Server (Future Extension):** If exposed for local developer agents behind an authenticated operator token, exposes strictly read-only SQLite-backed tools: `get_portfolio_summary()`, `get_repo_compliance(slug)`, and `list_failing_rules(severity)`. Zero mutating tools.

### 5.5 Hosting Target, CI/CD Packaging & 21-Layer 4-Pillar Verification Matrix (Including `N/A` Mapping)

- **Production Hetzner EU Packaging (`ops/hetzner/`):**
  - Multi-stage `Dockerfile`: Stage 1 compiles TypeScript packages and Vite bundle (`node:22-alpine`), Stage 2 runs minimal production runtime under non-root UID `10001` with `NODE_ENV=production`, no devDependencies, `HEALTHCHECK` hitting `127.0.0.1:8080/api/healthz`.
  - `compose.hetzner.yml`: Binds app container internally to a private Docker bridge network; only `Caddy 2` exposes ports `80`/`443` (TCP + UDP for HTTP/3 QUIC). Mounts persistent volume `/data` (`aaa.sqlite` + read-only mounted `targets.yaml`).
  - `Caddyfile`: Enforces automatic TLS, HTTP/3, HSTS (`max-age=31536000`), strict CSP (`default-src 'self'; frame-ancestors 'none'`), `X-Content-Type-Options: nosniff`, and gzip/zstd compression.
- **Complete 21-Layer 4-Pillar Verification Matrix (`detailed_repo_status.json` Alignment & `N/A` Mapping):**
  Under the `2026-11-26` DRS snapshot (`0 LOC`), all `21` matrix layers read `No — Not Built Yet` (`0/21` confirmed) because `ADR-0001` has not yet ratified the stack. Once `#5 [S0-01]` ratifies the **Provisional Node.js 22 + Fastify 5 + SQLite WAL + React 19 + Caddy 2** deterministic non-AI stack, **`17` layers are Applicable and `4` layers are explicitly `N/A`** (`18` Applicable / `3` `N/A` if `ADR-0001` selects the optional `Go` backend).

| Layer Key | Pillar | `2026-11-26` DRS Status | Provisional Node.js 22 Stack Applicability | Optional `Go` Swap (`ADR-0001`) | Target Verification Tool & Pass Gate |
| --- | --- | --- | :---: | :---: | --- |
| `p1_go` | P1 Code & Hygiene | `No — Not Built Yet` | **`N/A`** *(TypeScript/Node.js default)* | **Applicable** | `gofmt`, `go vet`, `golangci-lint`, `go test -race` *(N/A unless Go chosen)* |
| `p1_frontend` | P1 Code & Hygiene | `No — Not Built Yet` | **Applicable** | **Applicable** | `eslint`, `tsc --noEmit`, `prettier --check`, `stylelint`, `knip` (`DIR-01`, `DIR-05`) |
| `p1_python` | P1 Code & Hygiene | `No — Not Built Yet` | **`N/A`** *(Zero Python services in `AAA`)* | **`N/A`** | Explicitly excluded (`0` `.py` runtime modules) |
| `p1_database` | P1 Code & Hygiene | `No — Not Built Yet` | **Applicable** | **Applicable** | Transactional `0001_init.sql` dry-run + `PRAGMA integrity_check` (`DIR-02`) |
| `p1_scripts` | P1 Code & Hygiene | `No — Not Built Yet` | **Applicable** | **Applicable** | `actionlint`, `shellcheck` on `ops/hetzner/backup.sh`, `hadolint` on `Dockerfile` (`DIR-01`, `DIR-06`) |
| `p1_repo` | P1 Code & Hygiene | `No — Not Built Yet` | **Applicable** | **Applicable** | Doc-link check, `#5`–`#11` labeled, `main` protection, Dependabot active (`DIR-00`, `DIR-01`) |
| `p2_backend` | P2 Performance & Load | `No — Not Built Yet` | **Applicable** | **Applicable** | `k6` / Vitest API latency smoke (`p95 <= 50ms` v1; SSE stream in Gate 3 `DIR-08`) |
| `p2_browser` | P2 Performance & Load | `No — Not Built Yet` | **Applicable** | **Applicable** | Vite JS bundle `<= 250 KB` gzipped + Playwright Cold-Load / LCP (`DIR-05`, `DIR-07`, `DIR-08`) |
| `p2_database` | P2 Performance & Load | `No — Not Built Yet` | **Applicable** | **Applicable** | `perf.bench.ts` SQLite WAL covering-index benchmark: `p95 <= 10ms` over `18,000` rows (`DIR-08`) |
| `p3_hardware` | P3 Resource & Ops | `No — Not Built Yet` | **Applicable** | **Applicable** | Docker `50`-repo synthetic load profile (`<= 256 MB` steady-state RAM, `DIR-06`) |
| `p3_containers` | P3 Resource & Ops | `No — Not Built Yet` | **Applicable** | **Applicable** | Non-root `UID 10001`, read-only rootfs where writable `/data` isolated, `/api/healthz` (`DIR-06`) |
| `p3_code` | P3 Resource & Ops | `No — Not Built Yet` | **Applicable** | **Applicable** | Bounded worker concurrency (`3`), `ETag` store cap, memory stability over `1h` soak (`DIR-03`, `DIR-06`) |
| `p3_monitoring` | P3 Resource & Ops | `No — Not Built Yet` | **Applicable** | **Applicable** | Internal Prometheus `/metrics` scrape + structured JSON logs + backup restore drill (`DIR-06`) |
| `p3_ai_routing` | P3 Resource & Ops | `No — Not Built Yet` | **`N/A`** *(Deterministic non-AI utility)* | **`N/A`** | Zero LLM calls (`EUR 0.00/mo` ceiling); explicitly `N/A` in `PortfolioSnapshotImportV1` |
| `p4_code` | P4 Security & Safety | `No — Not Built Yet` | **Applicable** | **Applicable** | `semgrep` SAST + CSRF/auth/SSRF negative-path integration tests (`DIR-02`, `DIR-03`) |
| `p4_secrets` | P4 Security & Safety | `No — Not Built Yet` | **Applicable** | **Applicable** | `gitleaks` + public-repo sanitization regex check on every PR (`DIR-00`, `DIR-01`) |
| `p4_deps` | P4 Security & Safety | `No — Not Built Yet` | **Applicable** | **Applicable** | `npm audit --audit-level=high` + `osv-scanner` + `syft` SBOM (`0` critical/high CVEs, `DIR-01`) |
| `p4_containers` | P4 Security & Safety | `No — Not Built Yet` | **Applicable** | **Applicable** | `Trivy` image scan + `Dockle` (`0` critical/high OS CVEs, `DIR-06`) |
| `p4_web` | P4 Security & Safety | `No — Not Built Yet` | **Applicable** | **Applicable** | CSP/HSTS/XFO header tests + Playwright `@axe-core/playwright` WCAG 2.2 AA (`DIR-02`, `DIR-07`) |
| `p4_ai_safety` | P4 Security & Safety | `No — Not Built Yet` | **`N/A`** *(Zero generative AI execution)* | **`N/A`** | No LLM prompts/agents executed; future optional read-only MCP strictly deterministic SQL queries |
| `p4_licenses` | P4 Security & Safety | `No — Not Built Yet` | **Applicable** | **Applicable** | `license-checker` verifying `Apache-2.0` compatibility across all runtime dependencies (`DIR-01`) |

---

## 6. Build Reality (`2026-11-26`), Implementation Directives & Binary Release Gates

### 6.1 Honest Build Reality Inventory (`2026-11-26`)

Synced to `detailed_repo_status.json` and `live_commits_20261126.json` at `HEAD c5cec63`:

- **Built & Verified (`14` tracked files, `0` source/test LOC):**
  - Governance & Legal: `LICENSE` (verified **`Apache-2.0`**, catching DRS prose erroneously claiming `"MIT"`), `SECURITY.md` (`#1`, `8fb2e0f`), `CONTRIBUTING.md` (`#2`, `35d2371`), `CODE_OF_CONDUCT.md` (personal email scrubbed `2026-11-25`).
  - Operational Direction & Deployment Policy: `DEPLOYMENT_TARGET.md` (`ca41c87`, PR `#3` `084a164` removing Vercel), `PROJECT_DIRECTION.md` (`2026-11-25` alignment `c5cec63`), `README.md` (`12`-line direction header since `3762c49`, catching DRS prose erroneously claiming `"single-line README stub"`), `docs/MASTER_PLAN.md` (`5319714` -> `c5cec63`).
  - Issue/PR Scaffolding & Evidence Logs: `.github/ISSUE_TEMPLATE/bug_report.yml`, `.github/ISSUE_TEMPLATE/feature_request.yml`, `.github/dependabot.yml`, `.github/pull_request_template.md`, `dev/FEATURES.md` (`8086bf5` -> `c5cec63`), `dev/TEST-RESULTS.md` (`559853d`).
- **Built Local / Unverified Live:** `None` (`0` LOC).
- **Partial / Mocked:** `None` (`0` runtime features built; backlog aligned `2026-11-25` across `118` DRS open issues / `121` GitHub REST `open_issues_count`, `5` closed superseded `#24`, `#46`, `#47`, `#52`, `#53`, `1` open PR, `3` branches; `CODE_OF_CONDUCT.md:19` and issue `#30` live-sanitized with `0` leaks across `125` issues).
- **Missing (`100%` of Software Implementation & CI):**
  - Stack ADR (`docs/adr/0001-runtime-stack.md`), application manifest (`package.json`), lockfile, and workspace configs.
  - SQLite WAL database schema (`0/10` tables), migration runner, and `default-rules.yaml`.
  - Fail-closed `v1` Argon2id/scrypt operator authentication, CSRF/session store, security headers, and read-only GitHub token handler.
  - GitHub REST/GraphQL/ProjectV2 collectors (`#7`, `[FEAT-ING-10]`), Standards Evaluator engine, and `PortfolioSnapshotImportV1` endpoint.
  - React 19 Compliance Scoreboard UI (`#8`, `[FEAT-UI-01]`), timed `VG-01` exception workflow, copyable passive remediation hints (`[FEAT-REM-03]`), and WCAG 2.2 AA components.
  - Hetzner Docker/Caddy packaging, backup/restore automation, and cutover runbook (`#9`).
  - CI workflows (`.github/workflows/ci.yml`), automated tests, synthetic fixture gates, and `17` applicable 4-Pillar checks (`0/21` confirmed; `No CI`).
- **Immediate Repository Hygiene & Governance Gaps (`[FEAT-HYG-01]`):**
  - `branch_protection` on `main` is `Unprotected`.
  - Legacy umbrella issues `#5`–`#11` still carry `labels: []` (`roadmap_s_open: null`).
  - Automated CI `gitleaks` + public-repo regex sanitization enforcement stays queued in `[FEAT-HYG-01]` (`DIR-00`).

### 6.2 Implementation Directives (`DIR-00`–`DIR-08` — Coding-Agent Execution Sequence)

Execute directives strictly in priority order. Never proceed to `DIR-08` until `DIR-00` through `DIR-07` pass verification. Module paths under `packages/schema/` and `apps/server/` reflect the **Provisional Primary Default Stack (`Node.js 22 + Fastify 5 + SQLite WAL + React 19 + Caddy 2`)** pending `#5 [S0-01]` `ADR-0001` ratification (or equivalent `apps/server/` Go modules if ADR-0001 chooses Go). Every test fixture and screenshot MUST use 100% synthetic repository names (`example-org/example-repo-a`, `example-org/portfolio-service-1`).

#### `DIR-00`: Immediate Repository Governance & Sanitization Hygiene (`[FEAT-HYG-01]`, `STD-08`)
- **Target:** Repository settings + `CODE_OF_CONDUCT.md` + GitHub issues `#5`–`#11` + `.github/workflows/ci.yml` + `docs/MASTER_PLAN.md`.
- **Implementation:**
  1. Confirm and maintain `docs/MASTER_PLAN.md`, `PROJECT_DIRECTION.md`, `dev/FEATURES.md`, `CODE_OF_CONDUCT.md` (scrubbed `2026-11-25`), and all `125` issues (incl. scrubbed `#30`) strictly free of private repository names, internal server IP addresses, private Drive URLs/IDs, or personal emails.
  2. Apply structured labels (`enhancement`, `P0`/`P1`/`P2`, `domain:*`) to legacy open issues `#5`–`#11`.
  3. Wire automated public-repo sanitization regex verification + `gitleaks` in `.github/workflows/ci.yml` (`[FEAT-HYG-01]`).
  4. Enable GitHub branch protection on `main` requiring PRs and green status checks once `DIR-01` lands CI.
- **Verification:** `gh issue list --json number,labels` shows non-empty labels on `#5`–`#11` and automated `rg` + `gitleaks` checks confirm `0` private-data leaks across tracked files and issues.

#### `DIR-01`: Stack Ratification (`ADR-0001`), Standards Schema & CI Baseline (`#5 [S0-01]`, `#13`, `#31`)
- **Target Files:** `docs/adr/0001-runtime-stack.md`, `README.md`, `package.json`, `packages/schema/*`, `.github/workflows/ci.yml`, `.gitignore`.
- **Implementation:**
  1. Author `docs/adr/0001-runtime-stack.md` formally ratifying `Node.js 22 LTS + Fastify 5 + SQLite WAL + React 19 + Vite + Zod` (or locking the optional `Go` backend swap while recording exact `N/A` 4-Pillar layers from §5.5).
  2. Expand `README.md` with system overview, architecture diagram, synthetic local quickstart (`AAA_DEMO_MODE=true`), security boundary warning, and link to `docs/MASTER_PLAN.md`.
  3. Initialize workspace manifests, strict linting/typechecking, dead-code check (`knip`), and `.gitignore` (blocking `.env*`, `*.sqlite*`, `targets.*`, `runtime/`).
  4. Implement `packages/schema/src/standards.ts`, `snapshot.ts`, `rules/default-rules.yaml`, and deterministic synthetic fixtures (`fixtures/synthetic.ts`).
  5. Wire `.github/workflows/ci.yml` running Pillar 1 & Pillar 4 baseline checks (`eslint`, `tsc --noEmit`, `prettier --check`, `vitest`, `gitleaks`, `osv-scanner`/`npm audit`, `license-checker`, public sanitization regex guard).
- **Verification:** `npm ci && npm run lint && npm run typecheck && npm test` exits `0` cleanly in GitHub Actions.

#### `DIR-02`: Authentication (`v1` Argon2id/scrypt), Fail-Closed Guards, Security Headers & Secret Isolation (`#6 [S1-01]`, `#34`, `#35`)
- **Target Files:** `apps/server/src/config/env.ts`, `apps/server/src/auth/*`, `apps/server/src/plugins/security.ts`, `apps/server/src/db/migrations/0001_init.sql`.
- **Implementation:**
  1. Implement strict `env.ts` Zod validator enforcing fail-closed startup in `production` when `AAA_SESSION_SECRET` (`>= 32B`) or `AAA_OPERATOR_PASSWORD_HASH` is absent *(keeping OIDC deferred cleanly to `v2+`)*.
  2. Implement SQLite WAL client (`better-sqlite3`), transactional migration runner, and full `0001_init.sql` schema (`10` tables, `6` covering indexes).
  3. Build Argon2id/scrypt login handler (`POST /api/v1/auth/login`), IP rate limiting (`5` tries / `15` min), `HttpOnly`/`Secure`/`SameSite=Strict` cookie sessions, CSRF validation middleware, and strict Fastify CSP/HSTS/XFO headers.
  4. Implement runtime `targets.yaml` loader and log/JSON redactor stripping bearer tokens or secrets before serialization.
- **Verification:** Vitest integration tests confirm: (a) prod boot exits `1` on missing secret, (b) unauthenticated `/api/v1/dashboard/summary` returns `401`, (c) CSRF-missing `POST` returns `403`, (d) login lockout activates after `5` bad attempts, and (e) CSP/HSTS/XFO headers exist on responses.

#### `DIR-03`: GitHub REST/GraphQL, CI, Advisory, Deployment Drift & ProjectV2 Ingestion (`#7 [S3-01]`, `[FEAT-ING-10]`, `#17`, `#18`, `#22`, `#36`)
- **Target Files:** `apps/server/src/github/*`, `apps/server/src/engine/evaluator.ts`, `apps/server/src/routes/sync.ts`.
- **Implementation:**
  1. Build GitHub HTTP client supporting `ETag` caching (`304`), `X-RateLimit-Remaining <= 150` circuit breaker, outbound host allowlist (`api.github.com`), and read-only scope check (`0` write scopes).
  2. Implement all `5` collectors (`docs.ts`, `ci.ts`, `security.ts`, `deployment.ts`, `projectv2.ts`) with graceful `403` `insufficient_scope` fallback.
  3. Wire deterministic `evaluator.ts` scoring repositories against `default-rules.yaml` (including `na` category exclusions) and writing atomic snapshots into `repo_snapshots` and `rule_evaluations`.
  4. Implement `sync-runner.ts` with per-repo error quarantine, `AAA_INGESTION_PAUSED` kill-switch, and scheduled + manual `POST /api/v1/sync/run` endpoints.
- **Verification:** Integration suite against a local mock GitHub HTTP/GraphQL server validates `304` caching, circuit-breaker activation, `vercel.json` drift detection, unlabeled `[S*-01]` issue detection, and `100%` deterministic compliance scores.

#### `DIR-04`: External Portfolio Snapshot & 4-Pillar Audit JSON Importer (`#37`, `#19`)
- **Target Files:** `apps/server/src/imports/snapshot.ts`, `apps/server/src/routes/imports.ts`.
- **Implementation:**
  1. Implement `POST /api/v1/imports/snapshot` authenticated via `AAA_SNAPSHOT_IMPORT_TOKEN_HASH` (timing-safe comparison) or operator session + CSRF.
  2. Validate `PortfolioSnapshotImportV1` payloads via Zod (including explicit `na_layers` and `p1_*`–`p4_*` keys), upsert `four_pillar_audits` and `worktree_state`, and preserve independent timestamps from GitHub API syncs.
  3. Add CLI entrypoint `npm run import:snapshot -- --file {path}` for local/CI batch imports.
- **Verification:** Integration test confirms valid synthetic `21`-layer (`17` Applicable / `4` N/A) payload persists and reflects in `/api/v1/repos/{owner}/{name}`, while invalid schemas return `400` and invalid bearer tokens return `401`.

#### `DIR-05`: Standards Compliance Dashboard UI, Per-Repo Drilldown & `VG-01` Triage Flow (`#8 [S5-01]`, `[FEAT-UI-01]`, `[FEAT-REM-03]`, `VG-01`)
- **Target Files:** `apps/web/src/*`, `apps/server/src/routes/dashboard.ts`, `apps/server/src/routes/repos.ts`.
- **Implementation:**
  1. Implement `/api/v1/dashboard/summary`, `/api/v1/repos`, `/api/v1/repos/{owner}/{name}`, `DELETE /api/v1/repos/{owner}/{name}`, and `/api/v1/standards/rules`.
  2. Build responsive, exception-first, keyboard-accessible React UI (`NL`/`EN` toggle `#30`, `AAA_DEMO_MODE=true` badge, `Ctrl/Cmd+K` palette `#55`): Login view, Portfolio KPI strip, `STALE DATA` warning banner, filterable/sortable Compliance Matrix table, and Repository Drilldown page showing rule checklist + **passive copyable remediation hints (`[FEAT-REM-03]`)**, time-boxed waivers (`#23`), CI runs, Dependabot advisories, `21`-layer 4-Pillar grid, and `30`-day trend chart.
  3. **Wire `VG-01` UX Ergonomics:** Ensure the default exception queue surfaces all critical/failing items, hosting drift, and unlabeled issues in `<= 2` clicks without multi-page hunting (`<= 5 min` daily triage target `[Planning Hypothesis (RA)]`).
  4. Serve production Vite static build cleanly from Fastify in production mode (`<= 250 KB` initial JS gzipped).
- **Verification:** `vite build` succeeds cleanly with `0` TypeScript errors, `0` unused exports (`knip`), and JS bundle `<= 250 KB` gzipped.

#### `DIR-06`: Hetzner Production Container, Caddy TLS, Backups & Monitoring (`#9 [S7-01]`, `#40`, `#41`)
- **Target Files:** `ops/hetzner/Dockerfile`, `ops/hetzner/compose.hetzner.yml`, `ops/hetzner/Caddyfile`, `ops/hetzner/backup.sh`, `ops/hetzner/targets.example.yaml`, `docs/HETZNER_DEPLOY.md`.
- **Implementation:**
  1. Author multi-stage non-root `Dockerfile` (`USER 10001`), `compose.hetzner.yml` (verifying `<= 256 MB` steady-state RAM), and `Caddyfile` with TLS + security headers.
  2. Implement `ops/hetzner/backup.sh` using SQLite online `.backup`, `PRAGMA integrity_check`, and off-box encrypted upload hook + automated restore verification script.
  3. Expose sanitized Prometheus `/metrics` (protected behind internal docker network or auth token).
  4. Write complete `docs/HETZNER_DEPLOY.md` covering architecture, DNS/TLS, secret injection, verified Hetzner EU monthly tariff (`EUR 0/mo` colocated or `<= EUR 10–20/mo` dedicated ceiling), migration safety, backup restore drills, and rollback procedure per `DEPLOYMENT_TARGET.md`.
- **Verification:** `docker build` + `Trivy` scan passes `0` critical/high OS CVEs; `docker compose -f ops/hetzner/compose.hetzner.yml up -d` passes `/api/healthz`; backup/restore drill restores synthetic DB cleanly with SHA-256 + `PRAGMA integrity_check`; `dev/TEST-RESULTS.md` updated.

#### `DIR-07`: Playwright E2E, WCAG 2.2 AA & Timed `VG-01` Verification (`#10 [S8-01]`, `#43`, `VG-01`)
- **Target Files:** `apps/web/e2e/*.spec.ts`, `.github/workflows/ci.yml`.
- **Implementation:**
  1. Write Playwright E2E suite booting `AAA` in `AAA_ENV=synthetic` mode against seeded synthetic repositories: login flow, exception-first filtering/sorting, manual sync trigger against mock GitHub server, per-repo drilldown + copyable remediation hint copy check, waiver flow, and logout.
  2. **Execute Timed `VG-01` Triage Verification:** Automate an operator triage scenario across a `25`-repo synthetic portfolio (locating critical CVE, CI failure, `vercel.json` drift, and unlabeled issue), asserting end-to-end scripted operator triage completion well below the `5`-minute daily budget (`VG-01`).
  3. Integrate `@axe-core/playwright` across every page (`login`, `dashboard`, `repo detail`, `standards`) asserting `0` WCAG 2.2 AA critical/serious violations at desktop (`1440x900`) and mobile (`375x812`).
- **Verification:** `npx playwright test` passes `100%` in CI; update `dev/FEATURES.md` checkboxes and `dev/TEST-RESULTS.md` with exact commit SHA and workflow evidence.

#### `DIR-08`: Gate 3 Optimization — Zero-Wait SWR, SSE Live Push, Sub-10ms Queries & HTTP/3 (`#11 [SPEED-01]`, `[FEAT-EVT-01]`)
- **Target Files:** `apps/server/src/events/sse.ts`, `apps/server/tests/perf.bench.ts`, `apps/web/src/api/client.ts`, `ops/hetzner/Caddyfile`, `.github/workflows/ci.yml`.
- **Implementation (ONLY after `DIR-01`–`DIR-07` pass):**
  1. Implement authenticated `GET /api/v1/events/stream` SSE emitter broadcasting incremental `repo_updated` and `sync_completed` events.
  2. Add client-side stale-while-revalidate caching + SSE reconnection hook in `apps/web`.
  3. Benchmark SQLite read queries against a `100`-repo x `180`-day synthetic dataset (`18,000` snapshot rows), verifying covering indexes keep `p95 <= 10ms`.
  4. Verify `Caddyfile` HTTP/3 (`443/udp`) listener and add CI latency regression check (`perf.bench.ts`).
- **Verification:** `npm run bench:db` reports `p95 <= 10ms`; Playwright verifies SSE updates UI live without page reload when sync fires.

### 6.3 Non-Overridable Binary Go/No-Go Release Gates (`G0`–`G6`)

| Gate | Quantitative Pass Criterion | Blocking Behavior |
| --- | --- | --- |
| **`G0` Public Sanitization & Repo Hygiene (`DIR-00`)** | **`0`** `gitleaks` / regex private-data hits across code, tests, docs, and all **`125+`** GitHub issues (`CODE_OF_CONDUCT.md` & `#30` verified clean); issues **`#5`–`#11`** non-empty labeled; **`main`** branch protection enabled. | **HARD BLOCK:** Zero feature PRs or Hetzner deployment permitted until public sanitization and `main` protection pass. |
| **`G1` Stack Ratification & CI Baseline (`DIR-01`)** | `docs/adr/0001-runtime-stack.md` committed; `.github/workflows/ci.yml` passes **`100%`** (`eslint`, `tsc`, `prettier`, `vitest`, `npm audit`/`osv-scanner`, `license-checker` `Apache-2.0`); **`0`** HIGH/CRITICAL dependency CVEs. | **HARD BLOCK:** Blocks all downstream feature merges until CI checks run green on every PR. |
| **`G2` Fail-Closed Auth & Secret Isolation (`DIR-02`)** | `AAA_ENV=production` exits **`1`** on missing `AAA_SESSION_SECRET` (`>= 32B`) or `AAA_OPERATOR_PASSWORD_HASH`; unauth `/api/v1/*` returns **`401`**; missing CSRF returns **`403`**; lockout triggers after **`5`** bad logins; **`0`** plaintext secrets in SQLite/logs. | **HARD BLOCK:** Blocks staging or Hetzner boot if any auth, CSRF, rate-limit, or secret-redaction test fails. |
| **`G3` Read-Only Ingestion & Determinism (`DIR-03`, `DIR-04`)** | Mock GitHub integration suite proves **`304`** `ETag` hit handling, circuit breaker at `X-RateLimit-Remaining <= 150`, SSRF outbound block, **`0`** write scopes/mutations, and **`100%`** deterministic scoring + `PortfolioSnapshotImportV1` persistence. | **HARD BLOCK:** Blocks UI integration and live portfolio target mounting until zero-mutation invariants pass. |
| **`G4` UI, WCAG 2.2 AA & `VG-01` Triage (`DIR-05`, `DIR-07`)** | **`100%`** Playwright E2E passes on `1440px` & `375px`; **`0`** `@axe-core/playwright` critical/serious WCAG 2.2 AA violations; initial JS gzipped **`<= 250 KB`**; timed **`VG-01`** synthetic triage finishes in **`<= 5 min`** (`<= 2` clicks). | **HARD BLOCK:** Blocks production Hetzner cutover and Gate 3 speed optimization (`DIR-08`). |
| **`G5` Hetzner EU Packaging, DR & Cost Cap (`DIR-06`)** | **`17/17`** applicable 4-Pillar layers green (`4` explicitly `N/A`); **`0`** CRITICAL/HIGH `Trivy` container CVEs; non-root `UID 10001`; `backup.sh` + restore drill SHA-256/`PRAGMA integrity_check` passes; steady-state RAM **`<= 256 MB`**; **`EUR 0.00/mo` LLM** and **`EUR 0/mo` colocated or `<= EUR 10–20/mo` dedicated VPS**. | **HARD BLOCK:** Automatic rollback/abort of Hetzner cutover if DR verification, CVE gate, RAM cap, or EUR ceiling fails. |
| **`G6` Gate 3 Zero-Wait Speed & SSE (`DIR-08`)** | `perf.bench.ts` reports **`p95 <= 10ms`** over **`18,000`** synthetic snapshots (`100` repos x `180` days); Playwright confirms live SSE `repo_updated` UI refresh without reload; `Caddy` HTTP/3 (`443/udp`) verified. | **HARD BLOCK (Gate 3):** Keeps `v1` on clean synchronous REST polling until `p95 <= 10ms` and live SSE pass CI. |

---

## 7. Risk Register, Assumption Register (`VF/RA/SR/OQ`) & Portfolio Cross-References

### 7.1 Risk Register

| Category | Risk & Observed Evidence (`2026-11-26`) | Severity | Mitigation & Hard Gate |
| --- | --- | :---: | --- |
| **Execution / Scope** | **Premature Optimization Trap:** Issue `#11 [SPEED-01]` specifies SWR, SSE, `<= 10ms` DB queries, HTTP/3, and CI latency gates while `AAA` still has `0` LOC (`HEAD c5cec63`). | `High` | **Hard Gate (`G6`):** Sequenced strictly into Gate 3 (`DIR-08`), only after `DIR-00`–`DIR-07` (`G0`–`G5`) establish schema, auth, ingestion, UI, Hetzner deployment, and Playwright/WCAG verification. |
| **Security / Privacy** | **Public-Repo Leakage:** `AAA` is a public `Apache-2.0` repo with external contributor access. While `CODE_OF_CONDUCT.md:19` and issue `#30` were scrubbed `2026-11-25` (`0` leaks across `125` issues), future PRs or fixtures could leak secrets or private targets. | `Critical` | **Hard Gate (`G0`):** `.gitignore` blocks runtime configs/DBs; CI runs `gitleaks` + public-repo regex guard (`[FEAT-HYG-01]`); all fixtures strictly synthetic (`example-org/*`). |
| **Security / Auth** | **Unauthenticated Exposure or Over-Privileged PAT:** Deploying dashboard on Hetzner without fail-closed auth or granting write/admin GitHub scopes compromises tracked private repositories. | `Critical` | **Hard Gate (`G2`):** Prod boot exits `1` if `AAA_SESSION_SECRET` / `AAA_OPERATOR_PASSWORD_HASH` unset (`DIR-02`); OIDC deferred to `v2+`; read-only GitHub scopes only (`#24` & `#53` closed). |
| **Architecture / Process** | **Duplication & Orchestration Scope Creep:** External JSON audits evaluate 4-Pillar readiness and external orchestrators run coding-agent queues; turning `AAA` into an agent dispatcher/sprint tool duplicates work. | `Medium` | **Mitigation:** `PortfolioSnapshotImportV1` adapter (`FEAT-09`, `DIR-04`) ingests external 4-Pillar audits passively while locking out agent orchestration (`#46`, `#47`, `#52` closed `2026-11-25`). |
| **External API** | **GitHub API Rate-Limit Exhaustion:** Polling multi-repository portfolios continuously across metadata, Actions, alerts, issues, and ProjectV2 can trip secondary rate limits. | `Medium` | **Mitigation:** `ETag`/`If-None-Match` conditional caching (`304` zero-cost), GraphQL batching, bounded concurrency (`3`), and automatic circuit breaker at `X-RateLimit-Remaining <= 150`. |
| **Governance / CI** | **Unprotected `main` & Zero Automated Checks:** `branch_protection` is `Unprotected`, `ci_status` is `No CI`, and issues `#5`–`#11` still carry `labels: []` (`roadmap_s_open: null`). | `High` | **Hard Gate (`G0`, `G1`):** `[FEAT-HYG-01]` (`DIR-00`) labels `#5`–`#11` and wires sanitization checks; `DIR-01` wires CI and enables `main` branch protection. |
| **Operational Trust** | **Silent Sync Failures Masking Decay:** Stale green scores mislead operators if background polling fails due to expired tokens or outages. | `Medium` | **Mitigation:** Per-repo `last_sync_status`, persistent `STALE DATA` warning banner whenever age exceeds `2x` sync interval, and `/metrics` sync-failure alerts. |
| **Onboarding** | **External Developer Friction:** `README.md` currently holds only a `12`-line direction header at `0` LOC, giving contributors insufficient architectural guidance. | `Medium` | **Mitigation:** `docs/MASTER_PLAN.md` live at `c5cec63`; land `docs/adr/0001-runtime-stack.md`, `AAA_DEMO_MODE=true` quickstart, and expanded `README.md` in `DIR-01`. |

### 7.2 Assumption & Verification Register (`VF / RA / SR / OQ`)

| Tag | Item / Claim | Classification | Evidence Basis & Verification Path |
| --- | --- | :---: | --- |
| **`VF-01`** | Live `2026-11-26` codebase & DRS state (`HEAD c5cec63`): `Stage 01`, `0%`, `14` files (`6` root `.md`s, `0` source/test LOC), `No CI`, `Unprotected` `main`, `0/21` 4-pillar layers, `118` DRS open issues (`121` GitHub REST `open_issues_count`), `5` closed superseded, `1` open PR, `3` branches, `Apache-2.0` `LICENSE`, `12`-line `README.md` | **Verified Fact (`VF`)** | Directly verified in `detailed_repo_status.json`, `live_commits_20261126.json`, `LICENSE`, and `README.md`; explicitly overrides erroneous DRS `"MIT / 1-line stub / 7 issues"` text (§2.2). |
| **`VF-02`** | `2026-11-25` Locked Scope & Live Public Sanitization: **100% Passive Read-Only Compliance Scoreboard ONLY**, zero GitHub writes/agent orchestration (`#24`, `#46`, `#47`, `#52`, `#53` closed), Hetzner EU target (`DEPLOYMENT_TARGET.md`, PR `#3`), and live scrub of `CODE_OF_CONDUCT.md:19` & public issue `#30` (`0` leaks across `125` issues) | **Verified Fact (`VF`)** | Directly verified in `PROJECT_DIRECTION.md`, `dev/FEATURES.md`, `docs/MASTER_PLAN.md` (`c5cec63`), and live GitHub sanitization audit. |
| **`VF-03`** | `EUR 0.00/mo` variable LLM & SaaS fee ceiling (`v1` deterministic rule engine, embedded SQLite WAL, conditional GitHub `ETag` reads, `v1` Argon2id/scrypt auth) | **Verified Fact (`VF`)** | Architectural invariant enforced in §1.4, §3.4, §4.1, and §5.3–5.5 (`p3_ai_routing` and `p4_ai_safety` marked `N/A`). |
| **`RA-01`** | Hetzner EU fixed infrastructure ceiling: **`EUR 0.00/mo` incremental** (colocated on existing node) OR **`<= EUR 10–20/mo`** (dedicated `CX22`/`CPX11` `~EUR 4–7/mo` + backup box `<= EUR 3.81/mo`) at `<= 256 MB` steady-state RAM | **Reasoned Assumption (`RA` — `[Planning Hypothesis]`)** | Models standard Hetzner EU entry-tier bounds; verify exact checkout tariff and `<= 256 MB` container footprint in `DIR-06` (Gate `G5`). |
| **`RA-02`** | Quantified operator leverage (`VG-01`): reducing manual `2–4 hr` cross-portfolio reviews to **`<= 5 min`** daily exception check (`>= 85%` triage time reduction), `<= 15–60 min` regression MTTD, and `<= 10ms` SQLite `p95` across `18,000` snapshot rows | **Reasoned Assumption (`RA` — `[Planning Hypothesis]`)** | Measurable targets wired directly into `DIR-05`, `DIR-07` (Gate `G4` timed `VG-01` test), and `DIR-08` (Gate `G6` `perf.bench.ts`). |
| **`SR-01`** | Premature optimization & stack-ratification drift risk: `#11 [SPEED-01]` (`DIR-08`) or unratified `Node 22` vs `Go` choice could stall `0` LOC delivery | **Scope / Schedule Risk (`SR`)** | Mitigated by marking Node 22/Fastify/Vite as provisional default pending `#5` `ADR-0001` (`DIR-01`) and gating `#11` strictly behind `G0`–`G5`. |
| **`SR-02`** | Open issue hygiene & unprotected `main` (`#5`–`#11` `labels: []`, `No CI`, `118` open issues) | **Scope / Schedule Risk (`SR`)** | Mitigated via Gate `G0` (`[FEAT-HYG-01]` / `DIR-00`) labeling `#5`–`#11`, wiring CI sanitization checks, and locking `main`. |
| **`OQ-01`** | `#5 [S0-01]` `ADR-0001` final runtime selection (`Node.js 22 + Fastify 5` provisional default vs optional `Go` swap) and resulting active 4-Pillar count (`17` Applicable / `4` N/A vs `18` Applicable / `3` N/A) | **Open Question / Gate (`OQ`)** | Resolved in `DIR-01` (`docs/adr/0001-runtime-stack.md`, Gate `G1`) before application source files are written. |
| **`OQ-02`** | `v2+` OIDC/SSO provider selection (`OIDC_ISSUER_URL`, `OIDC_CLIENT_ID`, `OIDC_REDIRECT_URI` PKCE flow) after `v1` Argon2id/scrypt operator authentication ships cleanly | **Open Question / Gate (`OQ`)** | Deferred cleanly to `v2+`; `v1` ships deterministic fail-closed `operator_sessions` (`DIR-02`, Gate `G2`) with zero unbuilt auth ambiguity. |

### 7.3 Generic Integration Contracts (Public-Repo Sanitized)

Because `AAA` is a public `Apache-2.0` repository, all downstream integration contracts are defined strictly in **repository-agnostic, configurable terms** rather than referencing any specific private repository identifiers:

1. **Monitored Portfolio Repositories (`example-org/example-repo-a`, `example-org/portfolio-service-1`):**
   - **Contract:** Configured dynamically at runtime via `/data/targets.yaml` on Hetzner EU (never committed to git). Every tracked repository is evaluated against standardized governance files (`LICENSE`, `README.md`, `SECURITY.md`, `DEPLOYMENT_TARGET.md` for deployable services, `PROJECT_DIRECTION.md`, `docs/MASTER_PLAN.md`, `dev/FEATURES.md`, `dev/TEST-RESULTS.md`) and active CI workflows.
   - **Flow:** `AAA` pulls 100% passive read-only state via GitHub REST/GraphQL (`DIR-03`); `AAA` performs zero writes and pushes zero issues, PRs, or modifications back to monitored repositories.
2. **External 4-Pillar & Local Worktree Verification Pipelines (`portfolio-audit-cli`):**
   - **Contract:** Any external inventory or 4-Pillar security/quality audit runner (evaluating the `21`-layer `p1_*` through `p4_*` verification matrix with explicit `N/A` support and local clean/dirty git worktree states) submits structured JSON matching `PortfolioSnapshotImportV1` to `POST /api/v1/imports/snapshot` (`DIR-04`) using a dedicated scoped bearer token.
   - **Flow:** External runner -> authenticated JSON POST -> `AAA` `four_pillar_audits` & `worktree_state` persistence -> unified per-repo drilldown view alongside live GitHub CI/CVE telemetry.
3. **Shared Hetzner EU Operations & Monitoring Stack:**
   - **Contract:** `AAA` exposes unauthenticated minimal `/api/healthz` for container/reverse-proxy liveness and authenticated/internal `/metrics` (Prometheus format) for central Hetzner observability dashboards and alerting, plus standard nightly `sqlite3 .backup` artifacts compatible with off-box encrypted backup pipelines (`DIR-06`).
4. **Separate External Coding-Agent Orchestrators & Governance Readers:**
   - **Contract:** Separate external orchestrators own autonomous agent execution, sprint forecasting, and repo changes; `AAA` provides passive read-only compliance scores and rule IDs (`CI-001`, `SEC-001`, `DEP-001`, `RDM-001`) via `/api/v1/repos/{owner}/{name}` or git specs without ever dispatching agents itself.

### 7.4 Verified Source Bibliography

1. **Repository & Live Telemetry (`2026-11-26`):** `Robert-Velhorst/AAA-Software-Development-standards-dashboard` at `HEAD c5cec63` (`2026-11-25T22:38:57Z`), `detailed_repo_status.json`, `live_commits_20261126.json`, and GitHub Issues `#5`–`#55` (incl. live-scrubbed `#30` and closed superseded `#24`, `#46`, `#47`, `#52`, `#53`).
2. **Public Repository Documentation & Governance Files:** `PROJECT_DIRECTION.md` (`c5cec63`), `docs/MASTER_PLAN.md` (`5319714` -> `c5cec63`), `dev/FEATURES.md` (`8086bf5` -> `c5cec63`), `dev/TEST-RESULTS.md` (`559853d`), `DEPLOYMENT_TARGET.md` (`ca41c87`, PR `#3` `084a164`), `README.md` (`3762c49`), `LICENSE` (`Apache-2.0`), `SECURITY.md` (`#1`), `CONTRIBUTING.md` (`#2`), `CODE_OF_CONDUCT.md` (sanitized `2026-11-25`), and `.github/{dependabot.yml,pull_request_template.md,ISSUE_TEMPLATE/*}`.
3. **Internal Charter & Private Documentation Reference (Redacted):** Internal `2026-11-15` Operational Charter and `2026-11-20` Owner Direction Lock (`Internal Private Technical Doc (redacted in public repository)` — private storage links and internal identifiers intentionally omitted from public repository history).
