# Authoritative Project Direction — AAA-Software-Development-standards-dashboard

> **Status:** Authoritative Direction Locked (`2026-11-25`).
> This repository stays **Public (`Apache-2.0`)** during active development with **ZERO private data leakage**.

| Dimension | Locked Direction |
| --- | --- |
| **Repository** | `Robert-Velhorst/AAA-Software-Development-standards-dashboard` |
| **Classification** | Open-Source 100% Passive Read-Only Compliance Scoreboard (`Apache-2.0`) |
| **Pricing / Governance** | Non-commercial open-source engineering compliance scoreboard (`Apache-2.0`, zero SaaS billing). |
| **Target Stack** | `Node.js 22 + Fastify 5 + SQLite WAL + React 19 + Vite + Caddy` validated strictly against synthetic fixtures |
| **Hosting Target** | Hetzner EU (self-hosted authenticated operator deployment behind Caddy TLS; zero serverless/Vercel hosting). |

## Locked Decisions (`2026-11-25`)

1. **100% Passive Read-Only Compliance Scoreboard ONLY:** `AAA` tracks CI pass rates, security advisories, docs/license/Hetzner deployment drift, GitHub ProjectV2 & unlabeled-issue visibility, and external 4-Pillar `PortfolioSnapshotImportV1` snapshot imports.
2. **Strict Negative Boundaries (Zero Scope Creep):**
   - **Zero GitHub Write Permissions:** `AAA` never requests write tokens, never pushes commits, never opens PRs, and **never creates GitHub issues** (legacy issue-campaign & PR-blueprint ideas superseded `2026-11-25`).
   - **Zero Coding-Agent Orchestration:** Separate external orchestrators own agent execution and sprint forecasting; `AAA` provides passive read-only compliance scores and copyable local remediation hints only.
   - **Zero Feature-Completeness Creep:** Do not turn `AAA` into an effort/sprint estimator or multi-repo backlog manager.
3. **Active Public Development (`Apache-2.0`) & Strict Sanitization (`DIR-00`):** Keep the repo public for external collaboration while enforcing zero private repo names, zero internal IP addresses, zero private Drive links, and zero personal emails anywhere in git history, tests, fixtures (`example-org/*` synthetic only), or issue templates. Keep live runtime targets and tokens strictly behind authenticated operator access on Hetzner EU.

---

*This file serves as the authoritative project direction record inside the repository.*

- **Canonical Single Source of Truth:** [docs/MASTER_PLAN.md](docs/MASTER_PLAN.md)
