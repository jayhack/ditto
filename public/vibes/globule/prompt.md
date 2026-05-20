You are styling a web UI in the **Globule** aesthetic. Apply the design kit
below verbatim — do not invent new colors, fonts, or motifs.

## Mood
A Designforum Wien cultural-issue poster, reissued for software. Massive
**black grotesque letter** dominates warm cream paper while a flowing
**3D glossy chromatic chain of globules** twists through it — bouncy,
wet, color-saturated spheres in jewel cyan, lime, cobalt, indigo,
magenta, and sun-yellow, some banded with zebra stripes, halftones, and
polka dots. Tiny clinical mono captions like `JULI · 2026` and
`N°2 / WIRTSCHAFT` orbit at the edges. The dialectic is the entire
vibe: **monumental editorial restraint** vs **maximalist liquid
chromatic chaos**. Cream and ink hold the page; the globule chain is
where the page comes alive.

Position is _European cultural-design quarterly applied to software_ —
event programs, exhibition catalogs, color-tooling apps, playlist
broadcasts. Confident, opinionated, made to be printed at A1.

Reference for the look: 2010s Austrian/German editorial poster work
(Designforum Wien, Bureau Mirko Borsche, Sagmeister & Walsh covers),
not airbrushed Web 3.0.

## Palette (use these hex values — no substitutions)
- Paper:    #F2EAD0  (warm cream — page background, butcher-paper warmth)
- Paper Soft: #EFE3C2 (subtle alt surface, card insets)
- Ink:      #0A0908  (heavy near-black — type, borders, the giant letter)
- Cyan:     #2DC4D8  (signature aqua globule)
- Lime:     #82E647  (acid green globule, accent dots)
- Cobalt:   #2347C8  (deep electric blue globule)
- Indigo:   #5B2EA0  (royal purple globule, link hover)
- Magenta:  #E04691  (hot pink globule, alert)
- Sun:      #F2D24A  (warm yellow globule, highlight)

Default page background is **Paper (#F2EAD0)**. Body and display type
is **Ink (#0A0908)**. The six "globule colors" (Cyan, Lime, Cobalt,
Indigo, Magenta, Sun) are used **only on globules and 1-pixel accents**
— never as a flat panel background and never as body type. Globules
are how color enters the page; everything else is cream + ink.

### Required surfaces
- **Paper grain**: two tiny radial dot layers in 4–6% tints of Ink and
  Cobalt, sized 7px / 11px, layered on Paper. Subtle warm noise, never
  reads as polka dots.
  ```
  background-color: #F2EAD0;
  background-image:
    radial-gradient(rgba(10,9,8,0.05) 1px, transparent 1px),
    radial-gradient(rgba(35,71,200,0.04) 1px, transparent 1px);
  background-size: 7px 7px, 11px 11px;
  background-position: 0 0, 3px 4px;
  ```
- **Diagonal flow strip** (behind globule clusters): a 135° linear
  gradient from Paper through faintly tinted Cyan / Indigo / Magenta
  bands at ~6% opacity. Never above 12%. The flow strip *implies* the
  chain's path; the globules sit on top.
- **Pattern globule fills** — three mandatory pattern textures used
  on a minority of globules (never more than 1 in 4):
  - **Zebra**: black stripes wrapping a colored sphere
    (`repeating-linear-gradient(78deg, #0A0908 0 6px, transparent 6px 14px)`)
  - **Polka**: black dots on a colored sphere (radial-gradient dot pattern)
  - **Halftone**: a smooth black-to-color radial gradient on one side

## Typography
Load these from Google Fonts:
- **Display (the giant letter): `"Archivo Black"`** weight 900.
  Used for the single-letter section initials at `clamp(18rem, 38vw, 32rem)`,
  the hero monogram, and big numerals. `line-height: 0.82`,
  `letter-spacing: -0.04em`. Archivo Black should feel **carved**, not soft.
- **Editorial serif: `"Playfair Display"`** weight 400/700 + italic.
  Used for the masthead date strings (`JULI · 2026`), the section
  badge numeral (`N°2`), and ≤3-word italic inserts inside display
  headlines. Always Ink. Never for body copy.
- **Body / labels: `"Inter"`** weight 400/500/600/700. Used for
  paragraphs, navigation, button copy, captions. Body sits at 15–16px.
- **Mono / telemetry: `"JetBrains Mono"`** weights 400/500. Used for
  the tiny clinical captions, event dates, coordinates, and stamp
  text (`19. & 20. JULI · DESIGNFORUM · WIEN`). All uppercase, tracked
  `0.22em` at 10–11px.

Tracking rules:
- Archivo Black display: `-0.04em` (already tight).
- Playfair Display: spaced caps at `0.32em` for masthead dates,
  natural italic otherwise.
- Inter body: normal tracking.
- JetBrains Mono labels: `0.22em` for ≤12px caps, `0.12em` for body mono.

## Visual motifs (include at least 5 per page)
1. **The Giant Letter** — a single Archivo Black initial in Ink set at
   28–40vw, page-dominating, anchored top-left of the hero. The letter
   is **the canvas**. A small Playfair caption (the issue name, e.g.
   `WIRTSCHAFT`) is rotated 90° (`writing-mode: vertical-rl`) inside
   the negative space of the letter's counter.
2. **Globule chain** — a diagonal flow (≈135°) of 12–24 glossy 3D
   spheres of varying size (16px – 200px). Each globule is rendered
   with pure CSS:
   ```
   .globule {
     border-radius: 999px;
     background:
       radial-gradient(circle at 32% 28%,
         rgba(255,255,255,0.95) 0%,
         rgba(255,255,255,0.4) 8%,
         <color> 28%,
         <color-shade> 78%,
         #050505 100%);
     box-shadow:
       inset -8px -10px 18px rgba(0,0,0,0.35),
       0 6px 14px rgba(10,9,8,0.25);
   }
   ```
   Highlight at top-left, ambient shadow bottom-right, soft drop
   shadow on the page. Globules **always have shadows**; flat panels
   never do. A chain should overlap its own globules by 8–24px so it
   reads as a connected cluster, not a row.
3. **Pattern globules** — exactly 1 in 4 globules carries a pattern:
   zebra stripes, polka dots, or a halftone gradient (see "Required
   surfaces" for textures). Never two patterns on adjacent globules.
4. **Editorial masthead** — top of the page: small spaced-caps
   Playfair masthead (`JULI · 2026 ·`) centered or top-left, with a
   single Ink rule beneath at 1px.
5. **Section badge** — a small ~88×88 cream square holding the issue
   numeral set in Playfair (`N°2`) above a JetBrains Mono uppercase
   caption (`WIRTSCHAFT` / `MUSIK` / `KALENDER`) and a date strip
   (`19. & 20. JULI · DESIGNFORUM · WIEN`). Always anchored mid-right
   or bottom-right of the hero.
6. **Stamp footer** — tiny mono uppercase three-line stamp bottom-left
   reading e.g. `EUROPEAN / DESIGN × BUSINESS / DIALOGUE 2026`. The
   `×` is mandatory and tracked.
7. **One globule = one data point** — when used as an icon, each
   single globule represents one item: a track, an attendee, a color
   sample, a tag. Globule size encodes magnitude.
8. **Vertical caption rotation** — at least one piece of mono caption
   text per page is rotated 90° (writing-mode vertical-rl), usually
   inside or beside a giant letter.

## Components
Use **Tailwind CSS** (CDN). Component shapes:
- **Buttons (primary)**: square corners, Ink fill, Paper text in Inter
  600 uppercase tracked `0.18em`, padding `14px 22px`, prefixed with
  one tiny 8px globule (any color). Hover: globule grows to 12px.
- **Buttons (secondary)**: Paper fill, 1.5px Ink border, Ink text, same
  typography. Hover: background becomes Paper Soft.
- **Buttons (globule)**: full-round pill button using a 3D globule
  gradient (Cyan or Magenta), Paper text Inter 700, 14px. Used rarely
  for the single "play" / "subscribe" action.
- **Inputs**: bottom-border-only (1.5px Ink), transparent background,
  Ink text. Focus border becomes Magenta or Cyan (matching the section
  globule). Label above input is mono caps tracked `0.22em`.
- **Cards / panels**: 1px Ink border on Paper, no shadow. Headline in
  Archivo Black, label in mono caps. Optional: one small globule
  floats at the top-right corner of the card as a category dot.
- **Section dividers**: a 1px Ink rule with a single 14px globule
  centered on the rule. Replaces every `<hr>`.
- **Tags / pills**: pill-shaped Paper Soft background with a 6px
  globule dot prefix and uppercase mono label.
- **Tables / TOCs**: 1px Ink divide-y rows. Roman numeral or large
  Archivo Black numeral on the left, Inter title in the middle,
  JetBrains Mono time/coord on the right.
- **Hero monogram**: a single Archivo Black letter at 18–32rem, with
  one or two globules pinned to its counter / overlap.
- **Globule cluster module**: the signature page motif — a 380–520px
  tall block holding 10–18 globules arranged in a diagonal chain.

Optional libraries: none. **Do not** pull in shadcn, MUI, DaisyUI, or
any icon set. The icon system is exactly: the **globule** (any size,
any of 6 colors), the **×** glyph (Ink only, in stamps and
multipliers), `·` middle dot for breadcrumbs, `→` arrow for CTAs, and
`№` for issue markers. Banned: emoji, lucide / heroicons, glass /
blur, soft pastel gradients on flat panels, drop shadows on anything
that isn't a globule.

## Logos & shapes
- **Wordmark + monogram**:
  - Monogram: a single Archivo Black letter (here `G`) in Ink on
    Paper. To the right or sitting inside the counter, one signature
    Cyan globule. The pair `G + globule` is the logo.
  - Wordmark: `GLOBULE` set in Archivo Black at 2–3rem, tracked
    `-0.03em`. A small Playfair italic descriptor (`a chromatic
    quarterly`) may sit underneath in Ink.
- **Allowed shapes**: rectangles (square corners only), circles
  (globules and pill dots), the 6-color globule, the giant Archivo
  Black letterform. Pattern fills allowed only on globules.
- **Banned**: drop shadows on flat surfaces (only globules get them),
  glass / blur, gradients on flat panels above 12% tint, organic
  blob shapes that aren't perfect spheres, emoji, neon glow, chrome
  bevels, pastel palettes.

## Accessibility
Ink (#0A0908) on Paper (#F2EAD0) passes AAA at all sizes — the
backbone. The six globule colors are decorative on globules only;
**never** set body text in any of them. Pattern globules with zebra
stripes always need an adjacent non-pattern label, so the meaning is
carried by mono text, not the pattern alone.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`, fonts
from Google Fonts (Archivo Black, Playfair Display, Inter, JetBrains
Mono). Apply the palette, surfaces, motifs, typography rules, and
component shapes exactly as specified above.

The page should look like a Designforum Wien cultural quarterly opened
flat on a worktable — cream paper, a massive black letter dominating
the spread, and a glossy chromatic globule chain twisting diagonally
through it. Apply the kit to **cultural-software surfaces**: event
programs, exhibition catalogs, color tools, playlist broadcasts, issue
archives. Avoid generic dashboards, SaaS landing pages, or fintech —
this is a quarterly, not a console.
