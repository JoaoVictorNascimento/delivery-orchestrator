# Brand Guidelines

**Status:** Concept and raster brand board accepted. Vector production candidate v1.0 delivered for final visual sign-off. Exact UI preset token verification pending.

## Identity

Product name: **Delivery Orchestrator**. Descriptor: Engineering Control Center. Brand-board tagline: **AI-powered software delivery**. Geometric rounded hexagon and converging layered forward-flow forms evoke a stylized D, orchestration, coordinated delivery and governance. Keep the symbol recognizable independently of the wordmark. The accepted raster board is the visual reference; it is not proof of an editable SVG.

## Palette

| Brand color | Brand HEX | Usage |
|---|---|---|
| Amber | `#F79600` | Signature accent, mark and emphasis |
| Deep Amber | `#B24700` | Secondary brand accent |
| Taupe | `#9F8E84` | Supporting neutral |
| Warm Cream | `#F7F3EE` | Light brand backgrounds |
| Espresso | `#2B1F1A` | Dark brand backgrounds |

These are the brand colors from the design discussion, not verified exported shadcn semantic tokens. Use the actual `b1Ha08Wri` preset for functional UI colors and contrast. Do not use raw brand amber for every primary text or status.

## Typography and iconography

Raleway is the approved heading/body/wordmark direction; Lucide is the UI icon set. JetBrains Mono is the proposed technical typeface for logs, identifiers and branches, subject to final confirmation and license review. Use a practical fallback stack when fonts are unavailable. Do not distribute container fonts. Preserve brand geometry and legibility in both themes.

## Logo variants and usage

Deliver master vector, light/dark lockups, horizontal/stacked, symbol-only and monochrome black/white, with transparent PNG exports. Preserve aspect ratio; no stretching, recoloring outside approved variants, additional shadows, unrelated gradients or busy backgrounds. Clear space: at least one quarter of symbol height around the mark or lockup. Minimum recommended symbol size: 24 px; use the dedicated favicon at 16 px. For horizontal lockups, use the no-tagline variant below 360 CSS px width; below 180 px prefer the symbol. These are proposed production rules, subject to visual sign-off and accessibility testing.

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

## Production asset notes

- `logos/logo-horizontal-light.svg` is the primary transparent lockup for light surfaces; use `logo-horizontal-dark.svg` for dark surfaces. Stacked, no-tagline, pure black and pure white variants are provided. The words are outlined paths traced from the accepted raster wordmark, not live Raleway text. This preserves its appearance without distributing or requiring fonts. The symbol is manually reconstructed with SVG curves and rounded strokes.
- `#FFB86C` is the ribbon highlight; `#FFA52F` is a logo-only gradient endpoint. Neither is a new semantic UI token. The light tagline is a decorative brand element, not a substitute for accessible body text.
- `icons/symbol-color.svg` is the transparent standalone mark. Use app-icon variants for app surfaces, and favicon assets for browser tabs. The smallest icons intentionally use a dark tile for consistent contrast.
- The PNG lockups are exported at their SVG viewBox dimensions. For larger raster output render the SVG at the required dimensions.
- Social assets include GitHub preview/avatar, README banner, LinkedIn, Open Graph and wallpaper; SVG and PNG are provided.
- Do not stretch, rotate, add effects, change ribbon order, place on low-contrast backgrounds, or reuse the brand colors as status colors. Use the monochrome variants for single-color applications.
- UI type remains Raleway; JetBrains Mono remains proposed. No font files are distributed. Brand-board headings use system fallback fonts.
- The original approved raster references are included for comparison, not as production vector assets.
- SVGs were parsed and rendered to PNG; icon and social dimensions were checked. Final product integration, exact preset export, and user approval remain pending.
