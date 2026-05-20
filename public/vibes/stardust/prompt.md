You are styling a web UI in the **Stardust** aesthetic. Apply the
design kit below verbatim — do not invent new colors, fonts, gradients,
or icons. The deep-purple cosmos is the page, the red halo bloom is
the signature, and every subject is a flat round orb tinted by a single
radial gradient.

## Mood
A late-night science explainer rendered as a children's picture book.
Awe-inspiring planetary subjects — suns, planets, cells, atoms, galaxies
— illustrated as **flat rounded orbs** filled with one continuous radial
gradient, set on a **deep-purple cosmos** with a soft **lighter purple
center vignette**, and lit from behind by a **hot-red halo bloom** so
the orb glows like a held-up lantern. Around every subject orbit tiny
**white star specks** and **clusters of yellow energy dots**, while a
**Lilac year pill** anchors the upper-left and a **white citation chip
with a play triangle** anchors the lower-right — every scene is a
sourced, dated, narrated frame from an educational broadcast. The feel
is curious, optimistic, big-picture, and a little bit cute: nothing is
photographic, everything is rendered, and the dark page lets the
saturated orbs do all the talking.

References: Munich pop-science explainer animation, modern children's
nonfiction picture books, planetary glyphs, scientific paper diagrams
reproduced as poster art. The vibe is *cosmic optimism* — endless
purple sky behind every chart, friendly orb shapes, no jagged edges
anywhere on the page.

The page's emotional center is always **one big orb glowing on a red
halo bloom** — only one hero subject per viewport, never two. Stats,
captions, and chrome orbit it.

## Palette (use these hex values — no substitutions)
- **Cosmos**  `#0F0728`  — deepest background, page edges, the void
- **Nebula**  `#1F1147`  — page surface mid-tone, card fill, panel bg
- **Lilac**   `#B197FC`  — year-pill fill, citation chip text, secondary outlines, hover accent
- **Mist**    `#F5F1FF`  — primary light text, citation chip fill, label text on dark
- **Halo**    `#FF2C45`  — signature red glow center, primary CTA fill, danger/heat
- **Solar**   `#FFD23F`  — energy dots, sun highlights, "active" indicator dots
- **Ocean**   `#2D7BEF`  — water / cool planet hemispheres, blue accents
- **Algae**   `#34D399`  — land / forest / cell membranes, green accents

Default page background = **Cosmos vignette** (radial gradient — see
below). Default body text = **Mist (#F5F1FF)**. Muted micro-copy =
**Lilac (#B197FC)**. The page is **always dark**; there is no light
mode. Saturated fills (Halo / Solar / Ocean / Algae) are reserved for
**orb subjects and small accent pills** — never as flat full-bleed
panels.

**Discipline rule.** The cosmos vignette + Nebula + Cosmos together
occupy **≥ 70%** of any rendered surface. Halo + Solar + Ocean + Algae
combined as flat fields occupy **≤ 15%** and almost always inside a
round orb or a small pill — never as a wall-to-wall background.

## Required gradients (use these strings exactly)

The **Cosmos vignette** — the entire page background, with a softer
purple bloom at the upper-center so the page never reads flat:

```
radial-gradient(ellipse 90% 65% at 50% 32%, #3A1F8C 0%, #1F1147 45%, #0F0728 100%)
```

The **Halo bloom** — the signature red radial glow that sits *behind*
every hero subject orb, ~1.6× the orb's diameter, never tighter than
that. Always layered as a single absolute-positioned div behind the
orb, never as a CSS shadow:

```
radial-gradient(circle at 50% 50%, rgba(255,44,69,0.55) 0%, rgba(255,44,69,0.22) 28%, rgba(255,44,69,0.05) 55%, rgba(255,44,69,0) 75%)
```

The **Solar orb** — the radial fill of any sun / star / energy
subject. Yellow center, orange mid, deep red rim:

```
radial-gradient(circle at 32% 28%, #FFE48A 0%, #FFD23F 26%, #FF8A2D 62%, #E0341B 100%)
```

The **Ocean orb** — the radial fill of any water-side hemisphere /
cool planet / blue subject:

```
radial-gradient(circle at 32% 28%, #7AB2FF 0%, #2D7BEF 50%, #173F9C 100%)
```

The **Algae orb** — the radial fill of any forest / cell / membrane /
green subject:

```
radial-gradient(circle at 32% 28%, #79EFC0 0%, #34D399 50%, #0E7A53 100%)
```

The **Lilac pill** — the year-pill fill (top-left of every hero):

```
linear-gradient(180deg, #C9B6FF 0%, #9F7FF5 100%)
```

No other gradients. No chrome, no glass, no sunset stripes, no
chromatic-aberration text shifts. Orbs are the **only** subjects that
get radial fills.

## Typography
Load from Google Fonts:

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=Nunito:wght@500;600;700;800;900&family=JetBrains+Mono:wght@500;700&display=swap"
  rel="stylesheet"
/>
```

- **Display + Body: `"Nunito"`** weights **500 / 600 / 700 / 800 / 900**.
  Nunito is the **only** sans face on the page — its rounded
  terminals are the entire reason the kit feels friendly. Display sizes
  use 900 weight, hero `clamp(3rem, 8.5vw, 6.5rem)`, line-height **0.96**,
  letter-spacing **-0.025em**. Body 16px Nunito 500, line-height **1.55**.
  Sub-heads Nunito 800 at 24–32px. Sentence case for headlines, never
  uppercase except inside pill labels.
- **Mono: `"JetBrains Mono"`** weights **500 / 700**. Used **only**
  inside the **year pill**, the **citation chip**, and any stat-tile
  metric label. Always **uppercase** with **tracking 0.12em** inside
  pills; metric labels tracked **0.18em**, 10–11px.

Type rules:
- Display is **always Mist (#F5F1FF)** on Cosmos. Never gradient text,
  never Halo display, never outlined display.
- The single allowed **emphasis** inside body copy is a Solar-yellow
  underline (1.5px, offset 3px) or a Lilac inline color swap — never
  bold + italic + color together.
- Italic is **banned**. Rounded warmth replaces italic emphasis.

## Visual motifs (include at least 7 per page)

1. **Cosmos vignette.** The entire page is the Cosmos vignette
   gradient. Never a flat dark fill. The lighter purple bloom belongs
   at roughly `50% 32%` — slightly above the visual center.
2. **Halo bloom.** Every hero subject orb sits on a Halo bloom
   layered behind it, sized at ~1.6× the orb diameter, anchored to the
   orb's center. Build it as an absolutely-positioned div, not a
   CSS box-shadow. There is **exactly one Halo bloom per viewport**.
3. **The Orb.** The signature subject. A perfect circle 240–460px
   filled with one of the four orb-gradients (Solar / Ocean / Algae /
   Halo). No outline, no border, no drop shadow. The radial highlight
   sits at `32% 28%` so the orb feels lit from the upper-left.
4. **Bisected orbs.** Pairs of orb-halves separated by a 1.5–2px
   Cosmos belt (the "equator"). Used for *before/after*, *day/night*,
   *hot/cool*. The dome-half always sits on top of the planet-half.
5. **Land patches.** Inside an Ocean orb, soft rounded blobs filled
   with Algae and Mist that follow the orb's curvature (clip to a
   circle). Land patches always have squidgy, friendly outlines — no
   accurate cartography, ever. White (Mist) patches are clouds.
6. **Energy dots.** Clusters of **6–14 Solar (#FFD23F) filled 4–10px
   circles** floating off the surface of a hot orb (Halo / Solar).
   They orbit a third of the orb's circumference and gradually fade in
   opacity from 100% → 40% as they move away from the body.
7. **Star specks.** **40–80 Mist 1–3px circles** scattered across the
   page (NOT a regular grid), at random opacities between 30% and 90%.
   Five or six of them are slightly larger (4–5px) and Lilac. Star
   specks live behind everything and provide atmospheric depth.
8. **The Year Pill.** Top-left of every hero scene. A 36–44px tall
   pill (fully round), Lilac-pill gradient fill, **JetBrains Mono 700
   uppercase Cosmos text tracked 0.12em** at 14–16px. Examples:
   `2050`, `13.8 BYA`, `T+04:21`, `2026 — Q3`. Never more than 8
   characters. No icons inside.
9. **The Citation Chip.** Bottom-right of every hero scene. A pill
   (fully round), Mist fill, **JetBrains Mono 700 uppercase Lilac
   text tracked 0.12em** at 11–12px, with a leading Halo `▶`
   play-triangle glyph (or SVG triangle). Example:
   `▶  Ng et al., 2025`. Real-sounding author + year citation only;
   never longer than two authors + et al.
10. **Stat bubble.** A rounded-3xl Nebula card with a 1.5px Lilac/25
    border and **no shadow**, containing one giant Nunito 900 stat in
    Mist + a 10px JetBrains Mono uppercase Lilac caption above it.
    Used for "predicted sea-level rise", "global avg temp", etc.

## Components
Use **Tailwind CSS** (CDN). All cards and containers use **rounded-3xl**
(24px) or larger. Buttons, pills, year pills, citation chips, and orbs
are **fully round**. There are no hard 90° corners anywhere except
SVG axis lines on micro-charts.

- **Buttons**:
  - **Primary** — `background: #FF2C45`, Mist text, Nunito **800**,
    sentence case at 15–16px, padding `14px 26px`, `border-radius:
    9999px`, no border, inner highlight `inset 0 2px 0 rgba(255,255,255,0.16)`,
    soft Halo glow `0 16px 28px -12px rgba(255,44,69,0.55)`. Hover:
    `background: #E01F36` and lift `transform: translateY(-1px)`.
  - **Secondary** — `background: transparent`, **1.5px solid Lilac
    (#B197FC)** border, Lilac text, Nunito 700 at 15px, padding
    `13px 25px`, `border-radius: 9999px`. Hover: background becomes
    `rgba(177,151,252,0.12)`.
  - **Tertiary / link** — Lilac text with a 1.5px Solar underline
    offset 3px. Hover swaps underline to Halo.

- **Inputs**: rounded-full Nebula background, 1.5px Lilac/30 border,
  Mist text 15px Nunito 500, padding `12px 20px`. Focus: border
  becomes Halo (1.5px), plus a small 6px Halo dot appears inside the
  right edge.

- **Badges / pills**: rounded-full. Three flavors:
  - **Year pill** — Lilac-pill gradient, Cosmos mono text (see motif 8).
  - **Tag pill** — Nebula fill, Lilac border 1px, Mist text Nunito 700
    sentence case 12px.
  - **Status pill** — One of Algae / Solar / Halo / Ocean filled, Cosmos
    text mono uppercase 10px tracked 0.12em (`LIVE`, `NEW`, `PREDICTED`).

- **Cards**: `background: #1F1147`, **`border-radius: 28px`**, **1.5px
  solid rgba(177,151,252,0.18)** border, no drop shadow (the page
  vignette provides the depth). Padding 24–32px. Section cards
  optionally get a tiny 6px Solar corner dot at the top-left.

- **Orb container**: the actual subject. Build it as a `<div>` with
  `border-radius: 9999px`, the chosen orb-gradient as `background`, an
  optional `clip-path: circle(50%)` only if land patches need to live
  inside. No `box-shadow` on the orb itself — depth comes from the
  Halo bloom layered behind it.

- **Tables / lists**: `divide-y` Lilac/15. Left column Nunito 700 Mist
  14px, body Mist 14px, right column JetBrains Mono 700 Solar 12px
  for numerics. Row hover: background `rgba(177,151,252,0.06)`.

Optional libraries: **none**. Hand-built from Tailwind + Google Fonts.
**Do not** pull in shadcn, MUI, DaisyUI, lucide, heroicons, or any
emoji-based icon set. Orbs and pills are the entire system.

## Logos & shapes

- **Logo mark**: a small planetary symbol — concentric circles.
  60×60 viewBox: a 24px-radius Halo orb at center, a 1.5px Lilac ring
  at radius 22, three 2px Solar energy dots orbiting at NE / S / NW
  positions on a phantom 30px-radius circle. Paired with the wordmark
  in Nunito **900** at the same x-height as the mark, sentence case.

  ```html
  <svg viewBox="0 0 60 60" width="40" height="40" aria-hidden="true">
    <circle cx="30" cy="30" r="30" fill="url(#halo-glow)" opacity="0.55"/>
    <defs>
      <radialGradient id="halo-glow">
        <stop offset="0%" stop-color="#FF2C45" stop-opacity="0.55"/>
        <stop offset="100%" stop-color="#FF2C45" stop-opacity="0"/>
      </radialGradient>
      <radialGradient id="orb-fill" cx="32%" cy="28%">
        <stop offset="0%" stop-color="#FFE48A"/>
        <stop offset="60%" stop-color="#FF8A2D"/>
        <stop offset="100%" stop-color="#E0341B"/>
      </radialGradient>
    </defs>
    <circle cx="30" cy="30" r="14" fill="url(#orb-fill)"/>
    <circle cx="30" cy="30" r="20" fill="none" stroke="#B197FC" stroke-width="1.5"/>
    <circle cx="46" cy="22" r="2" fill="#FFD23F"/>
    <circle cx="30" cy="50" r="2" fill="#FFD23F"/>
    <circle cx="14" cy="22" r="2" fill="#FFD23F"/>
  </svg>
  ```

- **Allowed shapes**: circles (all sizes), squircles at 24–32px
  radius, fully-round pills, soft cloud/land blobs clipped inside
  circles (the only place blobs are allowed), straight 1px Lilac/15
  divider lines. That's the entire shape language.

- **Banned**: hard 90° corners on any surface a user touches; outlined
  cartoon mascots; sharp triangles or stars; chromatic-aberration text;
  neon thin-line glow; glass / blur / backdrop-filter; sunset
  gradients on backgrounds; emoji; lucide / heroicons; italic text;
  drop shadows on flat text.

## Accessibility
Mist on Cosmos / Nebula passes AAA. Mist body text on Halo passes AA at
≥18px / 14px bold — so primary buttons use Nunito 800 16px. Lilac on
Cosmos passes AA at ≥14px and is **the only** acceptable color for
micro-copy below 14px on dark. Solar yellow has **insufficient
contrast** on Cosmos for body text — restrict Solar to dots, accents,
underlines, and tiny mono labels inside pills. Honor
`prefers-reduced-motion: reduce` — gate any ambient star-twinkle or
orb-pulse animations on that media query.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`, fonts
from Google Fonts (Nunito, JetBrains Mono). Build the cosmos vignette
as the `<body>` background, scatter Mist star specks via small absolute
divs (or a tiled SVG), construct each hero orb as a `<div>` with a
radial gradient + an absolutely-positioned Halo bloom layered behind
it, anchor a Lilac year pill at the top-left and a Mist citation chip
with a Halo play triangle at the bottom-right of every hero scene.
Build land patches as circle-clipped SVG paths in Algae and Mist.
Stats live in rounded-3xl Nebula cards with a tiny Solar corner dot.
The page should feel like a still frame from an unhurried explainer
about something beautiful and slightly terrifying — the cosmos behind
the curtain, illustrated cute.
