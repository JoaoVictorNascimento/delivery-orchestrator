# Brand Guidelines

**Status:** Concept and brand board accepted. Final vector asset production and exact color verification pending.

## Identity

Product name: **Delivery Orchestrator**. Descriptor: Engineering Control Center. Brand-board tagline: **AI-powered software delivery**. Geometric rounded hexagon and converging layered forward-flow forms evoke a stylized D, orchestration, coordinated delivery and governance. Keep the symbol recognizable independently of the wordmark. The accepted raster board is the visual reference; it is not proof of an editable SVG.

## Palette

| Brand color | Working HEX | Usage |
|---|---|---|
| Amber | `#F79600` | Signature accent, mark and emphasis |
| Deep Amber | `#B24700` | Secondary brand accent |
| Taupe | `#9F8E84` | Supporting neutral |
| Warm Cream | `#F7F3EE` | Light brand backgrounds |
| Espresso | `#2B1F1A` | Dark brand backgrounds |

These are working brand colors from the design discussion, not verified exported shadcn semantic tokens. Use the actual `b1Ha08Wri` preset for functional UI colors and contrast. Do not use raw brand amber for every primary text or status.

## Typography and iconography

Raleway is the approved heading/body/wordmark direction; Lucide is the UI icon set. JetBrains Mono is the proposed technical typeface for logs, identifiers and branches, subject to final confirmation and license review. Use a practical fallback stack when fonts are unavailable. Do not distribute container fonts. Preserve brand geometry and legibility in both themes.

## Logo variants and usage

Deliver master vector, light/dark lockups, horizontal/stacked, symbol-only and monochrome black/white, with transparent PNG exports. Preserve aspect ratio; no stretching, recoloring outside approved variants, additional shadows, unrelated gradients or busy backgrounds. Proposed clear space: at least one quarter of symbol height around lockup; validate after vector reconstruction. Proposed minimum symbol size 16px (test at 16/32/48); omit tagline when illegible. Treat these measurements as production candidates, not measured specifications of the raster board.

## Brand kit acceptance

| Asset | Target |
|---|---|
| `assets/brand/logos/` | Editable path-based SVG and transparent PNG variants |
| `assets/brand/icons/` | Symbol, app icon, favicon SVG/ICO and 16/32/48 raster variants |
| `assets/brand/social/` | GitHub preview 1280×640, avatar 512×512, README banner 1600×400, LinkedIn 1200×627, OG 1200×630; optional wallpaper 1920×1080 |
| `assets/brand/guidelines/` | Accepted board, finalized usage rules |
| `assets/brand/tokens/` | Brand JSON/CSS and documented relationship to UI tokens |

App icon target: 1024×1024. Verify transparency, shape fidelity, small-size readability, theme contrast and no embedded bitmap masquerading as vector. Use synthetic project data in promotional materials. Do not change repository license or publish corporate assets.

## Brand voice

Precise, calm, concise and evidence-oriented. Explain current state, next action and uncertainty; no inflated claims of autonomy or invented outcomes. English documentation; bilingual product UI.
