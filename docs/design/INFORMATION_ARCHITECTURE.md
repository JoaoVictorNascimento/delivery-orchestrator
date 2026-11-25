# Information Architecture

## Navigation

| Group | Module | Proposed route |
|---|---|---|
| Workspace | Overview | `/` |
| Workspace | Deliveries / Delivery Details | `/deliveries`, `/deliveries/:deliveryId` |
| Workspace | Action Center | `/actions`, `/actions/:actionId` |
| Engineering | Execution Inspector | `/executions`, `/executions/:executionId` |
| Engineering | Findings & Corrections | `/findings`, `/findings/:findingId` |
| Engineering | Pipeline Monitor | `/pipelines`, `/pipelines/:pipelineId` |
| Engineering | Agents | `/agents`, `/agents/:agentId` |
| Intelligence | Knowledge | `/knowledge`, `/knowledge/:entryId` |
| Intelligence | AI Usage & Efficiency | `/ai-usage` |
| Intelligence | Insights | `/insights` |
| System | Projects | `/projects`, `/projects/:projectId` |
| System | Integrations | `/integrations`, `/integrations/:integrationId` |
| System | Settings | `/settings` |

These are route proposals, not finalized contracts. Deliveries registry is part of the Deliveries module, not an additional separately approved high-fidelity screen. Tabs and selected entity should support deep links where useful. Use opaque identifiers scoped to project; do not expose local paths or secrets in URLs.

## Ownership and boundaries

Overview summarizes; Delivery Details shows business workflow; Execution Inspector shows technical execution; Findings tracks issues; Pipeline Monitor explains CI impact and recovery; Agents describes roles; Knowledge manages evidence-backed rules; AI Usage measures consumption and experiments; Insights measures delivery outcomes; Projects configures local repositories and overrides; Integrations diagnoses providers; Settings holds global defaults. Action Center owns all dashboard decisions. Chat and UI submit to the same action gateway. No in-app code editing, diff viewer, terminal, file explorer, debugger or chat clone.

## Cross-links

Delivery → current step execution, findings, pipeline, pending action, knowledge and usage. Finding → original source reference, correction execution, commit and action. Pipeline → failed job, diagnosis, recovery execution, SHA and delivery. Agent → registered integration, execution history and usage. Knowledge → source finding, project, evidence, approval action. Scatter point → execution or delivery as applicable. External links open only when supported and validated, otherwise display/copy safe references.

## Shared shell

Global language Select with SVG flag plus language name (not switch), theme control, search/command palette (`Cmd/Ctrl+K`), sidebar collapse, connection freshness, demo label and project context. Route changes retain valid project context; filter reset is explicit. No fake navigation to missing pages. Show active route and contextual breadcrumb. Scope all queries and selected entities by project.
