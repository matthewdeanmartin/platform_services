# Claude instructions

Read and follow [AGENTS.md](AGENTS.md), then [README.md](README.md) and [spec/SPEC_01.md](spec/SPEC_01.md). AGENTS.md is the shared source of bot behavior for this repository.

This is reverse vibe coding: the solo maintainer writes application code and tests by hand. Bots handle specs, tickets, documentation, and project administration. Do not supply implementation code, pseudocode, internal designs, or test code in tickets. External API contracts and observable acceptance criteria are welcome.

Keep the backlog small and the demo bounded to the spec. Do not expand this into an enterprise platform or add process that requires a team. Preserve existing work and follow the logging and verification rules in AGENTS.md.

Do not prescribe effort or delivery estimates. Split tickets by implementation language/artifact, include separate Go and container shell tickets, and keep infrastructure, sample data/mocks, local build, quality gates, and GitHub Actions distinct as required by AGENTS.md.
