# Bot instructions

## Purpose and boundaries

Read README.md and spec/SPEC_01.md before working. This is a solo-maintainer portfolio project demonstrating handwritten Go through reverse vibe coding. The human implements the application; bots help define and organize the work.

- Bots may write and refine specs, GitHub issues, project-board entries, documentation, and project-administration scripts (place ticket tooling in spec/src).
- Do not write, generate, patch, or refactor application code, Dockerfiles, deployment implementation, or automated tests. Do not turn tests into an executable specification. If a request appears to cross this boundary, explain it and clarify whether the human intends an explicit exception.
- Tickets may define external application contracts: HTTP endpoints, payload fields, status codes, environment inputs, and observable behavior. Do not include implementation code, pseudocode, internal interfaces, class layouts, or unit-test code.
- Explain concepts and answer questions without supplying the implementation. Human-written tests remain required by the spec.

## Keep this manageable for one person

- Favor the smallest working demonstration and an ordered backlog of concrete implementation steps, including setup work in this empty repository.
- Do not prescribe effort, hours, deadlines, story points, velocity, or delivery estimates. Sizing and scheduling belong to the maintainer, even when an older spec includes estimates.
- Preserve the Go / ECS Fargate / DynamoDB / Secrets Manager design. Three containers share one task, sidecars communicate over localhost, and only the thermostat app is externally reachable.
- Do not add production hardening, multiple tenants, authentication systems, HA, distributed retries, caches, background simulation, admin UIs, Terraform, or a deployment framework unless explicitly requested. Local build commands, quality gates, and GitHub Actions CI are explicitly requested; keep them as three separate tickets. This does not authorize continuous deployment. Manual AWS setup and manual integrated verification are acceptable.
- Avoid speculative architecture, elaborate process, redundant tracking issues, and dependencies added solely for anticipated scale. Do not require a team, sprint ceremonies, or a project board to make progress.

## Tickets and contracts

- Check existing issues, including closed issues, before creating tickets to avoid duplicates. Create or modify GitHub content only within the requested scope.
- Cite the relevant spec sections and any explicit maintainer scope changes. Give each ticket an outcome, bounded scope, observable acceptance criteria, and linked dependencies. Do not add effort estimates.
- Split work across implementation languages or artifact types into separate tickets: Go implementation, Dockerfiles, OpenAPI documents, Makefile/build scripts, and GitHub Actions workflows must not be bundled together. Related prose and verification criteria may accompany their owning artifact.
- Include explicit shell/scaffold work for each component: one Go service/application shell ticket and one Docker/container shell ticket. These are separate from functional implementation. Do not assume an existing module, executable, image, or build entry point.
- Aim for about three infrastructure tickets, three app feature/contract tickets plus its two shell tickets, and four tickets per sidecar including their two shell tickets. Adjust only to preserve meaningful boundaries; do not pad the backlog to meet a count.
- Keep infrastructure provisioning distinct from sample-data fixtures/seeding and mock generation. Establish local build, quality gates, and GitHub Actions in separate tickets.
- Keep required verification in the implementation ticket; do not create separate test projects or prescribe test internals.
- Distinguish spec requirements from proposed decisions. Record material contract ambiguities for the maintainer instead of silently inventing requirements; resolve small choices with the simplest spec-compatible behavior.
- Preserve the explicit non-goals and keep optional work optional. Use issues as the backlog rather than duplicating a second backlog in the repository.
- Track epics using GitHub labels: `epic:secrets`, `epic:config`, `epic:thermostat`, and `epic:build-infra`. Give each implementation ticket its owning epic label and a link to that label's issue view. Build/quality/CI, infrastructure, fixtures, and local mock tooling belong to `epic:build-infra`; keep their tickets distinct within it. Preserve unrelated existing labels when editing issues. Do not create redundant epic tracking issues unless requested.
- Use the repository-linked [Platform Services Kanban](https://github.com/users/matthewdeanmartin/projects/9): Ready → In progress → Ready to test → Done. Ready is the work queue; check linked dependencies before starting. Move work to Ready to test when implementation is available for verification, and Done only after acceptance criteria are verified. Preserve the maintainer's status choices. Sprint cadence and assignments belong to the maintainer; do not impose them.
- The maintainer requested four ordered work phases, tracked in the project's undated `Sprint` single-select field and filtered Kanban views: Sprint 1 - Infrastructure and Shells; Sprint 2 - Thermostat Application; Sprint 3 - Secrets Service; Sprint 4 - Configuration Service. The project README spells out allocations and order. App development uses spec-compatible sidecar mocks before the real services exist; final ECS deployment/integration follows Config in Sprint 4. Preserve epic labels independently of sprint assignments. Do not invent iteration dates or durations.

## Logs, repository care, and verification

- Log substantive human questions to the LLM and brief answers in questions/QUESTIONS_LOG.md. README.md currently refers to QUESTION_LOG.md (singular); use the existing plural file rather than creating a competing log. Do not log routine agent tool calls as human questions.
- Log actual web searches in searches/SEARCH_LOG.md with the query, date, and useful sources. Do not invent search activity. Never put credentials or secret values in either log or GitHub issues.
- Preserve the maintainer's staged, unstaged, and untracked work. Do not commit, push, deploy, or change cloud resources unless requested.
- Follow applicable parent-directory instructions, including the Git Bash shell preference. Do not invent build or test commands: no application implementation or toolchain is established yet.
- For documentation and ticket work, check spec coverage, links, consistency, and the diff. Report what changed and what was verified. Once handwritten code exists, use its documented checks when relevant; do not author tests on the human's behalf.
