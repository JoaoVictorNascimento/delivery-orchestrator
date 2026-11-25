# Design System

**Approved direction:** shadcn/ui, preset `b1Ha08Wri`, Rhea style, Taupe base, Amber theme and charts, Raleway headings/body, Lucide icons, Small radius. Both light and dark themes; system preference also supported. Exact preset tokens have not yet been extracted or verified.

## Visual principles

Linear: hierarchy and compact navigation; n8n: workflow canvas interactions; Raycast: command palette and keyboard productivity; Vercel: execution status/logs; Grafana: observability and timelines. Borrow interaction patterns, not logos or visual copies. Avoid GitLab-like clutter. Progressive disclosure: overview → selected entity → evidence, only as needed. Use amber sparingly for actions and focus; semantic colors with text/icon for status. No decorative badges or redundant cards.

## Frontend direction

| Layer | Choice |
|---|---|
| Application | React + TypeScript + Vite |
| UI | shadcn/ui + Tailwind CSS, official preset |
| Routing | React Router |
| Workflow | React Flow |
| Charts | Recharts / shadcn Charts; custom SVG heatmap |
| Data | TanStack Query, TanStack Table where appropriate; Zustand for local UI/demo state |
| Locale | i18next, react-i18next, ICU, Intl |
| Transport (production candidate) | REST + SSE, reconnect/reconciliation |
| Tests | Vitest and Playwright |

Dependency versions, underlying primitives, licenses and runtime contracts remain subject to M04 ADRs. Use official preset tooling, inspect generated theme variables and lock dependency versions. Do not substitute a hand-made palette as the actual preset. JetBrains Mono for technical text is proposed, not separately accepted.

## Component patterns

| Pattern | Usage |
|---|---|
| App shell | Collapsible grouped sidebar, persistent header, breadcrumb, search/command palette, language select and theme control |
| Page header | Title, short purpose, context and relevant actions |
| KPI row | Up to four high-value metrics per analytic view; clickable only when filterable |
| Registry / inbox | Compact searchable/filterable list or table; selection preserved by stable ID |
| Inspector | Contextual right panel, resizable where useful; tabbed detail; close/focus behavior |
| Workflow canvas | Pan, zoom, fit, minimap, focus active, cycle selector and keyboard/list alternative |
| Trace waterfall | Measured spans, hierarchy, duration, errors and explicit unknown intervals |
| Decision form | Explicit context, evidence, choices and submission; single action ID |
| Chart | Responsive axes, labels, legend, tooltip, table alternative and coverage |
| Settings | Grouped sections; validation, save/discard, safe export/import |

Use semantic CSS variables (`background`, `foreground`, `card`, `muted`, `border`, `primary`, `ring`, chart tokens, etc.) and theme-safe status tokens. Use a consistent spacing scale, dense technical lists, visible focus and accessible contrast. Preserve full values through tooltips/copy where truncation is needed. Layout must accommodate longer Portuguese strings and narrow desktop widths. Avoid using color alone or linear progress percentages for cyclic delivery.

## Shared states

Loading: shell and skeleton; empty: explicit reason and appropriate action; error: sanitized description, retry and correlation ID; stale/disconnected: last observed timestamp, stale marker, reconcile before mutation; unavailable: Not reported/Not supported/Not verified as appropriate; pending mutation: prevent duplicate submissions and wait for acknowledged outcome. Demo: persistent visible label, isolated state, no real writes. All states bilingual and theme-aware.

## Integration and verification

Use shared shell, reusable components and a single synthetic entity store in unified prototype. Verify against accepted individual prototypes rather than reimplementing every layout independently. Theme, language, filter and route changes must preserve relevant context. Production state is backend-owned, not browser localStorage. See [accessibility](ACCESSIBILITY.md) and [visualization](DATA_VISUALIZATION.md).
