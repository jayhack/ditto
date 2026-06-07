You are styling a web UI in the **Tourist** aesthetic. Apply the design kit
below verbatim — do not invent new colors, fonts, or motifs.

## Mood
A 1997 polaroid of a motorway interchange left on the dashboard in the
rain, then annotated by hand. Pale cyan wash bleeding into deep navy,
bone-paper sticky notes hand-pasted across the surface, stenciled sans
mastheads stamping over a blurred overpass, and one rust caution `X`
per page. The vibe is *late-90s alienation rendered as airline-safety
card* — equal parts rain-streaked windshield, lost-property bulletin,
and dot-matrix dispatch printout. Apply it to lost-and-found boards,
motorway dispatch consoles, dystopian travel sites, dread-tinted
dashboards — anything that should feel like a polaroid of the 21st
century left in the rain.

The reference is the Stanley Donwood / Tchocky design language: a
photographic blur drowned in cyan, then over-stamped with hand-printed
warnings, airline-safety pictograms, and a single rust `X`. Surface
this on developer tools as: build dashboards that look like motorway
dispatch boards, agent runs that look like signal-lost bulletins,
documentation that looks like a brace-position safety card.

## Palette (use these hex values — no substitutions)
- Mist:     #E8F0F2  (page background — pale rained-on fog)
- Wash:     #A8C9D2  (signature cyan — hero blur, pill backs)
- Cyan:     #5A9BAB  (middle teal — accent panels, hover)
- Highway:  #2D5A6B  (deep teal — body emphasis on cyan)
- Steel:    #0F2530  (near-black ink — body, borders, telemetry)
- Pitch:    #070D14  (pure deep ink — primary type, hard offsets)
- Bone:     #F1EBDC  (cream paper — sticky notes, polaroid frames)
- Caution:  #C84A22  (rust `X` — one per page, never two)

Default page background is **Mist (#E8F0F2)**. Body text is
**Pitch (#070D14)** or **Steel (#0F2530)**. Hero, polaroid, and
motion-blur surfaces are **Wash (#A8C9D2)** with mandatory rain
streaks. Cyan-field labels (the hand-printed ones) are
**Mist (#E8F0F2)**. Caution must occupy **under 4%** of any rendered
surface — exactly one rust X mark per viewport, no exceptions.

### Required gradients (use these strings exactly — they are the vibe)
- **Overpass blur** (signature — used on hero, card hero, key panels):
  `linear-gradient(95deg, #B8D4DC 0%, #A8C9D2 28%, #5A9BAB 55%, #2D5A6B 80%, #070D14 100%)`
- **Windshield rain** (vertical sky→pavement for full-bleed sections):
  `linear-gradient(180deg, #A8C9D2 0%, #7FB3C0 35%, #2D5A6B 75%, #0F2530 100%)`
- **Sticky paper** (Bone surfaces — polaroids, hand-note cards):
  `linear-gradient(180deg, #F1EBDC 0%, #E0D8C2 100%)`
- **Caution flare** (radial — only the rust X stamp, the lone alert orb):
  `radial-gradient(circle at 40% 40%, #E86530 0%, #C84A22 50%, #7A2911 100%)`
- **Dispatch ink** (deep ink panels — telemetry, terminal, footer):
  `linear-gradient(180deg, #0F2530 0%, #070D14 100%)`

## Typography
Load these from Google Fonts:
- **Display: `"Anton"`** weight 400. Uppercase only, letter-spacing
  `0.02em`, line-height `0.86` (stacks tight). Reads as a *stenciled
  motorway sign* — the wordmark stamps the surface, never floats.
  Hero size `clamp(3.25rem, 9.5vw, 7.5rem)`. Always Mist on cyan or
  Pitch on Mist — never both inside the same headline.
- **Body: `"Inter"`** weights 400/500/600/700/800. Sentence case for
  long-form. Section labels are **Inter 800 uppercase** at 11–12px,
  letter-spacing `0.22em`, in Steel or Cyan.
- **Mono: `"JetBrains Mono"`** weights 400/500/700. Used for telemetry,
  bracket pills, dispatch lines, the dot-matrix divider, and timestamps.
  Mono uppercase tracking is always `0.18em`. Lines that look like a
  printout begin with `> ` or `→ `.
- **Hand: `"Permanent Marker"`** weight 400. Used **only** for the
  hand-printed annotations laid on top of cyan fields — `LOST CHILD`,
  `IDIOT · SLOW DOWN`, `THIS WAY ↘`, `LIFT DOOR`. Always Mist, always
  rotated -1° or -2° (never straight), max 3 words per scrawl.

## Visual motifs (include at least 6 per page)
1. **Rain streaks**: every cyan field carries 1px vertical Mist strokes
   at irregular x-offsets (every 14–34px), `mix-blend-mode: screen`,
   opacity `0.20–0.32`. Animated drift down 22px over 3.6s. Without
   the streaks, no cyan field is in-vibe.
2. **Overpass blur band**: a horizontal band of the *Overpass blur*
   gradient sits at the top of every hero, with 1px ash diagonal strokes
   (~115°) at 18% opacity layered over it. Reads as a polaroid of a
   freeway curve photographed through a wet windshield.
3. **Hand-printed scrawls**: short Permanent Marker labels overlaid on
   cyan — `[ LOST CHILD · 14:22 ]`, `THIS WAY ↘`, `IDIOT · SLOW DOWN`,
   `LIFT DOOR`. Always Mist text, always rotated -1° to -2°, often
   inside square brackets `[ ]`. Replace nothing — they are *added*
   to legible labels, never substitutes.
4. **Stencil pictograms**: Donwood-style airline-safety SVGs in 1.5px
   Mist (on cyan) or Pitch (on Bone). Six allowed glyphs only:
   *brace-figure* (stick figure, arms forward, head down), *lift-figure*
   (stick figure, arms up), *no-entry circle* (○ with diagonal slash),
   *triangle bang* (△ with `!`), *doorway* (□ with right-arrow), and
   *the rust X* (the only Caution element). Each ~24px, square-cornered.
5. **The rust X stamp**: ONE per viewport. A hand-drawn `×` in
   Permanent Marker, ~28px, Caution color, with a 6px Caution dot
   nearby and a `[ NO ENTRY ]` bracket pill underneath in Mist mono.
   Reserved for: missing items, signal-lost beacons, off-limits.
6. **Typewriter telemetry beacons**: short JetBrains Mono lines in
   Steel or Mist prefixed with `> ` or `→ ` — `> SIGNAL LOST · 03:42:18 GMT`,
   `→ FITTER · HAPPIER · MORE PRODUCTIVE`, `> NO INCOMING TRAFFIC · J24`.
   Always uppercase, mono, tracking `0.18em`.
7. **Polaroid frames**: every photo / motion-blur image lives inside a
   Bone-paper polaroid — 4px Mist inner border, 1.5px Pitch outer
   border, 4px Pitch hard-offset shadow, hand-printed caption below in
   Permanent Marker. Slightly rotated (-1° to +1°) so the page feels
   pinned, not laid out.
8. **Sticky paper notes**: irregular Bone rectangles pasted onto cyan
   fields, rotated -2°, carrying a 1.5px Pitch border + 3px Pitch hard
   shadow, with a single hand-drawn arrow `↘` pointing toward a feature.
9. **Dot-matrix divider**: replace every `<hr>` with a row of
   `· · · · · · · · · · · · · · ·` in JetBrains Mono Pitch tracked
   `0.6em`. Never solid lines.
10. **Caution stripe tape**: 8px diagonal Caution + Pitch stripes used
    *once* per page as a single thin accent strip — typically the top
    of a "no entry" panel or the right edge of the alert sticky.

## Components
Use **Tailwind CSS** (CDN). Component shapes:
- **Buttons** (square corners, Inter 800 uppercase, tracking 0.18em):
  - `primary`: Pitch bg, Mist text. `px-6 py-3`, 1px Pitch border, 4px
    Pitch hard-offset shadow. Hover: Steel bg, shadow shrinks to 2px.
  - `secondary`: Bone bg, Pitch text, 1.5px Pitch border, 4px Pitch
    hard-offset shadow. Hover: Mist bg.
  - `ghost`: transparent bg, Cyan text. Hover: 1px Cyan bottom underline.
  - `hand` (special): Bone bg, Permanent Marker label, rotated -1°,
    no shadow — feels stickered onto the surface. Use for non-action
    hints like `[ TRY ME ]`.
  - One `primary` per region. Never two.
- **Inputs**: Mist bg, bottom-border-only (1px Pitch), Pitch text. Focus
  border switches to Caution. Labels above inputs in the section-marker
  style (Inter 800 uppercase tracking 0.22em, Steel or Cyan).
- **Cards / panels**: Bone or Mist bg, 1.5px Pitch border, 4px Pitch
  hard-offset shadow. Square corners — only the rust X dot, the
  brace-figure head, and pictogram circles round.
- **Bracket pills** (the universal label): square (no radius), no
  border, Wash bg, Pitch JetBrains Mono uppercase 10px text tracked
  `0.22em`, mandatory `[` `]` literal brackets in the text — e.g.
  `[ LOST CHILD ]`, `[ J24 · 14:22 ]`. The whole vibe defaults to
  bracket pills; never use rounded-full pills.
- **Tables / lists**: 1px Steel/15% divide-y, Inter 700 uppercase
  headers in Cyan, Pitch body cells, JetBrains Mono numerals in Steel.
  Caution pictogram (rust X) marks the at-most-one alert row.
- **Terminal / dispatch block**: Pitch (#070D14) background, Mist text,
  Cyan `>` prompt, Caution cursor (a 8px square, blinking). 1px Steel
  border. Rain-streak overlay clipped to the inside of the panel.
- **Nav**: top bar, 1.5px Pitch bottom rule with one rust X centered on
  the rule. Wordmark left, mono uppercase labels center, one Pitch
  primary CTA right.

Optional libraries: **none**. No shadcn, no MUI, no DaisyUI, no icon
set. The icon system is exactly: the *brace-figure*, the *lift-figure*,
the *no-entry circle*, the *triangle bang*, the *doorway*, the *rust X*,
plus `↘`, `↗`, `→`, `·`, `[ ]`. No emoji. No Heroicons. No Lucide.

## Logos & shapes
- **Wordmark + monogram**:
  - Monogram: a 56×56 Pitch square frame containing the *brace-figure*
    pictogram (1.5px Mist stroke), with a 4px Mist hard-offset shadow.
    The frame is the logo — a one-glyph airline-safety card.
  - Wordmark: `TOURIST` in Anton 400 at 2–3 rem, Pitch on Mist or Mist
    on Wash, with a JetBrains Mono `® AGENCY` superscript tracked
    `0.22em` immediately to the right.
- **Allowed shapes**: rectangles, square brackets, the six pictograms,
  the rust X, polaroid frames, hand-drawn arrows (`↘`, `↗`, `→`),
  1px hairlines, dot-matrix runs.
- **Banned**: drop shadows above 4px offset, blur / glass / backdrop
  filters, gradients above the 5 named gradients, ANY emoji, rounded
  corners on cards or buttons, lucide / heroicons / feather icon sets,
  photography (the cyan motion-blur replaces it), neon glow, pastel
  gradients, organic blobs.

## Accessibility
Pitch on Mist passes AAA at all body sizes. Pitch on Wash passes AA at
≥14px. Mist on Steel passes AA at ≥14px. Caution on Mist passes
AA-large only — never set body copy in Caution. Hand-printed Mist
scrawls on Wash are *decorative annotation*, never set body copy in
Permanent Marker. The terminal block (Mist on Pitch) passes AAA.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`, fonts
from Google Fonts (Anton, Inter, JetBrains Mono, Permanent Marker).
Apply the palette, gradients, motifs, typography rules, and component
shapes exactly as specified above.

The page should look like a motorway services lost-property bulletin
left in the rain — pale cyan wash, bone-paper polaroids pinned at
slight angles, hand-printed warnings stamped on top of stenciled sans
mastheads, dot-matrix dispatch printouts, and exactly one rust `X`
saying *not here, not now, not them*. Apply the kit to **developer
surfaces**: build dashboards as motorway dispatch boards, agent runs
as signal-lost bulletins, documentation as airline-safety cards, CLI
welcomes as field-radio chatter. Avoid pop-culture references, mascot
characters, and any literal album-art reproduction — the spirit is
implied by motif, never depicted.
