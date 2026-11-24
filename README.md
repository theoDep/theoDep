## Hi, I'm Theo

Software developer based in France, working since 2023 on industrial software and, before that, an advertising platform. I care about shipping software that works and stays easy to change: architecture that holds as the codebase grows, short feedback loops that catch mistakes early, and development workflows where AI agents do a large share of the work without lowering the bar.

### Testability and feedback loops

- **Fast local feedback.** Pre-commit hooks regenerate, format and lint the code and mirror the checks CI runs, so a pull request rarely fails on something a laptop could have caught.
- **Tests against real services.** Integration tests run against a real PostgreSQL instead of a mocked database, with one isolated database per package cloned from a migrated template, so the suite runs in parallel with no infrastructure to set up.
- **Functional and load tests.** Functional suites exercise the API end to end, and k6 scenarios measure user journeys and traffic spikes before they reach production.
- **Readable tests by convention.** Tests read as scenarios while the setup, test doubles and assertions live in dedicated drivers, and a checker in CI keeps the convention from eroding.
- **Hardware out of the loop.** A virtual machine simulator in Go, covered by Playwright end-to-end tests, lets features be built and verified without the physical machine.

### Architecture and maintainability

- **Modular monoliths.** A Go backend split into about twenty business modules that talk only through published contracts, and a Flutter app organized by feature, with domain, application, data and presentation layers.
- **Architecture as tests.** Module boundaries and import rules are checked by tests in CI, with a list of known violations that is only allowed to shrink.
- **Generated over hand-written.** Code generators for audit trails, authorization and telemetry parsers, so repetitive code has one source of truth.

### Scaling development with AI agents

- **Agent-ready repositories.** The repositories I work on describe their architecture, conventions and commands for agents, so the same rules apply whoever writes the code.
- **Checks agents cannot skip.** The hooks, tests and architecture checks above are the guardrails that make agent-written code safe to merge: an agent gets the same fast, precise feedback a developer does.
- **Shared skills.** A skill and workflow pack for Claude Code, Cursor and Antigravity that encodes how I design, slice pull requests, test and review, so agents follow a defined process rather than improvising one.
- **Automated review.** A self-hosted review bot in Go that reviews pull requests against repository-specific rules.
- **Knowledge base.** A structured description of machines, environments and danger zones that agents read before acting.

### Stack

- **Backend:** Go (Connect RPC, NATS, ent, sqlc), PostgreSQL, TypeScript and Node
- **Frontend:** React (TanStack Router and Query), TypeScript, Flutter and Dart
- **Testing:** Go test with Testcontainers, k6, Playwright, Flutter test
- **Infrastructure:** Docker, Terraform, Ansible, Proxmox, Linux

### On the side

- **Homelab.** Proxmox virtual machines (Home Assistant, media server, reverse proxy, game servers) provisioned with Terraform and cloud-init.
- **Shot tracker.** A do-it-yourself aim tracker for 10 m air pistol: camera firmware in C on an ESP32-P4, analysis tooling in Go.

My professional and personal work lives in private repositories. The public ones here are mostly exercises from my 2022 training.

[LinkedIn](https://linkedin.com/in/theode)
