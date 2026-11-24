# Product Vision

**Version:** 0.2 | **Date:** 2026-11-24 | **Status:** Proposed public baseline

## Vision and mission

Make software delivery an intelligent, observable and supervised process in which developers delegate operational work without losing control over consequential decisions. Reduce the human effort required to bring existing code changes to a merge-ready merge request through agent orchestration, governance, feedback and validated learning.

## Problem and audience

Coding agents automate individual tasks while developers still coordinate reviews, commits, publication, comments, CI and corrections. Fragmentation creates context switching and repeated mistakes. The initial audience is individual developers using Cursor or Codex with GitLab; engineering teams are a potential future audience, not a multi-user commitment.

**Job to be done:** After implementing a change, delegate its preparation and follow-up until it is ready to merge, intervening only when necessary.

**Differentiation:** A closed feedback loop combining governance, human oversight, traceability and project-specific accumulated knowledge. This is knowledge management around existing models, not model training.

## Approved product principles

1. Local-first control state; remote integrations only as needed.
2. Hybrid chat and dashboard interface.
3. Light and dark dashboard themes.
4. Real-time workflow visibility.
5. Complete execution history, subject to safe retention.
6. Multiple projects and deliveries.
7. Central human action inbox.
8. Project-isolated learning.
9. Cursor and Codex compatibility.
10. No automatic merge.
11. No mandatory additional paid services.
12. Recovery of interrupted deliveries.

## Public project principles

Open-source by design, provider-independent interfaces, privacy-first defaults, extensible architecture, English public documentation and reproducible synthetic demonstrations. Corporate knowledge, credentials, code, logs and runtime data must not enter the public repository. Corporate use and publication require appropriate rights and authorization.

## Experience and scope

Start from existing changes on a working branch. Review and validate locally, create granular commits, request explicit target selection, publish and monitor the MR. Analyze external feedback and CI failures, implement corrections, request functional validation and repeat. Show current status and evidence through chat and dashboard. Process approved learning after merge readiness and generate a final report.

Merge readiness requires current review evidence, required approvals, required discussions addressed, successful required CI and no known merge blocker. Completion also requires learning disposition and reporting. The product does not replace GitLab policies, human reviewers or CI; it does not implement entire Jira stories, merge, deploy, train models, or promise operation while the computer is off.

## Success and evolution

Primary metric: Human Touch Time, measured active human involvement rather than waiting. Complementary metrics: lead time, intervention count, review cycles, first-pass rate, recurring findings, local prevention, CI failures and provider-reported AI usage. Establish a manual baseline and compare similar changes before setting targets.

Validate first with disposable repositories and a synthetic GitLab environment, then authorized real deliveries. The full architecture is the chosen direction; individual technologies and guarantees require ADRs. Broader engineering orchestration, Jira and multi-user collaboration remain future possibilities.

## Risks and assumptions

Agent continuation and invocation depend on actual provider capabilities; manual resume is acceptable. Review completion requires reliable evidence or explicit authorized human confirmation, never silence. Existing AI and CI quotas may apply. Learning must be auditable, approved and reversible. Local-first does not imply that remote AI providers never receive code; their data handling must be documented and authorized.
