# Screen specifications

| Screen | Content | Interactions | PRD |
|---|---|---|---|
| Overview | Active deliveries, attention queue, recent events, connection freshness | Open delivery, filter projects, open actions | FR-19,21 |
| Delivery Details | Source/target, MR, current cycle, graph, history, local vs published vs CI SHA | Select cycle/node, open inspector, pause/resume request | FR-10,18,19,22 |
| Action Center | Branch choices, correction plan, diff snapshot, tests, exceptions and learning | Explicit confirm/reject with reason; stale action disabled | FR-07,14,17,20 |
| Execution Inspector | Task, actor, start/end, duration, sanitized logs, inputs/outputs, evidence | Filter events, copy safe ID, inspect failure | FR-04,05,12,19 |
| Deliveries list | Search, status/project filters, timestamps | Open detail | FR-21 |
| Findings | Source, severity, file/line, disposition, plan, evidence | Inspect, filter, request authorized disposition | FR-11 |
| Pipelines | SHA, jobs, logs, retry history and diagnosis | Inspect job, authorized retry | FR-12 |
| Agents | Provider, real execution, availability and failures | Inspect, resume instructions | FR-02,23 |
| Knowledge | Project-scoped rules, candidates, provenance, version | Approve/reject, rollback with confirmation | FR-17 |
| Projects | Repository and governance profile | Edit rules/commands, validate | FR-01 |
| Integrations | GitLab, Finding, Cursor/Codex diagnostics | Test connection, safe configuration | FR-23 |
| Settings | Theme, intervals, budgets, autonomy | Save validated settings | FR-23 |
| Insights | Period, baseline, denominators and missing data | Filter and compare | FR-24 P1 |

## Common states
Loading: preserve shell and show skeleton. Empty: explain absence and show appropriate next action. Error: safe explanation, retry and correlation ID. Offline/stale: retain last known snapshot with timestamp; disable decisions until revalidated. Pending action submission: disable duplicate clicks; only show accepted after server acknowledgement. Demo: permanent label and no real writes. No unsolicited chat continuation assumed.

## Acceptance
Keyboard-accessible navigation and actions; both themes; current stage and reason visible without color; historical cycles retained; latest published SHA distinguished from local changes; stale approvals blocked; empty/loading/error/stale states; synthetic demo never modifies real repos. Detailed secondary screen prototypes remain follow-up work.
