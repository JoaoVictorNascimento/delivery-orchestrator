# Screen Specifications

All 13 individual screen concepts/prototypes accepted on 2026-11-25. This is the normative design baseline; the unified prototype and implementation are pending. Every screen uses the shared shell, EN-US/PT-BR, light/dark/system, keyboard access, scoped project data, demo marker and common states. Data sources below are intended sources, not verified connections. Priorities follow the PRD.

## 01 — Overview (P0; FR-19, 21)

Purpose: answer how deliveries are progressing and where human attention is required. Header with project filter, command palette, language and theme. Compact KPI row (active, awaiting action, merge ready/completed, blocked as appropriate), delivery list, attention queue and recent activity. Filters by project/status and search; clicking a KPI filters the list. Select delivery for summary/inspector, navigate to Delivery Details; select pending action to open Action Center. Data: delivery state, action requests, external status observations, event history. Show last sync; no fake progress or stale success. Empty: onboarding or no matching deliveries.

## 02 — Delivery Details (P0; FR-03–18, 19, 22)

Purpose: current business workflow, reason for waiting and next action. Header with project, source/target branch, MR link, stage, pause/resume; summary of cycle, findings and validations. Central workflow canvas has Prepare & Publish, Review & Correct, Publish & Verify phases and visible review loop. Pan/zoom/fit, minimap, focus active, cycle selector, selectable nodes, contextual inspector and accessible list alternative. Tabs: Workflow, Activity, Commits, Findings, Pipeline, Learning. Display local snapshot, published SHA, CI SHA and evidence timestamps separately. Completed historical cycles are read-only. Human validation routes to the shared Action Center action, not separate approval. Pause/resume are requests acknowledged by backend, not cosmetic status changes. MergeReady distinct from Completed; external changes trigger reconcile. Never merge.

## 03 — Action Center (P0; FR-07, 14, 17, 20)

Purpose: single inbox for decisions across projects. Summary counts, searchable/filterable requests, selected request context and audited history. Types: target branch selection (real eligible remote branches, explicit confirmation), functional validation (summary, exact snapshot, automated checks, manual checklist, observations, approve or reject with reason), proposed finding dismissal/exception (evidence and bounded policy), learning candidate (scope and evidence). Required checklist gates approval, not rejection; rejection requires useful feedback. No editable code or embedded diff. Request state pending/approved/rejected/expired/superseded; stale and duplicate submission blocked. A decision only changes state after gateway acknowledgement; revalidate snapshot before publication. Show fallback instructions if agent cannot continue. All other screens link here.

## 04 — Execution Inspector (P0; FR-04, 05, 12, 19, 28)

Purpose: explain how a specific execution behaved using observable evidence. Execution selector, status/duration/operations/failures, trace waterfall and span inspector. Spans carry ID, parent, timestamps, duration, status, origin, related execution. Tabs: Logs, Tool Calls, Inputs & Outputs, Artifacts, Retry History. Search/filter severity and failures; live tail can pause; preserve historical events and sanitize exports. Click a span for its own evidence; show exit code, model/skill when reported, affected files as references and token counters if attributable. Only show measured operations; unknown inner spans must not be invented. Never expose hidden reasoning or credentials. Demo includes success, CI failure and monitoring scenarios. Link to related finding/pipeline/delivery and usage.

## 05 — Findings & Corrections (P0; FR-11–17, 32)

Purpose: track findings, assessments and verified resolution. KPI row total/open/resolved/recurring; searchable compact registry; filters project, delivery, cycle, severity, source, status. Inspector tabs Overview (assessment, correction plan, attempts, commit and attributable tokens), Evidence (file/line references, test results), History (events, recurrence, learning candidate). Sources include Finding, automated review and CI diagnosis; source comment is untrusted evidence. Distinguish confirmed, proposed dismissal, correcting, fixed locally, waiting validation, published, verified, authorized dismissal. Plan steps reflect workflow, not manual checkboxes. No editor, diff viewer or file browser. Use safe external references where supported. All exceptions route to Action Center. Resolution requires actual verification, not an agent assertion.

## 06 — Pipeline Monitor (P0; FR-10, 12, 16)

Purpose: delivery impact of CI and recovery rather than reproducing GitLab. Four summary indicators, pipeline registry by project/status, selected pipeline with delivery impact, stages/jobs and SHA. Tabs Diagnosis (selected job, failure classification, proposed next steps), Recovery (attempt history, evidence, reported usage), Evidence (job/pipeline link, SHA and validation). Search/filter/inspect; distinguish transient, code, infrastructure, existing or configuration failures. Authorized retries only through policy; avoid weakening checks. Green CI is necessary where required but not sufficient for MergeReady; stale pipeline SHA clearly flagged. Logs sanitized, source links conditional.

## 07 — Knowledge (P0; FR-17)

Purpose: reusable, evidence-backed project knowledge and Finding evolution. Four indicators for entries, active, awaiting review, superseded; search and filters by project/category/status. Inspector Overview (rule, rationale, scope, Finding application), Evidence (source delivery, finding, snapshot, validation), History (versions, approval, supersession/rollback). Candidate, active, rejected, superseded; approval via Action Center by default. Only approved version eligible for Finding; history retains exact version used. Deduplicate and avoid unsupported rules, allow rollback through authorized action; never auto-share across projects. Candidate approval does not hide MergeReady. No publication of corporate learning.

## 08 — AI Usage & Efficiency (P1 analytics; P0 collection; P2 runner; FR-28–30)

Purpose: measured consumption and quality-preserving optimization. Filters project/provider/period (7/14/30 days); optional model/skill/version grouping. Three tabs and exactly five selected chart types across them:

- Usage Overview: reported tokens, median observed delivery usage, cached input share, telemetry coverage; area chart daily tokens by provider; donut composition with selector for token categories/project/provider/workflow stage; compact recent execution table.
- Efficiency Analysis: heatmap weekday/hour token intensity; scatter duration vs tokens by execution with selection and link to inspector; show retry/wasted consumption and missing-data context without extra charts.
- Experiments: choose baseline and variant; radar of token efficiency, quality, speed, consistency, success rate; absolute comparison table, quality gate, configuration/snapshot/version/cache conditions and number of runs. Example RTK and Context Mode are fictional fixtures, not performance claims. Automated experiment runner deferred.

Filters recalculate all applicable metrics from same observations. CSV/JSON export sanitized. No fabricated costs, quotas, cache totals or findings attribution. See DATA_VISUALIZATION.md for metric definitions and normalization constraints.

## 09 — Agents (P0; FR-02, 23, 31)

Purpose: who executes work and what is available. Registry of configured roles (Finding, Correction, Pipeline diagnosis, Commit planner, Learning), provider, skill/model when known, project and state. KPIs configured/running/awaiting decision/unavailable; filter project/provider/status/search. Inspector Overview (role, active execution), Capabilities (verified/conditional/unavailable), History (executions and reported usage). Distinguish configured role from actual process; do not label idle provider as unavailable without evidence. No duplicated chat. Provider config lives in Integrations; per-project assignments in Projects.

## 10 — Projects (P0; FR-01, 21, 23)

Purpose: register local repositories and enforce project boundaries. Registry, search, add/edit, configured/setup required/paused state. Tabs Repository (name, local path, remote, rules location, validation commands), Policies (eligible target patterns, bounded retries, language overrides, locked safeguards), Agents (role assignments and provider/manual fallback), Knowledge (isolated scope and policy). Detect repo metadata when possible; validate paths, remote identity, commands and eligibility. Store config safely; do not run commands or connect merely by typing. Prevent conflicting writes to same checkout. No cross-project knowledge sharing by default. Project settings override only permitted global defaults.

## 11 — Integrations (P0; FR-23, 31)

Purpose: configure and diagnose external connections. Registry Cursor, Codex, GitLab REST and optional MCP servers; status connected/limited/setup required/unavailable. Tabs Overview (connection method, version, auth reference), Capabilities (verified, conditional, unavailable, unknown), Diagnostics (timestamp, results, safe remediation). Test connection and Run all checks; read-only checks by default, explicit confirmation for paid/side-effectful probes. Reuse local provider auth when supported; secret references only; never expose tokens or accept real credentials in demo. Propagate capability limitations to other modules. Evidence per environment/version, not blanket support claims.

## 12 — Insights (P1; FR-24)

Purpose: delivery outcomes, engineering quality and autonomy, not token consumption. Filter by project and time period 7/14/30 days. Delivery Performance: merge ready count/rate, median elapsed and waiting time; area chart started vs ready, donut outcomes, scatter elapsed vs human wait. Engineering Quality: total/recurring findings, first-pass rate, deliveries without recurrence, project comparison. Agent Autonomy: automated steps, human decisions, automation share, decisions per delivery, radar of observed rates with absolute values. Use comparable cohorts and denominators; active vs wait distinct; fewer findings alone not proof of quality. Do not optimize away required approvals. Missing information explicitly shown.

## 13 — Settings (P0 core; FR-23, 25, 27)

Purpose: global preferences, not project-specific policy or integration credentials. Sections General (interface, timezone, agent/commit/MR/report language), Appearance (light/dark/system preview), Workflow (timeouts, retry limits, monitoring, locked safeguards), Notifications (pending action, failure, merge ready, learning), Data & Privacy (telemetry, log/artifact retention, required sanitization and isolation), Advanced (safe JSON import/export, storage diagnostics, restore defaults). Validate fields and imports; save/discard, persistent preferences, clear errors, confirmation for destructive resets. Proposed defaults: execution timeout 30m, max automatic retries 3, poll 60s; preserve separate review window/cycle/transient retry policy pending M03/M04. Notifications internal initially. No credentials in export; restoration never disables safety.

## Acceptance for each screen

Render all supported themes/locales; verify actual controls and selected-entity consistency, loading/empty/error/stale/unavailable states and keyboard interaction. Demonstrate cross-module links using shared IDs and state. Every write simulated in demo; no real repo mutations, network credentials or unverified provider assertions. See M02_ACCEPTANCE.md for integrated scenario coverage.
