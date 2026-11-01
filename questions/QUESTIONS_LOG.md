# Questions to the LLM

## 2026-11-01 — Spec tickets and bot behavior

Request: Read spec/SPEC_01.md and README.md, create GitHub tickets, and add AGENTS.md / CLAUDE.md appropriate for a solo maintainer with limited time.

Response: Created GitHub issues #1–#8 covering the three services, local verification, minimal AWS setup, ECS deployment, and final walkthrough. Added shared bot guidance and a Claude entry point. The human writes application implementation and tests; bots define external contracts and acceptance criteria without implementation samples. Component work retains the spec's approximate 24-hour target; cloud setup and deployment are estimated separately.

## 2026-11-01 — Revise ticket granularity and track epics

Request: Separate implementation languages/artifacts, include explicit Go and container shells, distinguish infrastructure from sample data/mocks, and add separate local build, quality-gate, and GitHub Actions tickets. Do not prescribe effort. Track each service, the app, and build/infrastructure as epics.

Response: Reworked the backlog into 21 issues: four per sidecar, five for the app (two shells plus three contract/feature tickets), three infrastructure, two sample-data/mock-tooling, and three build/quality/CI. Rewrote the original eight issues and added #9–#21. Removed ticket estimates and standalone testing tickets; verification stays with implementation. Added four epic labels and linked dependencies. AGENTS.md and CLAUDE.md now record these rules; the no-estimates instruction supersedes the earlier response's planning approach. GitHub Actions CI is explicitly requested despite the original spec making CI optional; continuous deployment remains outside scope.

## 2026-11-01 — Kanban board and sprint support

Request: Set up Ready, In progress, Ready to test, Done; does GitHub Projects support sprints? After a stop for permissions, the maintainer authorized Projects access and resumed setup.

Response: Created repository-linked Platform Services project #9 with a Kanban board and the requested statuses. Existing tickets enter Ready as the work queue; their linked dependencies still determine what can start. GitHub supports sprints using Iteration fields with configurable durations and breaks. No sprint cadence or assignments were imposed.

## 2026-11-01 — Divide work into four sprints

Request: Divide work into infrastructure and shells, application, Secrets Service, and Configuration Service; spell out the names. Is a sprint just a view on a global Kanban?

Response: Added an undated Sprint single-select field, assigned every issue once, and created four filtered Kanban views. Sprint 1 includes all shells, app contract packaging prerequisite, foundational infrastructure/data, and build/quality/CI. Sprint 2 uses sidecar mocks to implement the app; Sprint 3 implements Secrets; Sprint 4 implements Config and completes ECS integration. Adjusted #12/#18/#16 dependencies to support that order. The project README lists every allocation. Sprint membership is field data; a view filters the shared items and statuses. Native GitHub Iterations add dates and durations, which were not supplied here.
