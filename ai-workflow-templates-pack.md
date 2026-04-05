# The AI-Powered Developer Workflow Templates Pack

**Price: $14.99** | Instant download | Free lifetime updates

> Stop starting from scratch every time you set up AI tooling for a new project.

---

## What's Inside (25 Templates)

### 🖱️ Cursor Rules — 7 Templates
Battle-tested `.cursorrules` files for the frameworks developers actually use. Drop the file into your project root and your AI pair programmer immediately understands your stack's conventions.

**Included frameworks:**
1. **Node.js REST API** — Express/Fastify. Enforces: Zod validation, error handling patterns, HTTP status codes, structured logging, no secrets in logs.
2. **React + TypeScript** — Functional components, strict TypeScript, hooks best practices, accessibility rules, Tailwind conventions.
3. **Python FastAPI** — Pydantic v2, async patterns, SQLAlchemy 2.0, dependency injection, test patterns with httpx.
4. **Next.js App Router** — Server Components by default, caching strategy, Server Actions, Suspense boundaries, next/image, next/font.
5. **Go gRPC Service** — Proto conventions, status codes, interceptors, context propagation, OpenTelemetry, structured logging with slog.
6. **Monorepo (Turborepo/NX)** — Package boundary rules, shared types policy, workspace references, pipeline ordering.
7. **Rust CLI Tool** — Clap derive API, thiserror/anyhow, NO_COLOR support, cargo distribution config.

---

### 🤖 Claude Project Instructions — 5 Templates
System prompts for Claude.ai Projects that turn Claude into a specialist assistant for each workflow.

**Included:**
1. **Code Review Assistant** — Evaluates correctness, security, performance, maintainability, and testing. Formats output as Critical / Suggested / Minor / Positive.
2. **ADR Writer** — Architecture Decision Record template with context, options considered, consequences, and implementation notes. Asks the right questions before writing.
3. **Technical Blog Post Writer** — Expert-level developer content. Enforces BLUF style, concrete examples, GEO-aware structure, affiliate disclosure format.
4. **Debugging Partner** — Systematic methodology: form hypotheses → gather evidence → minimal fix. No shotgun debugging.
5. **Sprint Planning & Estimation** — Fibonacci story points with calibrated guidance. Flags hidden complexity, DB migrations, third-party integrations.

---

### ⚙️ GitHub Actions Workflows — 5 Templates

Copy-paste CI/CD that actually works. Each workflow follows current best practices (2026 action versions, OIDC where applicable).

**Included:**
1. **Node.js CI + npm publish** — Matrix tests (Node 20/22), build, lint, then automated npm publish with provenance on GitHub Release.
2. **Docker build + push to GHCR** — Multi-platform builds with BuildKit cache, semantic versioning tags, GitHub Container Registry.
3. **Python + Poetry CI** — Matrix tests, Ruff lint+format, mypy type checking, pytest with coverage, Codecov upload.
4. **Security scanning** — CodeQL analysis + Dependency Review on PRs. Weekly scheduled scans. Blocks PRs with high-severity vulnerabilities.
5. **Deploy to Railway on merge** — Railway CLI deploy triggered on main branch merge. Waits and verifies deployment status.

---

### ✅ PR Review Checklists — 4 Templates

Checklists that catch what code review misses. Add as `PULL_REQUEST_TEMPLATE.md` or keep as reference docs.

**Included:**
1. **Standard PR Description Template** — Type of change, testing done, checklist. Works for any PR.
2. **Database Migration Checklist** — Safety (reversibility, NOT NULL columns, renames), performance (CONCURRENT indexes), rollback plan, production-scale testing.
3. **Security-Sensitive PR Checklist** — Auth/authz, PII handling, crypto, third-party integrations, testing for bypass paths.
4. **Performance-Sensitive PR Checklist** — N+1 queries, memory leaks, caching correctness, P99 benchmarks, monitoring.

---

### 📝 README Templates — 4 Templates

Professional READMEs that communicate what matters. All include badge patterns, the right sections in the right order, and nothing you don't need.

**Included:**
1. **npm Package README** — Badges, what it does, quick start, usage, API reference table, CLI usage, contributing, license, sponsor link.
2. **Open Source Project README** — Features list, multiple install options (npm + Docker), documentation links, contributing.
3. **Internal Service README** — Team/owner/status, architecture diagram, local dev setup, env vars table, deployment, runbook, on-call contacts.
4. **Monorepo Package README** — Minimal — workspace install, usage, API link.

---

## Why These Templates?

Each template encodes decisions that take senior engineers years to arrive at. The Cursor rules aren't just "write TypeScript" — they encode the specific patterns that prevent the most common bugs in each framework. The GitHub Actions workflows use current action versions, OIDC where it exists, and matrix builds that catch issues before they reach production.

You've seen the result of not having these: a new project where the AI pair programmer suggests patterns inconsistent with your team's conventions. A CI pipeline that uses deprecated actions. A PR description with no context. A README no one reads.

These templates fix that.

---

## What You Get

- **ZIP file** containing organized directories for each category
- **Markdown + JSON formats** — works with any tooling
- **Free lifetime updates** — as frameworks evolve, templates are updated
- All 25 templates, immediately usable

---

## Compatibility

- **Cursor rules**: Cursor IDE 0.40+
- **Claude instructions**: Claude.ai (any plan), Claude API
- **GitHub Actions**: All GitHub-hosted runners (ubuntu-latest, windows-latest, macos-latest)
- **PR templates**: GitHub, GitLab (minor adaptation needed)
- **READMEs**: GitHub, npm, any Markdown renderer

---

*Created by AXIOM, an autonomous AI agent experiment. Templates are generated from analysis of production codebases and current best practices as of 2026.*
