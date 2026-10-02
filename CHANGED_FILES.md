# Hero overlap fix + Matrix background restore

## Files changed

| File | Changes |
| ---- | ------- |
| `index.html` | Fixed logo/title overlap; restored Matrix rain as page background only; kept card spinning lights disabled |
| `CHANGED_FILES.md` | This summary |

## Exact cause of logo/title overlap
1. The logo `<img>` used inline `transform: scale(1.4)`, drawing 40% outside its circular shell into the title column.
2. Conflicting CSS forced `.hero-top` to `grid-template-columns: 84px 1fr !important` while desktop logo was `112px`, so the logo overflowed the grid track into the title.

## Exact fix
1. Removed `scale(1.4)`; logo image now `object-fit: contain` inside a circular shell with `overflow: hidden`.
2. `.hero-top` is CSS Grid: `auto minmax(0, 1fr)` so the logo column sizes to the logo and the title column gets the remaining space with `min-width: 0`.
3. Responsive logo sizes: 72px (≤380) → 88px → 104px (tablet) → 120px (desktop). Title uses `clamp()` and normal wrapping.

## Matrix background
- Re-enabled `matrixFall` animation on `.matrix-col`.
- Layer: `position: fixed; z-index: 0; pointer-events: none; opacity ~0.14`.
- Content (`nav`, `hero`, `main`, cards) at `z-index ≥ 1` with opaque dark panels so rain stays **behind** boxes.
- Not inside cards; no conic-gradient / rotating rims restored.
- Reduced motion: animation off, low static opacity. Hidden tab: `animation-play-state: paused`.

## Still disabled
- Rotating card perimeter lights
- `conic-gradient` rims
- `hubRotate` / spinning `::before`/`::after` on cards
