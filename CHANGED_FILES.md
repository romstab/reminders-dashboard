# Correction Pass — Changed Files

Only regressions from the previous UI/performance update were fixed.
No redesign, no Firebase path changes, no auth/AI/arena logic changes.

| File | Correction |
| ---- | ---------- |
| `game.js` | Restored valid `signalPushToSection()` (was corrupted mid-string into `listenPushSignal`). Removed leftover `}, 45000)` polling remnant. Replaced ignore-on-hidden with real subscribe/unsubscribe: `startPushSignalListener` / `stopPushSignalListener` on `visibilitychange` (bound once). Unified postMessage type to `SHOW_UPDATE` to match `sw.js`. |
| `sw.js` | Added `icon-maskable-192.png` and `icon-maskable-512.png` to precache. Bumped cache to `bscs1a-rst-hub-v5`. |
| `CHANGED_FILES.md` | Updated for this correction pass. |

## Unchanged in this pass
`index.html`, `dashboard.html`, `manifest.webmanifest`, icons, `logo.png`, `package.json`, `vercel.json`, all `api/*` files.
