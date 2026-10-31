

<h1 align="center">Abdulakeem Seun Agbaje</h1>
<h3 align="center">Lead Software Engineer · Java · Python · TypeScript<br>Multi-tenant SaaS · Payments · Production AI</h3>

<p align="center">
  <a href="mailto:agbajeabdulakeemseun@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Email-agbajeabdulakeemseun%40gmail.com-0b6e4f?style=flat-square"></a>
  <a href="https://linkedin.com/in/agbaje-abdulakeem-seun"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-agbaje--abdulakeem--seun-0A66C2?style=flat-square"></a>
  <a href="https://x.com/awosome_dev"><img alt="X" src="https://img.shields.io/badge/X-@awosome__dev-111111?style=flat-square"></a>
  <a href="https://acallence.com"><img alt="Acallence" src="https://img.shields.io/badge/Live%20product-acallence.com-0b6e4f?style=flat-square"></a>
</p>

<p align="center">
  👋 Hello, wherever you're reading this from. I build software that real organisations depend on, and I'm open to working with teams anywhere in the world.
</p>

---

## For recruiters and hiring managers

| | |
|---|---|
| **Role I'm looking for** | Lead / Senior Software Engineer, Backend Engineer (Java or Python), Full-Stack Engineer, AI Engineer |
| **Experience** | 5+ years building and running production systems end to end |
| **Location** | Nigeria, UTC+1 (WAT). Full overlap with UK/Europe working hours; mornings with US Eastern |
| **Work setup** | Remote (any time zone with overlap) or relocation |
| **Languages I work in** | Java, Python, TypeScript/JavaScript, SQL. I pick up new stacks quickly |
| **Contact** | agbajeabdulakeemseun@gmail.com · full CV and references on request |

### Why teams hire me
- **I ship whole products, not just tickets.** I led the engineering of Acallence, a live multi-tenant school platform with 45 domain modules. I also built MDX, an awards platform with about 4,700 automated tests and 91 written architecture decisions, alone in about four weeks.
- **I make money and concurrency boring.** Payments are credited exactly once across Paystack and Flutterwave, with webhooks, row locks and a reconciliation sweep. Failures are loud, not silent.
- **I test before I ship.** Acallence has about 2,000 backend tests, 116 frontend test files and CI on every service.
- **I already run AI in production,** carefully: RAG assistants, text-to-SQL limited to safe queries, model fallbacks, and personal data removed before any model call.

---

## Featured work

### MDX: awards and community platform for African technical creatives · [joinmdx.com](https://joinmdx.com)
**Client project for Motion Design Xperience (MDX) · sole engineer · Oct 2026 – present · launching now**
`Python 3.13` `Django 5.2` `DRF` `PostgreSQL 17` `Valkey/Redis` `Celery` `Next.js 16` `React 19` `TypeScript (strict)` `SSE` `Docker` `Caddy` `GitHub Actions`

**What it is.** A platform where motion designers, animators, 3D/VFX artists and creative technologists across Africa compete in weekly, monthly and yearly awards. It includes:
- jury and member voting, and a live leaderboard;
- profiles and projects, a journal, events with limited seats, and a curated roster;
- token purchases through Paystack, Flutterwave and MTN MoMo.

**Scale of the build.** I designed, built, tested and shipped it alone in about four weeks:
- 319 commits, 20 Django apps and 105 migrations;
- **about 4,700 automated tests**: 3,303 backend, about 1,380 frontend and 22 end-to-end;
- 91 written architecture decision records;
- 17 CI jobs.

**Problems I solved:**
- **The last-slot race.** Two people grabbing the final award-entry slot can never both get it. A row lock, a database CHECK constraint and the database clock inside the transaction handle it, and barrier tests against real PostgreSQL prove it.
- **Fair scoring with few votes.** I built a pure-Python Bayesian shrinkage formula with exact arithmetic (Fraction/Decimal).
  - The scoring config is frozen when voting opens, and its hash is re-checked before results are finalised.
  - Golden-file tests cover it, and the formula is kept free of any framework code.
- **Correct even when Redis is down.** Sessions and lockouts live in PostgreSQL, and cache errors count as misses. A dedicated CI job runs the suite with Redis switched off. When the throttle store is down, sensitive lookups fail closed (503) instead of open, which closes an email-enumeration hole.
- **A live leaderboard that respects privacy.** Server-Sent Events with coalescing, `Last-Event-ID` resume and a snapshot fallback. Tests guarantee that only rank and score are public while voting is open.
- **Money moved exactly once:**
  - payments are verified with the provider before any state change;
  - webhooks go through a single inbox (the only CSRF-exempt view, enforced by a custom Semgrep rule);
  - result corrections can't pay a winner twice.
- **Concurrency bugs found and fixed:** a deadlock between two code paths that took locks in opposite order, and a concurrent index build that could leave an invalid index and break every later migration.
- **A hardened deploy pipeline:**
  - each image is built once, and the same digest is promoted to production after approval;
  - a guard refuses release bundles containing symlinks and only accepts the stack's exact mount sources;
  - when a Docker Compose update silently dropped `env_file`, the guard was changed to fail closed.

**Engineering principles I followed, and enforced in code:**
- **A modular monolith with enforced boundaries.** 33 import-linter contracts. Apps talk only through services and selectors, and pure domain modules (scoring, state machines, money) contain no Django.
- **Decisions written down:** 91 ADRs, including a list of what I deliberately chose *not* to use (Kubernetes, Kafka, Elasticsearch…), each with the condition that would make me revisit it.
- **Types and linting:** mypy `strict`, TypeScript `strict`, ruff with security rules, and naive datetimes banned.
- **Testing beyond the happy path:**
  - property-based tests (Hypothesis);
  - concurrency tests against real PostgreSQL;
  - fault-injection tests with Redis down;
  - pinned query counts against N+1 regressions;
  - accessibility checks (axe, WCAG AA, reduced motion).
- **Security by default:**
  - scanning in CI: gitleaks, Semgrep (with custom rules), Bandit, pip-audit and pnpm audit;
  - per-request CSP nonces on credential pages, Argon2 password hashing, MFA, and a STRIDE threat model per flow.
- **Contracts and budgets in CI:** the OpenAPI schema and generated TypeScript client must match (drift fails the build), and each route has a JavaScript size budget that fails the build when exceeded.
- **Data integrity:**
  - append-only audit and ledger tables, enforced by database triggers;
  - a transactional outbox, so background jobs are never lost or sent twice;
  - UUIDv7 public IDs.
- **Operations:**
  - encrypted, streamed PostgreSQL backups with monitoring check-ins and a written restore-drill runbook;
  - structured JSON logs with request IDs, and Sentry;
  - deploy freeze windows enforced in code.
- **Privacy:** NDPA/GDPR-aligned. A tested inventory of personal data, data export and account deactivation, and age declarations where required.

### Acallence: multi-tenant school management and learning platform · [acallence.com](https://acallence.com)
**Lead Software Engineer, Keematics Technologies Ltd · Sep 2025 – present**
`Java 21` `Spring Boot 3.4` `PostgreSQL` `Redis` `React 19` `TypeScript` `FastAPI` `Docker` `GitHub Actions`

- **Scope:** 45 domain modules covering admissions, fees, results, attendance, computer-based exams and parent communication. The frontend is an installable PWA.
- **Payments:** settlement across Paystack and Flutterwave that credits each payment exactly once.
  - HMAC-verified webhooks, and a row lock on the gateway reference.
  - The amount is checked on all three entry paths.
  - A refused payment writes a ledger row and notifies people instead of failing silently.
- **Tenant isolation:** each school's data is isolated from request to cache key. A build-time architecture test fails any new unscoped query.
- **AI service (FastAPI):** report-card comments, exam questions and finance insights.
  - Signed calls with replay protection, and per-school rate limits.
  - Gemini with an OpenAI fallback.
  - Student names are replaced by codes before any model call.
- **Reliability:** I found and fixed silent failures:
  - stalled Redis consumers that reported healthy;
  - duplicate parent emails on retry;
  - a time-zone bug that would have opened a 9 a.m. class at 10.

### Nexam: offline exam app for school computer labs
`Tauri` `React` `Fastify` `SQLite`
- **Measured:** 150 students sat one paper in one room with zero failures, and all 150 papers were marked.
- **Security:** encrypted question bank (AES-256-GCM), signed licences (Ed25519) and encrypted off-site backups.
- **Tests:** 306 server and 27 frontend tests.

### RAYIYS Services & Lifestyle · [rayiys.ng](https://rayiys.ng)
`Django 5.2` `Celery` `PostgreSQL` `Redis` `Paystack` `Gemini` `ChromaDB` `scikit-learn`
- A subscription laundry platform with pickup and delivery, a shop and referrals.
- Credits can't be granted twice, even when a webhook and a customer's return arrive together.
- **AI in production:**
  - a RAG customer assistant;
  - a text-to-SQL admin assistant restricted to SELECT queries on approved tables;
  - demand and churn models retrained weekly.

### White-label school website platform
`Next.js 16` `Payload CMS 3` `Vercel` `PostgreSQL`
- A website platform for schools.
- **Fix:** parallel build workers were racing to run database migrations and breaking deploys. Fixed with a single migration step and a Postgres advisory lock.

### Al-Hijrah College portal
**System Developer · Nov 2023 – present**
`Django 5.1` `PostgreSQL` `ReportLab` `APScheduler`
- The college's production portal, with role-based access for staff, students and parents (639 commits since March 2024).
- PDF report cards and transcripts, and fee management with a configurable debtor gate.
- Scheduled parent reports.

### AWO Muslim Community platform · [audawo.org](https://audawo.org)
`Django 5.2` `Celery` `Redis` `PostgreSQL` `Paystack` `Termii`
- Membership and finances for a community: contribution groups, payments, fundraising campaigns and events.
- SMS, WhatsApp and email reminders, plus PDF and Excel reports.

### LaundryPro *(in development, 2026)*
`Django` `Next.js` `FastAPI` `Gemini` `Stripe` `Paystack` `Docker`
- Multi-tenant laundry SaaS with custom domains, wallets with a ledger, prorated upgrades and tenant payouts.
- An AI service for garment classification and quality inspection.



---

## What I bring to your team

These are habits I've used on every project above, and I can bring them to any team, whatever the language or domain.

| What you get | How I do it |
|---|---|
| **Correctness under concurrency** | I find the race before users do: row locks plus database constraints, idempotency keys, exactly-once payment settlement, and barrier tests that prove it against a real database. |
| **Architecture that stays clean as it grows** | Modular monoliths with boundaries enforced by tooling (import-linter, architecture tests), pure domain logic kept free of frameworks, and decisions recorded as ADRs so new teammates know *why*. |
| **Tests that catch real failures** | Unit, integration, property-based, concurrency, fault-injection (dependency down), contract and end-to-end tests. Coverage is reported, but I judge tests by the failures they catch, not by a percentage. |
| **Security and privacy from day one** | Threat modelling (STRIDE), secret and dependency scanning in CI, strict CSP, MFA, personal data minimised (and removed before any AI model call), and NDPA/GDPR-aligned export and deletion. |
| **Calm, repeatable releases** | Build once and promote the same artifact, forward-only migrations, guarded deploy scripts, encrypted backups with restore runbooks, structured logs and alerting. |
| **Pragmatic choices** | The simplest stack that's correct: PostgreSQL as the source of truth, Redis only where it isn't needed for correctness, with no Kubernetes or Kafka until there's a written reason. |
| **AI features that are safe in production** | Model fallbacks, rate limits, signed service calls, text-to-SQL restricted to safe queries, and private data replaced by codes before a model sees it. |
| **Clear communication** | Written decisions, runbooks and pull-request descriptions; async-friendly from UTC+1 with overlap across Europe, Africa and US mornings. |

---

## Tech stack

| Area | Tools |
|---|---|
| **Languages** | Java, Python, TypeScript, JavaScript, SQL |
| **Java** | Spring Boot, Spring Security, Spring Data JPA, Hibernate, Flyway, JUnit 5, Mockito |
| **Python** | Django, Django REST Framework, FastAPI, Pydantic, Celery, django-allauth, pytest |
| **Frontend** | React, Next.js, TanStack Query, Zustand, Tailwind CSS, Vite, PWA, HTMX, Alpine.js, Vitest, Playwright |
| **Data** | PostgreSQL, Redis, SQLite, MySQL, ChromaDB |
| **AI/ML** | LLM APIs (Gemini, OpenAI), RAG, vector databases, text-to-SQL, scikit-learn, predictive analytics, NLP, Gemini Vision |
| **Infrastructure** | Docker, Docker Compose, Linux, systemd, GitHub Actions, GHCR, Caddy, Nginx, Gunicorn, uvicorn, Cloudflare, DigitalOcean (production), Vercel, Render, AWS & IBM Cloud (hands-on) |
| **Quality & security tooling** | mypy (strict), ruff, import-linter, Hypothesis, pytest, JUnit 5, Vitest, Playwright, axe-core, Semgrep, gitleaks, Bandit, pip-audit, Sentry, structlog |
| **Realtime & async** | Server-Sent Events, Redis pub/sub, Celery & Celery Beat, transactional outbox |
| **Payments** | Paystack, Flutterwave, Stripe, webhooks, Termii |
| **Practices** | Multi-tenant SaaS, idempotency and concurrency control, REST API design, automated testing, CI/CD, code review |

---

## What I'm learning now
Deepening AI and ML engineering in public: LLM evaluation, agents, production AI and model serving, plus the maths and ML fundamentals underneath. I share what I build on [X](https://x.com/awosome_dev) and [LinkedIn](https://linkedin.com/in/agbaje-abdulakeem-seun).



---

## Experience

| Role | Organisation | Dates |
|---|---|---|
| Lead Software Engineer | Keematics Technologies Ltd · remote | Sep 2025 – present |
| System Developer | Al-Hijrah College · Ogun State, hybrid (NYSC year Nov 2023 – Oct 2024) | Nov 2023 – present |
| Software Developer | Awo Tech Hub · Ekiti State | Jan 2023 – Nov 2023 |
| Frontend Developer (Internship) | Taoglobal Technologies Ltd · remote | Apr 2021 – Dec 2022 |

**Education:** B.Sc. Water Resources Management and Agrometeorology, Federal University Oye-Ekiti (2016 – 2023)

**Certifications:**
- IBM AI Developer Professional Certificate
- AWS Cloud Solutions Architect
- IBM Full Stack Software Developer
- IBM DevOps, Cloud and Agile Foundations
- Meta Front-End Developer
- Meta Database Engineer

All six are from Coursera. Also: Google Africa Developer Scholarship (GADS) and the Andela React Learning Program.

---

<p align="center">
  <b>Hiring, building something, or want to collaborate?</b><br>
  Email <a href="mailto:agbajeabdulakeemseun@gmail.com">agbajeabdulakeemseun@gmail.com</a> or message me on <a href="https://linkedin.com/in/agbaje-abdulakeem-seun">LinkedIn</a>.
</p>
