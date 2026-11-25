# Roadmap

**Updated:** 2026-11-25. Status reflects design approvals, not implementation, repository inspection or release verification.

| Milestone | Deliverable | Status |
|---|---|---|
| M00 | Product vision, requirements, success metrics | Accepted baseline |
| M01 | Public repository foundation | Accepted baseline; local repo not inspected |
| M02 | UX, brand, 13 screens, integrated prototype and design documentation | Individual screens accepted; consolidation open |
| M02.1 | Technical feasibility and data availability | Planned; can run alongside consolidation |
| M03 | Domain model, glossary, invariants, state machine and events | Planned |
| M04 | System design, C4, security, ADRs and verified integration choices | Planned |
| M05 | Shared contracts, ownership, agent orchestration and worktrees | Planned |
| M06 | Parallel implementation of core, persistence, integrations, MCP, worker, dashboard and learning | Planned |
| M07 | Integration, independent QA, recovery, security and accessibility tests | Planned |
| M08 | Authorized real-world dogfooding and baseline measurement | Planned |
| M09 | Public demo, installation, documentation and release | Planned |

## M02 completion gate

See [acceptance checklist](design/M02_ACCEPTANCE.md). The next deliverable is the unified interactive prototype. Preserve all accepted screen decisions; do not introduce a code editor or diff viewer. Reuse shared synthetic entities and decisions across screens. Apply the exact preset, finish brand assets and validate both locales and themes.

## Technical gate

[M02.1](research/TECHNICAL_FEASIBILITY.md) precedes closure of M04 and real write operations. Unknown capabilities must have explicit fallbacks. Run local and disposable-repository tests first; do not consume corporate credentials or write to real remotes without authorization.

## Release progression and priorities

Foundation → Delivery Core → Feedback Loop → Control Center → Resilience → Intelligence → Integrations → Demo → Release Candidate → v1.0. P0: safety, durable delivery, bilingual control center and conditional usage capture; P1: analytics and advanced filters/notifications; P2: automated experiments, optional optimization integrations, budgets and anomaly recommendations. Safety gates apply before any real writes regardless of release label. No promise of release dates or concurrent agent capacity.
