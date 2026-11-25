# M02.1 — Technical Feasibility

**Status:** Planned, no environment-specific PoC executed by this package. Documentation and prototype data are not evidence of installed capability. Run on authorized macOS environment, using synthetic/disposable repositories first and existing subscriptions where supported. No real remote mutation without permission.

| PoC | Procedure | Pass evidence / fallback |
|---|---|---|
| POC-01 Cursor CLI | Check installed version/help/auth; invoke harmless task using supported structured output, capture events | Redacted event sample and schema; otherwise manual executor |
| POC-02 Codex CLI | Check version/help/auth; run harmless task with supported JSON events | Redacted JSONL and exit result; otherwise manual |
| POC-03 Cursor hooks | Verify available hooks and scope on installed version; correlate registered session/tool events | Real hook events and correlation coverage; instrument own spans if unavailable |
| POC-04 GitLab MR/discussions | Read authorized test MR, comments, SHA, approval and permissions | Redacted fields and scope; REST fallback if MCP lacks fields |
| POC-05 CI | Read pipeline/jobs/logs for known SHA, check sanitized errors | Matching IDs/SHA/status; unknown state if restricted |
| POC-06 Reviewer completion | Observe real completion indicator, verify association with latest SHA, test silence | Explicit current-SHA evidence; block or authorized confirmation under policy if absent |
| POC-07 Token usage | Capture real counters from each authenticated executor; test cache semantics, cumulative vs incremental, retry/resume dedup | Reconcile sample totals and coverage; unavailable if not reported; no API purchase implied |
| POC-08 Finding | Inspect existing skill and rules, invoke against disposable known findings, require structured evidence | Schema/skill version/results; do not replace missing skill silently |
| POC-09 Resume | Interrupt and resume on same/different provider; verify state, no duplicate effects | Durable checkpoint and explicit continuation support; manual resume acceptable |
| POC-10 Human decision | Simulate shared action through UI/chat, duplicate and stale snapshot, rejection and reapproval | One decision, revalidation, no stale publication |
| POC-11 Local transport/recovery | Local MCP, REST/SSE disconnect, restart and replay, conflicting checkout | Recovered state, stale marker, deduplication and lock behavior |
| POC-12 Safe credentials | Validate least-privilege auth, redaction, local secret references, export | No secrets in outputs; fail closed on unauthorized action |

## Candidate commands (verify against installed version before execution)

`agent --help`, `codex --help`, `git --version`, `glab --version` where installed. Candidate structured modes: `agent --print --output-format stream-json` and `codex exec --json`; arguments, supported auth and output schema require verification. Avoid executing unknown hooks or scripts from remote data. Do not use paid API credentials as a substitute without explicit approval. Record command version, environment, date, result, sanitized sample, observed limitations, reproduction steps and fallback. Never include real corporate payloads in public docs.

## Integration choices to resolve

CLI vs SDK/App Server, editor-session continuation, MCP scope, direct GitLab REST/CLI vs MCP, review completion evidence, structured Finding contract, secure storage (macOS Keychain candidate), event/telemetry normalization and retention. Proposed architecture: local TypeScript/Node, explicit state machine/policy engine, Git engine, adapters, SQLite, worker polling without AI, MCP and shared skill, Fastify REST/SSE, React dashboard. These are candidate decisions for M03/M04, not implementation claims.

## Exit criteria

Every critical capability has evidence or documented safe fallback; no assumed reviewer completion, token counts, session resumption or write permissions. Test cases cover interruption and stale approval. Update DATA_AVAILABILITY_MATRIX.md with evidence references and installed versions. Record ADRs before final contracts and real writes.
