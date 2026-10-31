<!-- To update this page (new project, new role, new numbers), use the templates in UPDATING.md -->

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
- **I ship whole products, not just tickets.** I led the engineering of Acallence, a live multi-tenant school platform with 45 domain modules, from database design to deployment and support.
- **I make money and concurrency boring.** Payments are credited exactly once across Paystack and Flutterwave, with webhooks, row locks and a reconciliation sweep. Failures are loud, not silent.
- **I test before I ship.** Acallence has about 2,000 backend tests, 116 frontend test files and CI on every service.
- **I already run AI in production,** carefully: RAG assistants, text-to-SQL limited to safe queries, model fallbacks, and personal data removed before any model call.

---

## Featured work

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

<!-- NEW PROJECT: copy the "Project card" template from UPDATING.md and paste it at the right position above (most impressive first) -->

---

## Tech stack

| Area | Tools |
|---|---|
| **Languages** | Java, Python, TypeScript, JavaScript, SQL |
| **Java** | Spring Boot, Spring Security, Spring Data JPA, Hibernate, Flyway, JUnit 5, Mockito |
| **Python** | Django, Django REST Framework, FastAPI, Pydantic, Celery, pytest |
| **Frontend** | React, Next.js, TanStack Query, Zustand, Tailwind CSS, Vite, PWA, HTMX, Alpine.js, Vitest, Playwright |
| **Data** | PostgreSQL, Redis, SQLite, MySQL, ChromaDB |
| **AI/ML** | LLM APIs (Gemini, OpenAI), RAG, vector databases, text-to-SQL, scikit-learn, predictive analytics, NLP, Gemini Vision |
| **Infrastructure** | Docker, Linux, systemd, GitHub Actions, Caddy, Nginx, Gunicorn, Cloudflare, DigitalOcean (production), Vercel, AWS & IBM Cloud (hands-on) |
| **Payments** | Paystack, Flutterwave, Stripe, webhooks, Termii |
| **Practices** | Multi-tenant SaaS, idempotency and concurrency control, REST API design, automated testing, CI/CD, code review |

---

## What I'm learning now
Deepening AI and ML engineering in public: LLM evaluation, agents, production AI and model serving, plus the maths and ML fundamentals underneath. I share what I build on [X](https://x.com/awosome_dev) and [LinkedIn](https://linkedin.com/in/agbaje-abdulakeem-seun).

<!-- Update this line when you finish a track or ship something new (template in UPDATING.md) -->

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
