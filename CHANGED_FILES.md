# Matrix digital rain — real animated canvas

| File | Change |
| ---- | ------ |
| `index.html` | Replaced static DOM matrix host with `<canvas id="matrixCanvas">`; CSS for fixed full-viewport canvas behind content |
| `game.js` | Replaced DOM column matrix with canvas `requestAnimationFrame` digital rain (independent streams, trails, speeds) |
| `CHANGED_FILES.md` | This summary |

## Implementation
- **ONE** full-viewport canvas, `position: fixed`, `z-index: 0`, `pointer-events: none`
- **ONE** `requestAnimationFrame` loop drawing falling glyphs
- Columns = independent drops with random speed, trail length, reset
- Character set: katakana + hex digits
- Trail via translucent dark wipe each frame + bright head glyph
- Resize debounced; pause on `document.visibilityState !== "visible"`
- `prefers-reduced-motion`: static field, no continuous animation
- Density capped by viewport (mobile fewer columns)

## Preserved
- Hero logo/title separation
- No rotating card lights / conic rims
- Auth, Firebase, arena logic, SW unchanged
