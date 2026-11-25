# Accessibility and UX Validation

Target WCAG 2.2 AA; compliance is not yet audited. This is an acceptance plan, not a certification.

| Area | Required checks |
|---|---|
| Keyboard | All controls, filters, dialogs, tabs, selects and actions reachable; visible focus; no traps; logical order; Escape closes overlays |
| Semantics | Landmarks, heading hierarchy, native buttons/inputs, table headers, accessible names and appropriate ARIA |
| Contrast | Verify exact light/dark preset tokens; normal text ≥4.5:1, large text ≥3:1, relevant non-text controls ≥3:1; no color-only status |
| Workflow | Keyboard/selectable stage list as alternative to canvas drag/zoom; current stage and reason announced |
| Charts | Text summary and accessible data table; keyboard equivalent to tooltip/drill-down; patterns/labels or legends for series; missing distinct from zero |
| Forms | Explicit label, required state, error association and validation; disable repeat submission, not necessary rejection |
| Live updates | Polite status announcements; no focus theft or endless live spam; pause live tail; reduced-motion preference |
| Layout | 200% zoom, long identifiers and Portuguese expansion; narrow desktop; scrollable inspector and tables without hiding actions |
| Preferences | Language flags have text names; theme system preference respected; persistent settings |
| Safety | Confirmation for consequential actions; stale/expired decisions disabled; external destination indicated |

Run automated accessibility checks (e.g. axe with Playwright) plus keyboard and screen-reader smoke tests; automated scans are not sufficient. Capture findings by screen, locale, theme, severity, reproduction and resolution. Verify common states and no unexpected focus movement. Document exceptions with owner and resolution plan; critical blockers must be resolved before M02 acceptance. Browser regression remains open for prototypes where Chromium did not render; syntax validation alone is not proof of interaction correctness.
