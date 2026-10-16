# The Era booth — brand spec (kiosk skin)

A second brand skin for the **PÓZE buồng chụp** kiosk prototype. Same
components, same 11-screen flow, same 1920×1080 layout as the default Poze
skin — only the token layer + type posture change, bound as
`html[data-brand="the-era"]` in `index.html`.

Switch by appending `?brand=the-era` to the URL:

```
index.html                    → default PÓZE skin
index.html?brand=the-era      → The Era booth skin
```

Authoring brief: `The Era booth`, palette beige + light wood, modern type,
Poze-style function screens, no AI slop.

## One-sentence system

Warm beige canvas, light-wood surfaces used structurally (nav pills, active
chips, recessed panels), one deep-caramel accent, and a single modern
geometric sans (Manrope, weight-driven) — no condensed or rounded display
face.

## Color tokens

| token | value | role |
|---|---|---|
| `--bg` | `#f3ebdd` | beige kiosk canvas |
| `--bg-deep` | `#eadcc4` | recessed panels, chips, language toggle |
| `--wood` | `#c3a377` | light wood — structural surfaces |
| `--surface` | `#fbf7ee` | warm near-white cards, keypad keys, QR card |
| `--surface-2` | `#f0e7d6` | pressed / secondary cream |
| `--fg` | `#3a2c1d` | espresso text on beige |
| `--muted` | `#7c6647` | secondary text on beige |
| `--border` | `#ddcbb0` | hairline on beige |
| `--ink` | `#2b2014` | ink text on surface |
| `--ink-soft` | `#8a7458` | muted ink on surface |
| `--accent` | `#a9742f` | **deep caramel** — wordmark, headline, countdown ring, primary pill |
| `--accent-soft` | `#d9bd93` | light-wood tint — circular nav, active chips/frames |
| `--status-fg` | `#fbf7ee` | light text on green / red / blue status pills |
| `--ok` | `#3f9d6a` | continue / confirm (green) |
| `--warn` | `#c5452f` | retake / destructive (red) |
| `--info` | `#4f7aa8` | change-frame (blue) |

The printed-frame artwork palettes (`--t-*`) are content, not chrome — they
are **unchanged** between skins.

## Type

| token | stack | use |
|---|---|---|
| `--font-display` | `'Manrope', 'Be Vietnam Pro', system-ui` | headings, big numbers — weight **800** |
| `--font-round` | `'Manrope', 'Be Vietnam Pro', system-ui` | labels, pills, buttons, subheads |
| `--font-serif` | `'Manrope', 'Be Vietnam Pro', system-ui` | frame name bands |
| `--font-ui` | `'Be Vietnam Pro', system-ui` | body, keypad, form UI |
| `--font-mono` | `ui-monospace, 'SF Mono', Menlo` | prices, codes, order id |

Manrope carries Vietnamese, so the Poze display tier (Oswald condensed +
Baloo 2 rounded + Playfair serif) collapses to one face at heavy weight.
Hierarchy comes from **weight**, not from condensed/uppercase treatment —
so `.bi` is overridden to `text-transform:none; letter-spacing:-.02em`.

## Layout posture

1. **Light canvas, dark text** — every chrome token is remapped so text on
   beige and text on cream are both espresso/ink. No per-surface inversion.
2. **Wood is structural, not decorative** — the light-wood tint lives in
   `--accent-soft` (nav / active states), never as a text background or an
   arbitrary accent bar.
3. **One accent** — caramel carries the wordmark, the screen headline, the
   countdown ring, and the single primary pill. Status colors never decorate.
4. **Weight-driven hierarchy** — Manrope 800 for display, 700 for labels.
   No letter-spacing tricks, no condensed uppercase stack.
5. **Light chrome stays light** — `.flash` and `.qrbox` are pinned to light
   surfaces (the default uses `--fg`, which is dark on this skin); status
   pills / keys / scan-tab / dark nav take `--status-fg` so they keep light
   text over green / red / blue.

## Wordmark

Text lockup, no image: **The Era** in caramel Manrope 800 (`.brandword`),
with a lowercase muted **booth** descriptor (`.branddescr`). The default
PÓZE logo (`assets/poze-logo.png`) is hidden under this skin. Order/session
codes are prefixed `ERA-` instead of `MOC-`.
