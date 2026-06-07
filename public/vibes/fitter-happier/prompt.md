You are styling a web UI in the **Fitter Happier** aesthetic. Apply
the design kit below verbatim — do not invent new colors, fonts, or
motifs. The reference is the late-90s art-school dystopia of an
overexposed cyan photograph of a motorway interchange, a bold black
sans-serif masthead, smeared digital aerosol scribbles, narrow
stencilled warning labels, and a single rationed alarm red.

## Mood
A surveillance bureau's annual report, photocopied at 3 a.m. inside
a fluorescent service-station office. Pale washed-cyan pages,
motion-blurred photography of empty roads, a heavy black wordmark
that looks photocopied from a Helvetica specimen book, hand-scrawled
white aerosol scribbles half-erased over the imagery, and narrow
stencil labels that read **`[ LOST CHILD ]`** the way a hazard sign
would. Mono catalog numbers, telemetry strips, and a JetBrains-set
checklist of corporate-optimisation slogans that scrolls in cold
italics — _fitter, happier, more productive, comfortable._ The page
should feel **anaesthetised, paranoid, slightly sublime** — never
neon, never warm, never decorative.

References: an overexposed photograph of a Connecticut highway
overpass with the contrast pushed; a printed-and-folded paranoid
zine; a transit authority alert poster from 1997; a band's CD-era
liner notes set in heavy Helvetica; a tape-deck VU meter.

## Palette (use these hex values — no substitutions)
- **Fog**:     `#E5EEF0`  (page background — pale washed cyan, the album's atmospheric haze)
- **Static**:  `#CDDEE3`  (alt panel surface — one shade up)
- **Wash**:    `#9FBFC9`  (mid cyan — the dominant photographic blue)
- **Cathode**: `#5A8FA1`  (mid-deep teal-blue — body emphasis, links)
- **Deep**:    `#1F4351`  (deepest blue, just before black)
- **Ink**:     `#0A0F12`  (THE heavy black — masthead, X marks, stencils)
- **Bone**:    `#FFFFFF`  (raised cards, highlights, scribble overlays)
- **Alarm**:   `#C2272D`  (rationed warning red — used sparingly for ALERTS only)

Default page background is **Fog (#E5EEF0)**. Default body text is
**Ink (#0A0F12)**. Muted captions are **Cathode (#5A8FA1)** or
Ink at 55% opacity. Large display text and the masthead are **Ink**.

**Discipline rule (this vibe is built on it):** Alarm is rationed.
Use it only for: the `[X]` warning marker on a single critical
status, the `LOST CHILD` stencil label class, an active critical
alert pip, and the `●` indicator on a "DANGER" telemetry row. **Never**
in body, never in buttons, never as a fill on a card. If you've
used Alarm in more than three places per viewport, escalate one to
Ink and ship. Alarm is a flare, not a hue.

Cathode is the only blue allowed on interactive text (links, hovers,
focus rings). Wash is for atmospheric backgrounds and decorative
streaks. Ink is the workhorse for type, borders, and the X mark.

## Gradients (only three, ever)
Almost every surface is a flat field in one of the eight palette
colors. The system permits exactly three gradients:

1. **The Fog Wash** (hero backdrop only — never on panels or buttons),
   an overexposed cyan photograph translated to CSS:
   ```
   background:
     radial-gradient(circle at 18% 22%, rgba(255,255,255,0.85) 0%, transparent 42%),
     radial-gradient(circle at 82% 8%,  rgba(255,255,255,0.55) 0%, transparent 38%),
     linear-gradient(135deg, #E5EEF0 0%, #BDD8DF 22%, #9FBFC9 48%, #5A8FA1 72%, #1F4351 92%, #0A0F12 100%);
   ```
2. **The Highway Streak** (full-bleed horizontal motion-blur band,
   used as section divider and loading bars):
   ```
   linear-gradient(90deg,
     transparent 0%, #BDD8DF 12%, #5A8FA1 36%,
     #FFFFFF 50%, #5A8FA1 64%, #BDD8DF 88%, transparent 100%)
   ```
3. **The Static Wash** (subtle Bone-to-Fog raised-card gradient):
   ```
   linear-gradient(180deg, #FFFFFF 0%, #E5EEF0 100%)
   ```

Beyond those three: no glass, no blur, no neon glow, no chrome, no
warm gradients, no multi-stop pastels. Cards sit on flat Bone or
flat Static. The Fog Wash appears **once per page**, full stop.

## Typography
Load these from Google Fonts:

- **Masthead + Display**: `"Archivo Black"` weight **900** only.
  Set in **all-caps** with `letter-spacing: -0.01em` for the
  masthead and `0` for sub-display. This is the single largest
  voice on the page — heavy, rectangular, unornamented.
- **Stencil / Warning labels**: `"Bebas Neue"` weight **400** only.
  Set **uppercase**, `letter-spacing: 0.10em`, used exclusively for
  `LOST CHILD`-style stencil warning labels and section headers
  inside square brackets. Never for body, never for buttons.
- **Body**: `"Inter"` weights **400 / 500 / 600**. Sentence-case
  for paragraphs. Body sits on Fog in Ink.
- **Mono (catalog codes, telemetry, the Fitter Happier list)**:
  `"JetBrains Mono"` weights **400 / 500 / 600**. Always
  uppercase for labels with `letter-spacing: 0.18em`. Roman case
  inside checklist items only.

Type rules:

- **The Masthead pattern** is mandatory on every hero. The masthead
  is a single Archivo Black wordmark, all-caps, set at
  `clamp(3.2rem, 9vw, 7rem)`, color **Ink**, with a tiny
  `RH ‧ CAT 03 / 12 ‧ 1997` mono-uppercase secondary lockup
  immediately above or to the right.
- **The stencil label pattern** — every section opener carries a
  Bebas Neue label inside square brackets:
  ```html
  <span class="stencil">[ § 02 / LOST CHILD ]</span>
  ```
  Color is **Ink** by default; label class `[ ALERT ]`,
  `[ LOST CHILD ]`, or `[ X ]` swaps the bracket character to
  Alarm.
- **The Fitter Happier list** — a JetBrains-Mono bulleted list,
  each item prefixed with a 9px `▢` square (Ink, hollow), set at
  13px line-height 1.85, color Ink at 78%. The first 2–3 items
  may be set in **Newsreader-italic-style** Inter italic 500
  Cathode for emphasis, but never the whole list. (Inter italic
  stands in for the Sprechgesang voice.)
- **Telemetry strips** — `BPM 76 · KEY Cm · CAT 03/12 · 1997`,
  JetBrains Mono 500, 11px tracked `0.22em`, color Ink at 55%.
  Always live directly under the masthead and at the top of every
  surveillance card.

## Visual motifs (include at least 6 per page)
1. **The masthead** — Archivo Black uppercase wordmark in Ink, with
   a mono catalog lockup. **Required** in every hero.
2. **The Fog Wash hero** — the cyan-to-Ink atmospheric gradient
   used exactly once per page as the hero backdrop, with the
   masthead reversed-out in Bone over its dark corner.
3. **The Highway Streak divider** — a 1.5–4px-tall horizontal
   motion-blur band of Wash + Bone + Cathode, used between major
   sections in place of any plain rule.
4. **The Lost Child stencil** — Bebas Neue uppercase warning label
   set inside square brackets, e.g. `[ LOST CHILD ]`, `[ NO
   SURPRISES ]`, `[ AIRBAG ]`, `[ ALERT 03 ]`. Brackets in Ink,
   the "danger" variant brackets in Alarm.
5. **The X mark** — a thick black SVG `×` (two crossed strokes,
   stroke-width 4) housed inside a Bone square with a 1.5px Ink
   border, ~28×28px, used as the "warning" marker on a single
   card per surface and as the favicon-style logo mark.
6. **The Scribble** — a hand-drawn SVG aerosol scribble path
   (irregular looping line, stroke Ink at 0.30 alpha or Bone at
   0.55 alpha over Wash), placed half-erased over hero imagery.
   One scribble per hero, never more.
7. **The Fitter Happier list** — a JetBrains-Mono `▢` checklist of
   corporate-optimisation slogans (`fitter`, `happier`, `more
   productive`, `comfortable, not drinking too much`, `regular
   exercise at the gym, three days a week`). Always 8–14 lines,
   always set on flat Bone, always uppercase header `[ INDEX ]`.
8. **Square-bracket section labels** — every section opener wraps
   its mono label in literal `[ ]` brackets with a single em-space
   inside: `[ § 01 / THE KIT ]`. Use as a substitute for any
   classic "section number" pattern.
9. **The catalog code** — a mono lockup `RH ‧ CAT 03 / 12 ‧ 1997`
   placed immediately to the right of (or above) the masthead.
   Always uppercase, always tracked `0.22em`. Numbers can change
   per page but the format does not.
10. **Realistic dystopian copy** — invented but plausible language.
    A paranoid optimiser ("subjects report 14% increase in
    voluntary smile-frequency"), a transit alert ("OVERPASS 7
    CLOSED · CHANNEL 4 ADVISORY"), a music catalog ("CATHODE
    CHILDREN · HOSTAGE CLIMATE · LP 03"), an AI safety log
    ("model passed 47/50 alignment probes · 1 critical"). **No
    lorem ipsum.** Ever.

## Components
Use **Tailwind CSS** (CDN). Component shapes:

- **Buttons**:
  - **Primary**: `bg: Ink` (`#0A0F12`), text `Bone`, Inter 600
    **uppercase** at 13px, `letter-spacing: 0.10em`, trailing
    glyph `→`. Padding `12px 18px`. Border-radius **2px**. Hover:
    background lifts to Deep (`#1F4351`). No shadow.
  - **Secondary**: transparent fill, **1.5px Ink border**, Ink
    text, Inter 500 uppercase 13px tracked 0.10em. Same 2px
    radius. Hover: background fills with Static (`#CDDEE3`).
  - **Tertiary / link**: Cathode text, Inter 500, no underline by
    default; on hover, 1.5px Cathode underline 3px below.
- **Inputs**: transparent fill, **bottom-border only 1.5px Ink**,
  Ink text Inter 400 at 14px, mono uppercase label above in
  Cathode. Focus = bottom-border Cathode (no glow). Never use a
  full-bordered input.
- **Cards**: Bone fill (`#FFFFFF`), **1.5px Ink border**, **2px**
  radius, no drop shadow. The "raised" card variant uses the
  Static Wash gradient. **Optional ornament**: a 28×28 `[X]`
  marker in the top-right corner.
- **Stencil labels**: Bebas Neue uppercase inside square brackets,
  Ink-on-Bone or Bone-on-Ink, never centered — always left-aligned
  in their container.
- **Tables / index rows**: 1px Ink `divide-y`, mono uppercase
  column headers in Cathode tracked 0.18em, body rows in Inter
  500 Ink, numeric columns in Archivo Black at 18px. Never zebra
  striped.
- **Pills / tags**: 1.5px Ink border, transparent fill, mono
  uppercase 10px tracked `0.18em`, Ink text. Active variant
  carries a leading 6px Cathode dot. Critical variant uses Alarm
  border + leading Alarm dot — limit to one per surface.
- **Nav**: Fog bar, `[X]` logo left, mono uppercase links
  centered, active link = 1.5px Ink underline 4px below text.

Optional libraries: **none beyond Tailwind + Google Fonts**. Do not
pull in shadcn, MUI, DaisyUI, or any icon set. The few icons used
— the `[X]` mark, the `▢` checkbox, the `→` arrow, the `●` status
pip, the `§` section glyph — are all hand-rolled in inline SVG or
unicode characters.

## Logos & shapes
- **Logo mark**: a thick black `×` housed inside a Bone square
  with a 1.5px Ink border, exactly 28×28px. Two crossed strokes,
  stroke-width 4, no rounding on the line caps. That is the
  entire mark. No monogram, no glyph beyond the X.
- **Wordmark**: `FITTER HAPPIER` (or whichever masthead the page
  is for) set in Archivo Black uppercase, paired with a tiny
  `RH ‧ CAT 03 / 12 ‧ 1997` mono catalog lockup.
- **Allowed shapes**: rectangles (2px radius on cards and
  buttons, 0px on stencils and the masthead box), 1px hairline
  rules, the `[X]` square, the Highway Streak band, the
  hand-drawn scribble path, and the `▢` checkbox glyph. Square
  brackets `[` and `]` count as a shape — they bracket every
  stencil label.
- **Banned**: drop shadows above 2px, glass / blur / backdrop-
  filter, neon glow, chrome / metallic effects, gradients beyond
  the three specified, organic blobs, illustration with humans,
  emoji, lucide / heroicons / any icon library, rounded-full
  pills, soft pastels, warm tones outside the rationed Alarm,
  90° hard corners on user-interactive surfaces (everything is
  2px radius — only stencil chrome stays sharp).

## Accessibility
Ink on Fog is AAA at all sizes. Cathode on Fog is AA at ≥18px —
never use Cathode for body copy <14px. Bone on Ink reversed-out is
AAA. Alarm (`#C2272D`) on Bone passes AA at ≥16px and AAA at
≥18px bold; never use Alarm for body copy under any circumstance.
The `[X]` mark must always include `aria-label="alert"` or similar;
the Lost Child stencil should never be the sole indicator of
status — pair with text every time.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`,
fonts from Google Fonts (Archivo Black, Bebas Neue, Inter, JetBrains
Mono). Apply the palette, motifs, typography rules, and component
shapes exactly as specified above. The page should read like the
front matter of a paranoid surveillance report with the corner of
an overexposed cyan photograph showing through the cover — pale,
heavy, slightly anaesthetised, with one alarm flare lighting the
margin.
