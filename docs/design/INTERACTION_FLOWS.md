# Interaction flows

```mermaid
flowchart TD
 A[Start in chat] --> B[Inspect and review]
 B --> C[Commit plan and local checks]
 C --> D[Select target in chat or dashboard]
 D --> E[Push and create or recover MR]
 E --> F[Monitor review and CI]
 F -->|Findings or failure| G[Plan and implement corrections]
 G --> H[Local checks and human validation]
 H -->|Reject| G
 H -->|Approve exact snapshot| I[Re-review and publish]
 I --> F
 F -->|All current gates satisfied| J[Merge ready]
 J --> K[Learning approval and report]
 F -->|Timeout or fault| L[Pause or block]
 L -->|Resume and reconcile| F
```

Chat and dashboard share the same action ID and state. First valid decision wins; concurrent or stale submissions are rejected and refreshed. A branch change requires target-relative revalidation. Material changes after functional approval invalidate it. The dashboard shows resume instructions if the agent session is no longer active. No automatic merge. Approval of learning is separate from merge readiness.

Workflow nodes represent stages; executions are cycle-specific. Select a node to inspect recorded evidence. Monitoring may observe CI and review independently; a green pipeline alone never indicates completion. Display published SHA, CI SHA, local snapshot, pending gates and freshness. A completed cycle is immutable in the UI.
