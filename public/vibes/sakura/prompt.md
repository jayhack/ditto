You are styling a web UI in the **Sakura** aesthetic. Apply the design
kit below verbatim — do not invent new colors, fonts, gradients, or
icons. The dot grid is the entire art system; the radial bloom is the
entire color theory.

## Mood
A meditative tribute to Damon Xu's *INSIDE OUT THE COLOR — SAKURA*
poster: hundreds of soft 3D-rendered spheres arrayed in a perfect grid,
each one tinted by a single master radial that blooms from pale
petal-white at the edges through saturated cherry pink into a deep
crimson heart at the center. The vibe is *hanami* (花見, cherry-blossom
viewing) applied to digital surfaces — generous whitespace, one
contemplative focal point per screen, and the unhurried satisfaction of
a perfectly registered print. Soft but exact. Pink but not cute. Never
breezy, never glittery, never Instagrammy.

References: Damon Xu's *INSIDE OUT THE COLOR* series, late-Heisei
graphic posters, Issey Miyake catalogs, Sōshun Edo dye palettes, Vera
Molnár dot grids done in cherry.

The page's emotional center is always the **Heart**: one radial-tinted
dot module per viewport, never two. Everything else falls away from it.

## Palette (use these hex values — no substitutions)
- Petal:   `#FCF4F7`  (page background, default surface)
- Blush:   `#F8DEEA`  (outer dot ring, card borders, dividers)
- Sakura:  `#F5A6C7`  (the iconic cherry pink — mid dot ring, secondary fills)
- Plum:    `#EF6FA5`  (third dot ring, accent text on Petal)
- Magenta: `#E1318A`  (primary CTA, emphasis text, link color)
- Crimson: `#B41C5E`  (deep ring, button hover, headline emphasis)
- Heart:   `#5D0830`  (dark center of the bloom, foreground on dark panels)
- Sumi:    `#1A0913`  (ink black with a magenta tint — body text, page-end strip)
- Stone:   `#8B7280`  (muted micro-labels, secondary mono — derived, use sparingly)

Default page background is **Petal (#FCF4F7)**. Default body text is
**Sumi (#1A0913)**. Muted micro-copy is **Stone (#8B7280)**. Magenta
(#E1318A) is the link color and the primary CTA color — used precisely,
never as a flat field larger than a button.

**Discipline rule.** The radial bloom does the visual work. Keep flat
fields **mostly Petal**: Petal + Blush together should occupy **≥ 65%**
of any rendered surface. Magenta + Crimson + Heart combined should
occupy **≤ 12%**, and almost always as the Heart bloom rather than as
flat fills.

## Required gradients (use these strings exactly)

The signature — **the Heart bloom** (used on the gallery card hero, the
identity hero, and exactly one Heart panel per UX application):

```
radial-gradient(circle at 50% 50%, #5D0830 0%, #B41C5E 18%, #E1318A 34%, #EF6FA5 50%, #F5A6C7 68%, #F8DEEA 84%, #FCF4F7 100%)
```

The **Petal wash** (used on hero backdrops, full-bleed bands, the
footer info strip):

```
linear-gradient(180deg, #FCF4F7 0%, #F8DEEA 60%, #F5A6C7 100%)
```

The **dot sheen** — applied to each individual 3D sphere to give it
volume; layered on top of a flat tint:

```
radial-gradient(circle at 32% 28%, rgba(255,255,255,0.65) 0%, rgba(255,255,255,0.18) 18%, transparent 42%),
radial-gradient(circle at 68% 78%, rgba(26,9,19,0.18) 0%, transparent 38%)
```

The **CTA sheen** — used on the Magenta primary button only:

```
radial-gradient(circle at 30% 30%, #EF6FA5 0%, #E1318A 50%, #B41C5E 100%)
```

No other gradients. No sunset stripes, no glass, no chromatic shifts.

## Typography
Load these from Google Fonts:

- **Display: `"Inter Tight"`** weights **700 / 800 / 900**. The only
  display face. Uppercase for wordmarks, mixed case for section
  openers. Letter-spacing **-0.02em** at large sizes, **0** at small.
  Hero size: `clamp(4rem, 13vw, 11rem)`. Line-height **0.92**.
  Wordmarks **always** get an `®` superscript in JetBrains Mono at
  0.45em, sitting on the cap-height.
- **Body: `"Inter"`** weights **400 / 500 / 600 / 700**. Sentence case.
  15–17px paragraphs, line-height **1.55**.
- **Mono: `"JetBrains Mono"`** weights **400 / 500 / 700**. Uppercase
  for the universal eyebrow `INSIDE OUT THE COLOR` and every micro-label
  (`№ 03 / 12`, `BLOOM 0.482`, `EAST WIND · 03:42`). **Tracking is
  always 0.32em** for the eyebrow, **0.22em** for ordinary mono labels.
- **Kanji accent: `"Noto Serif JP"`** weight **600**. Used **only** for
  the single character 櫻 (sakura), or short 2–3 character poetic
  inserts (花見, 春, 月). Never as body copy. Always Crimson or Heart.

**The signature type effect — the SAKURA wordmark.** Inter Tight 900,
uppercase, the trailing letter optionally sliced by an `®` sup. Set in
Sumi on Petal. Hero size, set on its own line. Below it sits a single
Noto Serif JP 櫻 in Crimson at ~0.4× the wordmark height. No shadow, no
outline, no fill effect — the wordmark is **flat ink on petal paper**.
The visual heat comes from the dot grid behind it, never from the type.

Type rules:
- Display is **always Sumi** on Petal. Never gradient text. Never
  Magenta display.
- Italic is **banned** — restraint is the point.
- The eyebrow `INSIDE OUT THE COLOR` (mono uppercase, tracked 0.32em,
  Stone or Magenta) appears at least once per page, usually as the
  masthead caption.
- Magenta body text only at ≥14px (contrast). Below that, Crimson or
  Sumi.

## Visual motifs (include at least 6 per page)

1. **The Dot Grid.** The signature. A 16–24 column grid of round 3D
   spheres at 95–100% diameter:gap ratio (i.e. tight grid, almost
   touching, never overlapping). Each sphere is rendered as a flat tint
   + the **dot sheen** layered radial highlight + ambient shadow.
   Sphere tints are sampled from the **Heart bloom** based on their
   radial distance from the grid center — outer rings are Petal/Blush,
   middle rings Sakura/Plum, inner rings Magenta/Crimson, the center
   Heart. Use a 5–7 ring quantization, not a smooth gradient: each
   sphere is one **discrete** tint, which is the whole charm of the
   piece.
2. **The Heart.** One dot grid module per surface, centered, as the
   emotional and visual focus. The user reads from the heart outward.
3. **The Petal info-band.** A pale Petal/Blush horizontal strip at the
   bottom of the hero (and once at page-end) with: mono uppercase label
   `INSIDE OUT THE COLOR` + author/section line on the left; 櫻 kanji
   below the label in Crimson Noto Serif JP; giant Inter Tight wordmark
   right-aligned across the band. This is a direct nod to the original
   poster's bottom band. Mandatory on the hero.
4. **The kanji 櫻.** Used as a standalone glyph — never inside a
   sentence, never doubled. Always Crimson on Petal or Petal on Heart.
   Size: ~3rem at the hero info-band, ~1.25rem at section breaks.
5. **The ◉ bullet.** A heavy filled circle in Magenta, the only list
   marker. Place at 0.5em from the line, vertically centered.
6. **Petal-row divider.** A single horizontal row of 12px Blush spheres
   (sheen applied), evenly spaced, replaces every `<hr>`. Never use a
   line — always a row of dots.
7. **The eyebrow.** `INSIDE OUT THE COLOR` in JetBrains Mono uppercase,
   tracked 0.32em, Stone or Magenta, 11px. Pairs with a section number
   like `№ 02 / 05` aligned right.
8. **The 6px corner dot.** A tiny Magenta 6px sphere with sheen tucked
   into the top-left and bottom-right corners of every card. Two dots,
   no more. This is the card's "registered" mark.
9. **The DAMONXART®-style colophon stamp.** Mono uppercase `SAKURA® ·
   INSIDE OUT THE COLOR · NO. 03 / 12` on a 1px Blush hairline at the
   bottom of any catalog/poetry surface.

## Components
Use **Tailwind CSS** (CDN). All cards and containers use **soft**
radii (16–24px); buttons and pills are **fully round**.

- **Buttons**:
  - **Primary**: `background: radial-gradient(circle at 30% 30%, #EF6FA5 0%, #E1318A 50%, #B41C5E 100%)`,
    Petal text, Inter 700 uppercase at 12px, tracking 0.22em, padding
    `14px 28px`, `border-radius: 9999px` (fully round), no border,
    soft shadow `0 12px 28px -10px rgba(228,49,138,0.55)`. Hover: shift
    sheen to Crimson core (`radial-gradient(circle at 50% 50%, #B41C5E 0%, #5D0830 100%)`).
  - **Secondary**: Petal background, **1px solid Magenta** border,
    Magenta text, Inter 600 uppercase 12px tracking 0.22em, padding
    `13px 27px`, `border-radius: 9999px`. Hover: Magenta fill, Petal text.
  - **Ghost / link**: Magenta text with a Magenta underline at 1.5px,
    offset 4px. Hover: Crimson.

- **Inputs**: bottom-border-only (`border-bottom: 1.5px solid Sakura`),
  transparent background, Sumi text 15px Inter 500. Focus: border
  becomes Magenta (1.5px), plus a single 6px Magenta sphere appears
  inside the right edge as the focus indicator. No box around inputs.

- **Selects**: same as inputs, with a 6px Magenta sphere as the
  chevron-replacement (since the icon system is dots).

- **Badges / pills**: rounded-full, Blush background, Magenta text,
  Inter 600 uppercase 10px tracking 0.22em, padding `4px 11px`, no
  border. Optional 4px Magenta dot prefix.

- **Cards**: Petal background, **`border-radius: 24px`**,
  **1px solid Blush** border, soft shadow `0 24px 40px -16px rgba(245,166,199,0.55)`.
  Two 6px Magenta corner dots (top-left + bottom-right, 14px inset).
  Optional Petal-row divider at section breaks.

- **Dot-grid module**: a CSS grid (or SVG) of N×N spheres, each rendered
  as a `<div>` (or `<circle>`) with a flat tint + dot sheen + ambient
  shadow. The Heart panel is **the only place** an N≥16 grid appears;
  smaller dot grids (3×3 / 5×5) are used as logo marks, section
  ornaments, and product thumbnails.

- **Tables / lists**: `divide-y` Blush. Mono uppercase 10px Stone for
  left labels, Inter 15px Sumi for body cells, JetBrains Mono 11px
  Magenta for right-aligned numerics.

Optional libraries: **none**. Hand-built from Tailwind + Google Fonts.
**Do not** pull in shadcn, MUI, DaisyUI, lucide, heroicons, or any
emoji-based icon set. The dot **is** the icon.

## Logos & shapes

- **Logo mark**: a 5×5 mini dot grid (25 spheres) with the Heart bloom
  tint distribution: corners Petal, mid-ring Sakura, center Heart.
  Always paired with the wordmark `SAKURA` in Inter Tight 900 + a
  Mono `®` superscript.

  ```html
  <svg viewBox="0 0 60 60" width="36" height="36" aria-hidden="true">
    <!-- 5x5 grid of 10px circles with 2.5px gap (centers at 5,17,29,41,53) -->
    <!-- corner ring: Blush -->
    <g fill="#F8DEEA">
      <circle cx="5" cy="5" r="5"/><circle cx="17" cy="5" r="5"/><circle cx="41" cy="5" r="5"/><circle cx="53" cy="5" r="5"/>
      <circle cx="5" cy="17" r="5"/><circle cx="53" cy="17" r="5"/>
      <circle cx="5" cy="41" r="5"/><circle cx="53" cy="41" r="5"/>
      <circle cx="5" cy="53" r="5"/><circle cx="17" cy="53" r="5"/><circle cx="41" cy="53" r="5"/><circle cx="53" cy="53" r="5"/>
    </g>
    <!-- ring 2: Sakura -->
    <g fill="#F5A6C7">
      <circle cx="29" cy="5" r="5"/><circle cx="29" cy="53" r="5"/>
      <circle cx="5" cy="29" r="5"/><circle cx="53" cy="29" r="5"/>
    </g>
    <!-- ring 1: Magenta -->
    <g fill="#E1318A">
      <circle cx="17" cy="17" r="5"/><circle cx="41" cy="17" r="5"/>
      <circle cx="17" cy="41" r="5"/><circle cx="41" cy="41" r="5"/>
      <circle cx="29" cy="17" r="5"/><circle cx="17" cy="29" r="5"/>
      <circle cx="41" cy="29" r="5"/><circle cx="29" cy="41" r="5"/>
    </g>
    <!-- heart -->
    <circle cx="29" cy="29" r="5" fill="#5D0830"/>
  </svg>
  ```

- **Allowed shapes**: circles (all sizes), rounded-rectangles at 16–24px
  radius, fully-round pills, the 櫻 kanji glyph, the eyebrow line, the
  ® superscript. That's the entire shape language.

- **Banned**: hard 90° corners (except the bottom Petal info-band's
  hairline rules), drop shadows above 32px blur, neon / glow / chrome,
  glass / blur / backdrop-filter, sunset gradients, hot pink that isn't
  one of the named values, emoji, lucide / heroicons, organic blobs,
  italic type.

## Accessibility
Sumi on Petal is AAA. Magenta on Petal passes AA at ≥14px — fine for
headings, buttons, links. Crimson on Petal passes AAA. Petal on Heart
passes AAA — Heart panels carry their copy in Petal. Stone is reserved
for ≤11px micro-labels only. The Heart bloom radial sits behind no body
text; copy that overlays the bloom must land on a Petal-fill panel
clipped over the bloom. Honor `prefers-reduced-motion: reduce` —
nothing in this kit moves by default, but if you add ambient
sphere-pulse animations, gate them on that media query.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`, fonts
from Google Fonts (Inter Tight, Inter, JetBrains Mono, Noto Serif JP).
Build the dot grid as a CSS grid of div spheres (or an SVG with `<circle>`
elements) — each one a discrete tint sampled from the Heart bloom, with
the dot sheen layered on top for volume. Place one Heart bloom on the
identity hero, surface the Petal info-band beneath it, and use smaller
dot modules (3×3 logo marks, dot-row dividers, single 6px corner dots)
throughout. The page should feel like an unhurried May afternoon at the
end of a long winter — petal-white paper, a single deep heart, and the
quiet satisfaction of a perfectly registered print.
