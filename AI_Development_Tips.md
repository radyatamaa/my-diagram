# Step-by-Step App Development (AI Prompt Driven)

> **Goal:** Build an app from zero to ready for use by using AI as a pair programmer, in a clean, simple, and maintainable way.

---

## 1) Define Goal & Scope (Avoid Scope Creep)

**Make these clear:**
- What problem the app solves
- Who the main users are
- 3–5 required MVP features
- Non-goals (what will NOT be built now)

**AI Prompt:**
> “I want to build a **[app type]** for **[target users]**. Required MVP features: **[...]**. Non-goals: **[...]**. Please write a 1-page scope with goals, user stories, acceptance criteria, and technical limits.”

---

## 2) Create Mini PRD & User Flow

Write a short document to keep direction clear:
- User stories
- User flow (happy path + edge cases)
- Needed data
- Error and empty states

**AI Prompt:**
> “From this scope, create a **Mini PRD** with user stories (‘As a… I want… so that…’), step-by-step user flow, key edge cases, and acceptance criteria.”

---

## 3) Choose Architecture & Tech Stack

Pick tools you know well and can ship fast.

- Frontend: React / Next / Vue  
- Backend: Node / Go / Laravel  
- Database: Postgres / MySQL  
- Auth: JWT / OAuth  
- Hosting: VPS / Cloud  

**AI Prompt:**
> “With a deadline of **[X days]** and my skills in **[stack]**, suggest a simple architecture with modules, layers, folder structure, and trade-offs.”

---

## 4) Design Data Model & API First

This avoids rewriting code later.

- Main tables
- Relations and indexes
- API endpoints with request/response examples
- Status codes and error format

**AI Prompt:**
> “Create a data model for feature **[...]** with tables, columns, types, relations, and indexes. Then create an API contract with endpoints, payloads, and sample responses.”

---

## 5) Repo Setup & Engineering Rules

Set standards early.

**Must have:**
- `.env.example`
- Lint and format tools
- Pre-commit hooks (optional)
- Logging and config loader
- Simple CI (test + lint)

**AI Prompt:**
> “Create a repo setup checklist for **[stack]** with env, config, linting, formatting, testing, and simple CI. Include folder structure.”

---

## 6) UI Skeleton & Component Plan (If Frontend)

- Simple wireframes
- Page list
- Component list
- State management plan

**AI Prompt:**
> “From the user flow, list all pages and components. For each page, list needed state, loading/empty/error states, and API usage.”

---

## 7) Build Features Step by Step (Vertical Slice)

Build one feature fully before moving on.

**One slice =** UI → API → DB → Tests → Polish

**Example order:**
1. Login / Auth  
2. Main CRUD  
3. Search / Filter  
4. Logs / Analytics  

**AI Prompt:**
> “Create a vertical slice plan for this MVP. Order features by priority, give effort estimate, and list risks.”

---

## 8) Testing Plan (Simple but Useful)

**Minimum tests:**
- Unit tests for core logic
- Integration tests for key APIs
- 1–2 E2E tests for happy paths

**AI Prompt:**
> “For **[stack]**, suggest a simple testing pyramid and list important test cases for feature **[...]**.”

---

## 9) Security & Quality Checks

Often missed but important.

**Checklist:**
- Server-side input checks
- Basic rate limiting
- Output cleaning (XSS)
- Role and permission checks
- Secrets not stored in git

**AI Prompt:**
> “Review this API design for security risks and suggest quick fixes.”

---

## 10) Logs & Monitoring

Make bugs easier to find.

- Structured logs
- Error tracking (optional)
- Basic metrics (response time, errors)
- Request ID

**AI Prompt:**
> “Add simple logging and monitoring for **[stack]** with log format, middleware, and example logs.”

---

## 11) Deployment Flow

From local to production.

- Docker (if needed)
- Auto database migration
- Health check endpoint
- Simple rollback plan

**AI Prompt:**
> “Create deployment steps for **[stack]** on **[platform]** including env vars, build, migrate, start, health check, and rollback.”

---

## 12) Documentation & Handover

Keep it short and clear.

**Docs should include:**
- How to run locally
- Environment variables
- API list
- Known limits
- Next improvements

**AI Prompt:**
> “Create a short README with setup, run, test, env vars, endpoints, and known limits.”

---

# Main Prompt Template (Copy–Paste)

## Context
App: **[short description]**  
Users: **[...]**  
MVP features: **[...]**  
Limits: **[deadline, stack, platform, rules]**

## Task
Please create: **[PRD / ERD / API / code / tests]**

## Rules
- Make it practical and ready to use.
- Write assumptions if any.
- Focus on MVP only, no over-design.

---

# AI Workflow Tips

- Ask AI for a **plan + checklist** first.
- Ask for code per feature, not all at once.
- Ask AI to review code for bugs, edge cases, and security.
- Save decisions in `docs/decisions.md`.
