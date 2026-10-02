# UI/UX Overhaul — Changed Files

Visual system and responsive layout only. No auth, Firebase, AI, or game-logic changes.

| File | Changes |
| ---- | ------- |
| `index.html` | Removed PERIMETER ENERGY spinning conic-gradient / rotating rim effects on cards, hero, pins, links, logo, page frame. Replaced with static academic design tokens (border, shadow, radius, colors). Coherent type scale via clamp(). Progressive breakpoints (≤480 / 481–767 / 768+ / 1024+ / 1280+ / 1600+). Desktop max-width 1280–1400px centered. Multi-column grids for officers, stats, shortcuts, hero. Arena question area max-width on desktop. Quieter matrix ambient. Reduced blur. Guest-role links kept functional without animated rims. |
| `dashboard.html` | Static background (no continuous gradient animation). Wider max container (1200–1280px). Overview stats grid responsive. Softer glass/shadow. Mobile input zoom prevention retained. |
| `CHANGED_FILES.md` | This summary. |

## Unchanged
`game.js`, `sw.js`, `manifest.webmanifest`, icons, `logo.png`, `package.json`, `vercel.json`, all `api/*` — behavior and paths preserved.
