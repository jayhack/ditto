You are styling a web UI in the **Iridesce** aesthetic. Apply the design kit
below verbatim — do not invent new colors, fonts, or motifs.

## Mood
A holographic foil-print poster pinned on a gallery wall. Heavy carved
**black caps** sit directly on top of **melting oil-slick gradients**,
**halftone dot suns**, and scattered **white stitch marks**, all floating on
a quiet **smoke-gray** paper. The dialectic is the whole vibe: monumental
black-and-gray restraint versus a rainbow that refuses to land on any single
color. Think risograph + chrome foil + 1990s rave flyer, printed at A1.

Position is a _foil print studio's identity applied to software_ — print-drop
shops, holographic music broadcasts, gallery openings, art editions, beauty /
iridescent product pages. Loud art, quiet frame. Never a generic SaaS
dashboard.

## Palette (use these hex values — no substitutions)
- Smoke:   #E9E9E7  (warm light gray — page background, gallery paper)
- Smoke 2: #DEDEDB / #F4F4F2  (card insets, alt surface)
- Ink:     #0A0A0A  (near-black — type, borders, the carved caps)
- Flare:   #FF2D1E  (hot red — halftone sun, alert / sold-out states)
- Fuchsia: #FF3D9A  (hot pink — foil, focus borders)
- Lilac:   #B6A4F0  (lavender — foil mid-tone)
- Aqua:    #57DED6  (cyan — foil + chromatic aberration)
- Acid:    #B4EE3C  (chartreuse — foil highlight)
- Cobalt:  #2E3BE6  (electric blue — oil-slick deep stop)

Page background is **Smoke**. All body and display type is **Ink**. The six
chroma (Flare, Fuchsia, Lilac, Aqua, Acid, Cobalt) **never appear as a flat
panel fill or as body text** — they live only inside foil gradients,
oil-slick, melting blobs, halftone dots, and tiny 1px seeds. Everything flat
stays smoke + ink. Color enters only through light.

## Required gradients
- **Foil** (the signature linear sweep):
  `linear-gradient(115deg, #FF2D1E 0%, #FF3D9A 18%, #B6A4F0 38%, #57DED6 56%, #B4EE3C 74%, #FF3D9A 100%)`
  Set `background-size: 220% 220%` and animate `background-position` over
  ~14s for a slow shimmer.
- **Oil slick** (looping conic):
  `conic-gradient(from 210deg at 50% 50%, #FF3D9A, #B6A4F0, #2E3BE6, #57DED6, #B4EE3C, #FF2D1E, #FF3D9A)`
  Optionally rotate the element slowly (~22s linear) for a turning-puddle feel.
- **Chrome melt** (white sheen injected):
  `linear-gradient(160deg, #FFFFFF 0%, #FF3D9A 16%, #B6A4F0 34%, #FFFFFF 50%, #57DED6 64%, #B4EE3C 82%, #FFFFFF 100%)`
- Always honor `@media (prefers-reduced-motion: reduce)` by disabling the
  gradient animations.

## Typography
Load from Google Fonts:
- **Display: `"Archivo Black"`** weight 900. The carved monumental caps and
  the wordmark. `letter-spacing: -0.045em`, `line-height: 0.82`,
  `text-transform: uppercase`. Display type is ALWAYS Ink and usually sits
  directly over the artwork. Frequently stacked over 2–3 lines like a poster.
- **Italic insert: `"Fraunces"` italic 600** (opsz). Used for ≤3-word lyric
  inserts inside or beneath a display headline (`refuses`, `that`,
  `iridescent`). Lowercase, never uppercase, max once per headline.
- **Body / UI: `"Inter"`** 400/500/600/700. Paragraphs, nav, buttons, prices.
  Body sits at 15px.
- **Mono / telemetry: `"JetBrains Mono"`** 400/500. Tiny clinical captions,
  edition numbers, timestamps, stamps. Uppercase, tracked `0.24em` at 10–11px.

## Visual motifs (include at least 5 per page)
1. **The overlap** — carved black Archivo Black caps laid directly on top of a
   holographic art slab. The art is the canvas; the black type is the print.
   Apply **chromatic aberration** to hero display type:
   `text-shadow: 0.045em 0 0 rgba(255,61,154,.85), -0.045em 0 0 rgba(87,222,214,.85)`.
2. **Melting blob** — a liquid holographic mass: an element with the Foil
   fill, an organic `border-radius` (e.g. `47% 53% 62% 38% / 55% 42% 58% 45%`),
   and a soft `drop-shadow(0 10px 22px rgba(10,10,10,0.18))`. Vary the radius
   per blob. These are the ONE permitted organic shape.
3. **Halftone flare** — a red (or single-chroma) dot disc standing in for a
   sun. Tile `radial-gradient(var(--dot) 31%, transparent 34%)` at
   `background-size: 9px 9px`, then `mask-image: radial-gradient(circle at 50% 48%, #000 36%, transparent 72%)`
   to fade it into a disc.
4. **Stitch field** — scattered white tick marks (rain / hand-drawn stitches):
   `repeating-linear-gradient(118deg, rgba(255,255,255,.92) 0 2px, transparent 2px 9px)`
   chopped by `mask-image: repeating-linear-gradient(26deg, #000 0 6px, transparent 6px 15px)`.
   Layer at 50–70% opacity over artwork.
5. **Gallery mat** — every card / panel is a smoke rectangle with a `1.5px Ink`
   border, square corners, NO drop shadow (only blobs get shadows). Optional
   tiny corner tag pill (`№ 01 / FOIL`) top-left.
6. **The seed** — a tiny round oil-slick conic dot used as the universal bullet,
   button prefix, list marker, and divider center. Single chroma for category
   dots, full conic for "live / new".
7. **Seed divider** — a `1.5px Ink` rule with a single 16px conic seed centered
   on it. Replaces every `<hr>`.
8. **Paper grain** — two faint radial dot layers (Ink/5%, Cobalt/3.5%) at
   8px / 13px over Smoke. Subtle warm noise, never reads as polka dots.

## Components
Use **Tailwind CSS** (CDN). Square corners everywhere; only seeds, blobs, and
the halftone disc are round.
- **Buttons (foil)**: square, `1.5px Ink` border, Ink text in Inter 700
  uppercase tracked `0.16em`, with a Foil gradient behind the text (use a
  `::before` at `z-index:-1`). The primary "buy / shop / RSVP / play" action.
- **Buttons (ink)**: square, Ink fill, Smoke text, Inter 600 uppercase tracked
  `0.18em`, prefixed with one tiny conic seed. Hover widens the gap.
- **Buttons (line)**: transparent, `1.5px Ink` border, Ink text. Hover fills
  white. The secondary action.
- **Inputs**: bottom-border-only (`1.5px Ink`), transparent, Ink text. Focus
  border becomes Fuchsia. Label above is mono caps tracked `0.24em`.
- **Pills / badges**: square, `1.5px Ink` border, Smoke fill, mono uppercase
  10px, optional leading seed. Sold-out / alert pills switch border + text to
  Flare.
- **Cards / panels**: smoke `1.5px Ink` border, square, no shadow. Optional one
  melting blob bleeding off a corner.
- **Tables / queues / TOCs**: `1px Ink` divide-y rows, mono index left, Inter
  title middle, mono time/coordinate right. One seed per row encodes category.

The icon system is exactly: the **seed** (conic or single-chroma dot), the
**melting blob**, the **halftone disc**, `№` for editions, `·` middle dot, `→`
for CTAs, and `▶` for play. Banned: emoji, lucide / heroicons, glass / blur,
soft pastel gradients on flat panels, neon glow, chrome bevels on buttons,
drop shadows on anything that isn't a blob.

## Logos & shapes
- **Wordmark**: `IRIDESCE` in Archivo Black, tracked `-0.045em`, with chromatic
  aberration. A small Fraunces italic descriptor (`a foil print studio`) may
  sit beneath in Ink.
- **Mark**: one small Foil melting blob (~44px) paired to the left of the
  wordmark. The blob + wordmark is the logo.
- **Allowed shapes**: rectangles (square corners only), circles (seeds, halftone
  disc), and the melting blob (the single organic exception). The six chroma
  appear only inside foil / oil-slick / chrome / halftone / blobs / seeds.
- **Banned**: drop shadows on flat surfaces, glass / blur, gradients on flat
  panels, neon glow, chrome button bevels, emoji, generic dark dashboards,
  any chroma used as a flat background or as body text.

## Accessibility
Ink (#0A0A0A) on Smoke (#E9E9E7) passes AAA — the backbone for all real text.
Never set body or critical text in a chroma. Black display type over bright
foil generally clears AA at large sizes; keep chromatic-aberration offset
small (≤0.05em) so legibility holds. Halftone and stitch fields must stay
decorative — never carry meaning the mono labels don't also state.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`, fonts from
Google Fonts (Archivo Black, Fraunces, Inter, JetBrains Mono). Apply the
palette, gradients, motifs, typography, and component shapes exactly as
specified.

The page should look like a foil-print studio's poster opened flat on a
gallery wall — quiet smoke paper, a carved black wordmark, and melting
oil-slick light bleeding through halftone and stitch marks. Apply the kit to
**art / culture surfaces**: print-drop shops, holographic broadcasts, gallery
openings, iridescent product pages, edition archives. Avoid SaaS dashboards,
fintech, and any flat use of the rainbow.
