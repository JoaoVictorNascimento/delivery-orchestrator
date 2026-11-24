# Design system — v0.1 (proposal)

Engineering Control Center: compact, calm, evidence-oriented. English UI; keep strings localizable. Desktop-first, responsive down to 768px with collapsed navigation; smaller screens use stacked panels. No decorative charts on operational pages.

The Delivery Orchestrator must use the official shadcn/ui preset as its visual foundation.

### Preset configuration

- Preset: `b1Ha08Wri`
- Style: Rhea
- Base color: Taupe
- Theme: Amber
- Chart color: Amber
- Heading font: Raleway
- Body font: Raleway
- Icons: Lucide
- Radius: Small
- Themes: Light and Dark

### Implementation rules

- Use shadcn/ui and Tailwind CSS as the primary UI foundation.
- Do not introduce Ant Design or another competing component library.
- Preserve the original preset configuration and semantic design tokens.
- Do not hardcode theme-dependent colors inside feature components.
- Support light and dark themes consistently.
- Prefer existing shadcn components before creating custom primitives.
- Build reusable domain-specific components on top of shadcn.
- Use React Flow for interactive workflow visualization.
- Use JetBrains Mono for code, logs, commit hashes and technical identifiers, subject to final typography validation.
- Use color primarily to communicate meaningful states.
- Never rely exclusively on color to communicate execution status.
- Prioritize progressive disclosure, visual clarity and information hierarchy.
- Keep the workflow canvas as the primary visual element of delivery details.
- Use Linear, n8n, Raycast, Vercel and Grafana as interaction and information architecture references.
- Use GitLab only as a functional reference for merge requests, pipelines and delivery processes, not as a visual reference.
- Validate every screen in both themes before considering a UI milestone complete.