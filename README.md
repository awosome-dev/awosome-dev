<h1 align="center">Hi, I'm Abdulakeem Seun Agbaje 👋</h1>
<h3 align="center">Lead Software Engineer · Java · Spring Boot · Python · TypeScript · Payments · AI</h3>

<p align="center">
  <a href="https://acallence.com">acallence.com</a> ·
  <a href="https://linkedin.com/in/agbaje-abdulakeem-seun">LinkedIn</a> ·
  <a href="https://x.com/Agbaje_iKKim">X</a> ·
  agbajeabdulakeemseun@gmail.com
</p>

<p align="center"><b>Nigeria (UTC+1) · Open to remote roles or relocation</b></p>

---

### About me
I'm a software engineer with 5+ years of building and running production systems end to end. I led the engineering of **[Acallence](https://acallence.com)**, a live multi-tenant school platform on Java 21, Spring Boot, PostgreSQL, Redis and React 19, and built its payment settlement, tenant isolation and AI service.

I care about money and concurrency being boring: payments credited exactly once, failures that are loud, and changes that are tested before they ship.

**Open to:** Lead / Senior Software Engineer, Backend Engineer (Java, Python), Full-Stack Engineer and AI Engineer roles.

---

### What I've built

**Acallence: multi-tenant school management and learning platform** · [acallence.com](https://acallence.com)
*Lead Software Engineer, Keematics Technologies Ltd (Sep 2025 – present)*
- **Scope:** 45 domain modules on Java 21, Spring Boot 3.4, PostgreSQL and Redis, with a React 19 + TypeScript PWA. Covers admissions, fees, results, attendance, computer-based exams and parent communication.
- **Payment settlement (Paystack and Flutterwave):** credits each payment exactly once.
  - HMAC-verified webhooks, and a row lock keyed on the gateway reference.
  - The amount is checked on all three entry paths: webhook, checkout return, and a 5-minute reconciliation sweep.
- **Tenant isolation:** the tenant is resolved from the JWT into a request-scoped context, and queries and Redis cache keys are tenant-scoped. A build-time architecture test fails on any new unscoped lookup of school data.
- **AI service (FastAPI):** report-card comments, exam-question generation and finance insights.
  - HMAC-signed calls with replay protection, and per-school rate limits in Redis.
  - Gemini with an OpenAI fallback that records which model answered.
  - Student names are replaced by codes before any model call.
- **Testing and delivery:** about 2,000 backend tests (JUnit 5, Mockito), 116 frontend test files (Vitest, Playwright), 267 forward-only Flyway migrations, and GitHub Actions CI across all services.
- **Silent failures found and fixed:**
  - Redis stream consumers that stopped reading after one error while reporting healthy.
  - A retry path that could email a parent twice.
  - A server time-zone bug that would have opened a 9 a.m. live class at 10.

**Nexam: offline computer-based testing for school labs**
- **Stack:** Tauri desktop shell, React, Fastify, SQLite.
- **Measured:** 150 students sat one paper with zero failures, and all 150 papers were marked.
- **Security:** AES-256-GCM encrypted question bank, Ed25519-signed licences, and encrypted off-site backups.
- **Tests:** 306 server tests and 27 frontend tests.

**White-label school website platform**
- **Stack:** Next.js 16 + Payload CMS 3, on Vercel.
- **Fix:** parallel build workers were racing to run database migrations and breaking deploys. Fixed with a single migration step and a Postgres advisory lock.

**Al-Hijrah College portal**
*System Developer (Nov 2023 – present)*
- Django 5.1 + PostgreSQL, with role-based access for staff, students and parents (639 commits since March 2024).
- Results and transcripts as PDF report cards (ReportLab), plus Excel exports.
- Fee management with a configurable debtor gate.
- Scheduled parent reports (APScheduler, cron).

**RAYIYS Services & Lifestyle** · [rayiys.ng](https://rayiys.ng)
- Subscription laundry platform (Django 5.2, Celery, PostgreSQL, Redis, Paystack).
- Payments and coupon limits are protected with row locks, so a webhook and a customer's return can't grant credits twice.
- AI in production:
  - a RAG customer assistant (Gemini, ChromaDB);
  - a text-to-SQL admin assistant restricted to SELECT queries on allow-listed tables;
  - scikit-learn demand and churn models, retrained weekly by Celery Beat.

**AWO Muslim Community platform** · [audawo.org](https://audawo.org)
- Digitised a community's membership and finances: contribution groups, Paystack payments, fundraising campaigns, events, and bulk member import with account claiming.
- SMS, WhatsApp and email reminders, plus PDF and Excel reports.

**LaundryPro** *(in development, 2026)*
- Multi-tenant laundry SaaS (Django, Next.js, FastAPI) with tenant subdomains and custom domains.
- Wallets with a ledger, prorated plan upgrades and tenant payouts (Stripe, Paystack).
- A Gemini-powered FastAPI service for garment classification and quality inspection.

---

### Tech stack

| Area | Tools |
|---|---|
| **Languages** | Java, Python, TypeScript, JavaScript, SQL |
| **Java** | Spring Boot, Spring Security, Spring Data JPA, Hibernate, Flyway, JUnit 5, Mockito |
| **Python** | Django, Django REST Framework, FastAPI, Pydantic, Celery, pytest |
| **Frontend** | React, Next.js, TanStack Query, Zustand, Tailwind CSS, Vite, PWA, HTMX, Alpine.js, Vitest, Playwright |
| **Data** | PostgreSQL, Redis, SQLite, MySQL, ChromaDB |
| **AI/ML** | Gemini API, LLM APIs, RAG, vector databases, text-to-SQL, scikit-learn, predictive analytics, NLP, Gemini Vision |
| **Infrastructure** | Docker, Linux, systemd, GitHub Actions, Caddy, Nginx, Gunicorn, DigitalOcean (production), Vercel, Cloudflare, AWS & IBM Cloud (hands-on) |
| **Payments** | Paystack, Flutterwave, Stripe, webhooks, Termii |
| **Practices** | Multi-tenant SaaS, idempotency and concurrency control, REST API design, automated testing, CI/CD, code review |

---

### Currently
I'm deepening my AI and ML engineering in public, through a 320-day AI engineering curriculum (LLM apps, evals, agents, production AI, model serving) and a 90-day ML engineering programme (maths, classical ML, deep learning, transformers, MLOps). Follow along on X and LinkedIn.

---

### Experience
| Role | Where | When |
|---|---|---|
| Lead Software Engineer | Keematics Technologies Ltd (remote) | Sep 2025 – present |
| System Developer | Al-Hijrah College, Ogun State (hybrid; NYSC year Nov 2023 – Oct 2024) | Nov 2023 – present |
| Software Developer | Awo Tech Hub, Ekiti State | Jan 2023 – Nov 2023 |
| Frontend Developer (Internship) | Taoglobal Technologies Ltd (remote) | Apr 2021 – Dec 2022 |

**Education:** B.Sc. Water Resources Management and Agrometeorology, Federal University Oye-Ekiti (2016 – 2023)

**Certifications:**
- IBM AI Developer Professional Certificate
- AWS Cloud Solutions Architect
- IBM Full Stack Software Developer
- IBM DevOps, Cloud and Agile Foundations
- Meta Front-End Developer
- Meta Database Engineer

All six are from Coursera. Also: Google Africa Developer Scholarship (GADS) and the Andela React Learning Program.
