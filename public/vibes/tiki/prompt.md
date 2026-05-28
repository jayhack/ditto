# Tiki — design kit prompt

Build a UI in the **Tiki** vibe: a carved-teal idol staring out of an acid
Hawaiian sunset, rebuilt for software. Where the older island themes are either
cute-rounded (dark plum cartoons) or 1970s screen-print cream, Tiki is the
**edgy, modern, minimalist, dark** cousin — volcanic-glass black, one electric
teal that glows, and a saturated sunset gradient rationed to identity moments.
The "acid trip" lives only in thin psychedelic line-swirls behind the hero, not
in the chrome of the app. It must read as a real, operational product first and
a poster second.

## Mood

Dusk on a lava field. A geometric carved tiki cut from glowing turquoise stone
faces a sun melting through gold → coral → hibiscus → orchid before it drowns in
obsidian. Psychedelic swirls ripple at the edges like heat-haze. The feeling is
**after-dark, electric, restrained** — a tiki bar run by people who also ship
dashboards. Loud color, quiet surfaces.

## Palette (exact, prescriptive)

- **Obsidian `#0B0712`** — base background (volcanic glass, faint purple-black).
- **Basalt `#17111F`** — panels, cards, inputs.
- **Tiki Teal `#16E6C4`** — THE accent: the idol, primary buttons, focus, the
  one neon. Use it sparingly so it stays electric.
- **Solar `#FFC24A`** — sun / gold, highest sunset stop.
- **Ember `#FF6A2C`** — lava / coral, mid sunset.
- **Hibiscus `#FF2E76`** — acid magenta pop / alerts.
- **Orchid `#7A2BE0`** — psychedelic purple, lowest sunset stop before night.
- **Moonlight `#F6ECDD`** — primary text / foam (warm off-white).

Text is Moonlight on Obsidian/Basalt. Teal and Solar take Obsidian text on top.

## Required gradients (named, exact)

- **Sunset** (identity, hero wash, progress):
  `linear-gradient(180deg, #FFC24A 0%, #FF6A2C 30%, #FF2E76 56%, #7A2BE0 80%, #0B0712 100%)`
- **Acid Card** (the card hero / poster moment):
  `linear-gradient(155deg, #0B0712 0%, #7A2BE0 26%, #FF2E76 48%, #FF6A2C 66%, #FFC24A 84%, #16E6C4 100%)`
- **Lava Panel** (dark surface with a hot floor):
  `linear-gradient(180deg, #17111F 0%, #0B0712 64%, #3A0F12 100%)`
- **Teal Glow** (the one neon halo): radial of `#16E6C4` at ~0.5 alpha fading to
  transparent, applied as `box-shadow: 0 0 28px rgba(22,230,196,0.45)` only.

## Typography

- **Display: `Space Grotesk`** (Google Fonts, weights 500–700). Modern and
  geometric but compact and readable — set tight, `letter-spacing: -0.02em`.
  Hero clamp(4rem, 12vw, 11rem). (Avoid wide/extended faces like Syne — keep
  the display narrow so large headings stay legible.)
- **Body: `Inter`** (400–700), system-ui fallback. Calm and legible for forms,
  tables, and dense data.
- **Mono: `JetBrains Mono`** (500–700) for telemetry, prices, codes, labels —
  uppercase, `letter-spacing: 0.14em` for eyebrow labels.

## Visual motifs

1. **The Tiki mark** — a *geometric, original* carved-idol SVG: a rounded head
   block with a notched brow bar, two concentric-disc eyes, a downward trapezoid
   nose, and a bared-teeth mouth, with stacked notches at the base. Stroke in
   Tiki Teal with one soft teal glow. This is the logo and the only figurative
   glyph. Build it from primitives — never paste a photo or a real ki'i.
2. **Acid swirl** — thin 1px concentric / spiral line ornament at 8–16% opacity,
   in a single hue, drifting behind the hero and as a corner flourish. This is
   the *entire* "acid trip" — keep it off functional surfaces.
3. **Sun-burst** — a flat sun disc with thin 1px radiating lines behind the
   hero, clipped by the horizon. One per page.
4. **Sunset ribbon** — the Sunset gradient as a vertical bar / progress meter /
   masthead wash; the recurring color event.
5. **Carved notch row** — a row of small teal triangles/notches (tapa-style)
   replacing every `<hr>`. Abstract carving, never a sacred pattern.
6. **Obsidian glass panel** — Basalt fill, 1px Moonlight/12 hairline border,
   6px radius, optional 1px teal top-edge. No cartoon rounding, no blur.
7. **Mono telemetry beacon** — `LUAU 19:30 · TABLE 06 · TIDE +1.2M` in
   JetBrains Mono uppercase.

## Components

- **Buttons** (6px radius, never full pills): primary = Tiki Teal fill +
  Obsidian text + Teal Glow shadow; secondary = transparent + 1px Tiki Teal/45
  border + Moonlight; acid/alert = Hibiscus fill + Moonlight text. Uppercase
  optional, tracking 0.06em.
- **Inputs**: Basalt fill, 1px `rgba(246,236,221,0.14)` border, 6px radius;
  focus = Tiki Teal border + `0 0 0 3px rgba(22,230,196,0.25)` ring.
- **Cards**: Obsidian glass panels; data cards get a 1px teal top-edge, never a
  soft drop shadow (only the teal glow and the tiki mark glow).
- **Badges/pills**: small, 1px hairline border, mono uppercase, one 5px color
  dot (Teal / Solar / Hibiscus) as the status.
- **Nav**: active item underlined with a 2px Tiki Teal rule + faint glow.

## Component kits & libraries

Tailwind CSS via CDN. Google Fonts: Space Grotesk, Inter, JetBrains Mono. No component
library and no icon set — build the tiki mark, acid swirls, sun-burst, and notch
rows from inline SVG / CSS gradients only.

## Logos & shapes

Logo = the carved Tiki SVG idol in Tiki Teal with a soft teal glow on Obsidian.
Square-ish geometry everywhere: 6px radii, hairline borders; only the sun disc,
acid swirls, and status dots are truly round. **Banned:** sacred ki'i or real
temple/idol photography, copied tribal/tapa patterns presented as authentic,
cartoon pill-everything, glass/blur, soft pastel washes, neon beyond the single
teal, emoji, and lucide/heroicons.

## Accessibility & respect

Moonlight on Obsidian/Basalt clears WCAG AA. Keep the teal glow decorative, not
load-bearing — pair it with border/underline state changes. Treat Polynesian
culture with respect: the tiki here is an **abstract, invented carving**, never
a reproduction of sacred imagery, and motifs stay geometric and original.

## Deliverable

A single self-contained `preview.html` (Tailwind + Google Fonts via CDN, inline
SVG/CSS), following the canonical structure: identity → theme spec (palette,
gradients, typography, components) → at least two realistic UX applications →
footer. Dark-first, minimalist, operational.
