# Roadmap

All milestones are planned unless explicitly marked as draft or accepted. Versions are proposed and may change; they are not published releases.

| Milestone | Deliverable | Status |
|---|---|---|
| M00 | Product vision, requirements and success metrics | Draft available |
| M01 | Public repository foundation | Draft available |
| M02 | Information architecture, design system, interaction flows and high-fidelity prototype | Planned |
| M03 | Domain model, glossary, invariants, state machine and events | Planned |
| M04 | C4 architecture, security model, ADRs and technical discovery | Planned |
| M05 | Shared contracts, ownership, agent plan and worktrees | Planned |
| M06 | Parallel implementation of core, persistence, integrations, MCP, worker, dashboard and learning | Planned |
| M07 | Integration, independent QA, failure recovery and security tests | Planned |
| M08 | Authorized real-world validation and dogfooding | Planned |
| M09 | Public demo, installation, documentation and release | Planned |

## Technical discovery gates

Validate shared skill discovery, local MCP, agent CLI execution and continuation, GitLab review completion and permissions, approval from dashboard, durable recovery, SSE or equivalent event streaming, and Finding integration. Use synthetic data first. No unverified capability may be presented as implemented.

## Proposed release progression

Foundation → Delivery Core → Feedback Loop → Control Center → Resilience → Intelligence → Integrations → Demo → Release Candidate → v1.0. Foundational safety and recovery must exist before real writes, regardless of release labels.

## Next milestone acceptance

UX & Product Design: screen specifications for Overview, Delivery Details, Action Center and Execution Inspector; both themes; empty/loading/error/stale states; review loops; explicit human decisions; approved navigation and interaction flows.
