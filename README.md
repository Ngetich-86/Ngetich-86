![](https://github.com/halfrost/halfrost/raw/master/icons/header_.png)

# Gideon Ngetich

**Software Engineer in Test · Python, pytest, API & Integration Testing, CI/CD**

[Portfolio](https://gideonngetich.me) · [LinkedIn](https://www.linkedin.com/in/gideon-ngetich/)

I test backend and distributed systems by writing automated regression, API and
integration tests, reproducing failures before fixing them, and wiring those checks
into CI so regressions are caught before release. I also build the backend services
I test, which shapes how I look for failure modes.

---

## Testing & Quality Engineering

**API and integration testing.** pytest suites against a FastAPI + PostgreSQL service;
Jest + Supertest API-layer tests; Testcontainers-backed integration tests for a Spring Boot
API; PostgreSQL integration tests for a Rust service, run in CI. Coverage includes
authentication and authorization, validation, negative paths, error mapping and
status-code contracts.

**Regression tests with red/green proof.** A regression test should fail without the fix
and pass with it, so I check both directions before calling it done.

**Browser and mobile automation.** Playwright for end-to-end flows, accessibility checks
(axe) and link integrity; Maestro for Android smoke flows on physical devices, written with
semantic selectors and no fixed sleeps.

**Performance.** Grafana k6 smoke, spike, stress and soak profiles with explicit
thresholds, reported as test conditions rather than capacity claims.

**Quality gates in CI/CD.** Lint, type checks and automated suites as blocking steps in
GitHub Actions; a Jenkins pipeline and Prometheus/Grafana monitoring in a DevSecOps lab.

**Failure diagnosis.** Reading CI logs and container state in Linux/Docker environments to
separate infrastructure failures from real product defects.

**Web & mobile quality.** Functional, regression, smoke and exploratory testing,
with test cases, environments and evidence recorded so results can be reproduced.

---

## Backend & Systems Engineering

- REST APIs in Python (FastAPI), TypeScript (Express, NestJS, Hono), Java (Spring Boot) and Rust
- Distributed-systems behaviour: durable admission, idempotency keys, at-least-once
  processing, lease-based recovery (`FOR UPDATE SKIP LOCKED`)
- Authentication and authorization: JWT, role-based access control
- PostgreSQL, SQLite and Redis; Drizzle and Prisma ORMs
- Docker and Docker Compose environments; Prometheus/Grafana observability

---

## Open Source Work

### CVAT — Regression Test Contribution in Validation

`Python · pytest · REST API · Docker · GitHub Actions`

- Added REST API regression coverage for cloud-storage object keys containing empty path
  segments, following the behavior fixed in
  [cvat-ai/cvat#11201](https://github.com/cvat-ai/cvat/pull/11201).
- Covers both root-level and nested empty-path-segment cases and verifies that valid
  sibling files remain visible.
- Passed CVAT's full CI pipeline on my fork, including all 54 tests in
  `test_cloud_storages.py` and the broader REST API job with 2313 passed and 0 failed.
- Verified the regression red/green in GitHub Actions: both new cases pass with the current
  fix and fail with HTTP 400, a validation error on the listing's `content` field, when only
  the #11201 filter is removed.

Branch: [Ngetich-86/cvat · test/cloud-storage-empty-path-segment-listing](https://github.com/Ngetich-86/cvat/tree/test/cloud-storage-empty-path-segment-listing)

---

## Selected Projects

**[AI Evaluation & Rubric Management API](https://github.com/Ngetich-86/ai-evaluation-rubrics-management-system)**: a REST API for rubric-based human evaluation of AI outputs, with multi-rater scoring and inter-rater agreement.<br>
`Python · FastAPI · PostgreSQL · SQLite · pytest · GitHub Actions · Swagger`
- 57 pytest tests covering rubrics, scoring, submissions, agreement statistics and the web UI
- Scoring rules enforced and tested: every criterion scored exactly once, within the scale, no duplicate rater evaluations
- Lint and the test suite run in GitHub Actions; [live demo](https://ai-evaluation-rubrics.onrender.com/) with Swagger docs

**[PulseStream](https://github.com/Ngetich-86/PulseStream)**: a co-developed Rust event processing platform built for bounded concurrency, idempotency and crash recovery.<br>
`Rust · PostgreSQL · Docker · GitHub Actions`
- 63 tests, including 28 PostgreSQL integration tests run as a separate CI job
- Tests idempotent replays (`409` on key reuse), `503` rather than `202` on database outage, and lease reclaim after worker crashes
- CI gates on `rustfmt`, `clippy -D warnings`, unit tests, integration tests and build

**[Employee Management System](https://github.com/Ngetich-86/springboot-nextjs-employee-manager)**: a Spring Boot + Next.js app with JWT authentication and role-based access control.<br>
`Java · Spring Boot · Next.js · PostgreSQL · Docker · JUnit · Mockito · Testcontainers · Vitest`
- 65 JUnit tests, with Mockito unit tests and Testcontainers-based integration tests
- CI runs backend tests, frontend lint, frontend tests and the production build

**[DevSecOps Lab](https://github.com/Ngetich-86/DevSecOps-Lab-)**: a Node/TypeScript task API used to practise quality gates in the delivery pipeline.<br>
`TypeScript · Express · PostgreSQL · Jest · Supertest · Docker · Prometheus · Grafana · Jenkins`
- 22 unit tests enforced in GitHub Actions against a Postgres 16 service, with JUnit report artifacts
- 28 Jest + Supertest integration tests against a real database (run locally)
- `/metrics` endpoint with a provisioned Grafana dashboard; the README separates what is enforced from what is only planned

**[Portfolio site](https://github.com/Ngetich-86/Gideon.Ngetich)**: a React/TypeScript portfolio guarded by automated browser checks.<br>
`TypeScript · React · Playwright · axe · Lighthouse CI · GitHub Actions`
- Playwright E2E, accessibility and link-integrity suites plus Lighthouse CI, all in GitHub Actions

More testing work: [Task Manager QA lab](https://github.com/Ngetich-86/task_manager) (78 Jest + Supertest tests at 74.6% statement coverage in CI, plus k6 load profiles) · [Icon Training mobile QA](https://github.com/Ngetich-86/icon-training-mobile-qa) (Maestro, risk-based test design)

---

## Tooling

| Area | Tools |
| --- | --- |
| Testing | pytest · Jest · Supertest · JUnit · Mockito · Testcontainers · Vitest · Playwright · axe · Maestro · k6 |
| Languages | Python · TypeScript · JavaScript · Java · Rust · SQL · Bash |
| Backend | FastAPI · Express · NestJS · Hono · Spring Boot |
| Data | PostgreSQL · SQLite · Redis |
| CI/CD & Ops | GitHub Actions · Jenkins · Docker · Docker Compose · Prometheus · Grafana · Linux |
| API tooling | OpenAPI / Swagger |

---

## 📊 GitHub Activity

<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=ngetich-86&theme=default" alt="GitHub statistics" />
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=ngetich-86&theme=default" alt="Top languages by commit" />
</p>

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=ngetich-86" alt="GitHub streak" />
</p>

---

## Contact

[Portfolio](https://gideonngetich.me) · [LinkedIn](https://www.linkedin.com/in/gideon-ngetich/)
