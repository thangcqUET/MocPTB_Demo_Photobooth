# Mộc Photobooth — kiosk design system

Extracted from `Poze Overhead screen 1920x1080 v1` (visual style) with flow /
elements from `Mộc Photobooth app screenshot`. Canvas: fixed 1920×1080 kiosk,
scale-to-fit. Bilingual VI/EN.

## Color tokens (OKLch)

| token         | value                    | role                                   |
|---------------|--------------------------|----------------------------------------|
| `--bg`        | `oklch(38% 0.13 32)`     | deep burgundy kiosk canvas (textured)  |
| `--bg-deep`   | `oklch(30% 0.11 32)`     | vignette / pressed states              |
| `--surface`   | `oklch(95% 0.02 85)`     | cream cards, inputs, keypad panel      |
| `--fg`        | `oklch(100% 0 0)`        | white text on burgundy                 |
| `--ink`       | `oklch(21% 0.03 40)`     | dark text on cream / pill borders      |
| `--muted`     | `oklch(100% 0 0 / 0.72)` | secondary white text                   |
| `--border`    | `oklch(100% 0 0 / 0.18)` | hairlines on burgundy                  |
| `--accent`    | `oklch(70% 0.09 85)`     | gold — headings, prices, primary CTA   |
| `--accent-soft`| `oklch(83% 0.06 75)`    | soft gold — circular nav buttons       |
| `--ok`        | `oklch(64% 0.15 145)`    | continue / confirm (green)             |
| `--warn`      | `oklch(58% 0.19 30)`     | retake / destructive (red)             |
| `--info`      | `oklch(58% 0.07 255)`    | change-frame (blue)                    |

## Type

- **Wordmark / Didone serif** — `Playfair Display` (fallback Georgia). Gold, high contrast, tight tracking. Used for the brand lockup only.
- **Display / condensed** — `Oswald` (fallback `Arial Narrow`, Impact). All big kiosk headings, uppercase, tall condensed.
- **Rounded bold** — `Baloo 2` (fallback Segoe UI). Secondary bilingual labels under display headings.
- **UI / body** — `Nunito Sans` (fallback system sans). Dense app UI: frame picker, review, edit.
- **Mono** — system mono, tabular-nums. Prices, codes, IDs.

Bilingual rule: headings stack two lines — primary language at 1em, secondary at ~0.6em / 0.7 opacity. The VI/EN toggle flips which language is primary.

## Layout posture

- Full-bleed burgundy canvas with a fine noise grain overlay (SVG feTurbulence, ~6% opacity) + a soft darker vignette. No flat fills.
- Gold 4-point sparkle ornaments as the single recurring flourish — used once per screen, never on every heading.
- Navigation: circular gold (`--accent-soft`) buttons with a dark arrow; step-advance is always bottom-right, back is always bottom-left. Matches Poze.
- Primary CTA = white pill with a 2px `--ink` border (Pay cash, Pay with QR). Secondary = soft-gold pill.
- Content cards on the Mộc UI screens sit on cream (`--surface`) with `--ink` text and generous radii (14–20px).
- Numeric keypad: round cream keys, 3 columns; XÓA in `--warn`, OK in `--ok`.
- Accent budget: gold may appear as (1) the heading and (2) one CTA per screen. Status colors (green/red/blue) are functional, not decorative.

## Frame previews

Frames are CSS-drawn: a vertical strip with N photo slots and a decorative header/footer band carrying the frame name. Photo slots render either empty (cream) or a captured "simulated" scene (geometric backdrop + vignette), so the collage preview always reads as real.
