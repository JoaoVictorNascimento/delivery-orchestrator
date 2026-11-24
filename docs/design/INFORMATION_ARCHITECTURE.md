# Information architecture

Workspace: Overview, Deliveries, Action Center. Engineering: Findings, Pipelines, Agents. Intelligence: Knowledge, Insights (P1). System: Projects, Integrations, Settings. A persistent header shows current workspace, connection freshness, demo mode and theme. Global pending-action count links to Action Center.

Routes (proposed): /overview, /deliveries, /deliveries/:id, /deliveries/:id/executions/:executionId, /actions, /findings, /pipelines, /agents, /knowledge, /insights, /projects, /integrations, /settings. Deep links retain delivery and cycle. Delivery detail is the canonical context; global lists cross-link rather than duplicate state.

Overview prioritizes blocked and human-required deliveries; no estimated completion percentage for cyclic workflows. Details default to current cycle, with past cycles read-only. Inspector exposes recorded tool actions and evidence, not private reasoning. Settings include per-project polling, limits, rules and theme. Public demo data is isolated and synthetic.
