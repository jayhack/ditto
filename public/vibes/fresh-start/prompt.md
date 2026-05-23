You are styling a web UI in the **Fresh Start** aesthetic. Apply the
design kit below verbatim — do not invent new colors, fonts, or motifs.

## Mood
A wellness-tech company shot at golden hour. The product is slow,
sunlit, outdoor-friendly hardware (paper-like reading tablets, gentle
e-ink devices, calm-tech accessories) and the brand voice is part
camp-counselor, part Shaker workshop, part neurologist on a sabbatical.
Cream-paper backgrounds dominate, deep moss and forest greens hold the
nature photography, a single rationed **Marigold orange** carries every
CTA, and a warm **Amber glow** stands in for the device's backlit
screen. Type does two things: a calm humanist **serif** for headlines
(*"A computer that takes its time"*) with italic emphasis on the words
that carry the brand promise (*"a __device__ that lives __outside__"*),
and a friendly **rounded sans wordmark** set huge and lowercase
(`hearth`) in Marigold once per page.

Every interactive control is a **fully-rounded pill** with a soft
dark drop shadow. A **floating nav cluster** lives top-right (cream
container, text links + the Marigold ORDER NOW pill). A **newsletter
chip** lives bottom-right (cream pill with thin Marigold border).
A **Daylight-Kids-style circular stamp** badges special editions
(text-on-arc wrapping a Marigold disc). One **starburst radial** of
thin tapered black lines per page acts as the "vision" / mission
divider. The page flips to **night mode** in its last act: deep coffee
background with the device's amber glow taking over.

The page should feel like a beautifully shot product monograph for
something you'd give your sister as a wedding present — calm, warm,
intentional, with one perfectly rationed pop of orange doing all the
work.

## Palette (use these hex values — no substitutions)
- Paper:        #F5EFE6  (primary background — warm cream, the page)
- Cream Warm:   #EDE3D2  (secondary surfaces, photo card mats)
- Marigold:     #F0962D  (the only CTA color — pure pumpkin orange)
- Marigold Deep:#C97818  (hover, deeper variant, ring of stamps)
- Amber Glow:   #FFB74D  (warm screen-backlight glow, night-mode CTA)
- Moss:         #4A5836  (forest green — nature photo abstractions)
- Moss Deep:    #2F3A22  (deeper moss for shadow side of photos)
- Coffee:       #2A2218  (default text, dark cards, footer)
- Charcoal:     #0F0C08  (night-mode background, deepest dark)

Default page background is **Paper (#F5EFE6)**. Default body text is
**Coffee (#2A2218)**. Mono labels and muted captions are Coffee at
60% opacity.

**Discipline rule (this vibe is built on it):** Marigold is rationed.
Use it for: every primary CTA pill (`ORDER NOW`, `GET UPDATES`, `READ
MORE`), one circular stamp badge per page, the wordmark, and the thin
border on the floating newsletter chip — **and nothing else**. If
you've used Marigold on a card background, a hairline rule, or body
type, you've broken the vibe. Sub it for Coffee.

Amber Glow appears **only** inside the night-mode section as a device
backlight; it never decorates a button on a paper background.

## Required gradients
The system permits exactly three gradients:

1. **The sectional hero card** (used on the card thumbnail in the
   gallery; never on a real surface):
   ```
   linear-gradient(135deg,
     #F5EFE6 0%, #F5EFE6 35%,
     #F0962D 35%, #F0962D 62%,
     #2A2218 62%, #0F0C08 100%)
   ```
2. **The amber-glow screen** (only inside the night-mode section, on
   the simulated device screen):
   ```
   radial-gradient(ellipse at 50% 50%,
     #FFB74D 0%, #F0962D 50%, #C97818 85%, #2A2218 100%)
   ```
3. **The moss field** (CSS abstraction standing in for nature
   photography on the hero):
   ```
   radial-gradient(circle at 18% 30%, #5A6B40 0%, transparent 14%),
   radial-gradient(circle at 64% 22%, #3F4D2D 0%, transparent 12%),
   radial-gradient(circle at 38% 70%, #4A5836 0%, transparent 18%),
   radial-gradient(circle at 82% 80%, #2F3A22 0%, transparent 22%),
   linear-gradient(135deg, #4A5836 0%, #2F3A22 100%)
   ```

Beyond those three: no glass, no blur, no chrome, no neon glow. Flat
fields only on every other surface.

## Typography
Load these from Google Fonts:

- **Display serif (headlines + italic emphasis)**: `"Newsreader"` —
  weights 400 / 500 / 600 in both roman and italic. Set
  `font-variation-settings: "opsz" 36;` at headline size for the
  warmest cut. Tight `letter-spacing: -0.015em`, `line-height: 1.05`.
  Roman 500 is the default; **italic** is reserved for 1–3 emphasis
  words per headline (the brand promise: *device*, *outside*, *slow*,
  *paper*, *outdoors*, *every day*).
- **Wordmark sans (the brand mark)**: `"Hanken Grotesk"` weight 800 —
  set lowercase, tracked `-0.04em`, color Marigold. Used at
  clamp(7rem, 18vw, 16rem) for the big page-closer wordmark and at
  17px for the small nav wordmark. **The wordmark is the only place
  Hanken Grotesk 800 is allowed at a large size.**
- **Body sans**: `"Inter"` — weights 400 / 500 / 600. 16–18px,
  line-height 1.5, sentence case.
- **Mono (chip text, spec labels, timestamps)**: `"JetBrains Mono"` —
  weight 500 / 600. ALWAYS uppercase, ALWAYS `letter-spacing:
  0.18em`. Used for `GET UPDATES · NO SPAM`, `LIMITED EDITION`,
  `SHIPS WITHIN 3–5 BUSINESS DAYS`, spec column headers.

Type rules:
- **Italic emphasis pattern**: every hero headline has at least one
  italic word and at most three. The italic words are the brand
  promise (the nouns and adjectives that distinguish the product).
- **Roman default**: body, captions, navigation, button copy are
  never italic.
- **Small-caps mono**: every photo card has a `LABEL · CATEGORY` mono
  line above the title.

## Visual motifs (include at least 7 per page)
1. **Floating nav cluster (top-right, persistent)** — A Paper-fill,
   28px rounded container holding inline text links (`Home`, `Product`,
   `FAQ`) with a single Marigold `ORDER NOW →` pill flush right.
   Soft Coffee/15% drop shadow. Lives sticky in the top-right of
   every viewport — it doesn't span the page like a traditional nav.
2. **Newsletter chip (bottom-right, persistent)** — A Paper-fill,
   24px rounded pill with a 1.5px Marigold border. Inside: a 15px
   Newsreader 500 "Newsletter" title + a mono uppercase
   `GET UPDATES · NO SPAM` subline + a small ✕ dismiss in the
   corner. Always visible.
3. **Marigold ORDER NOW pill** — The signature CTA. Full-round pill,
   Marigold fill, Coffee/Paper text 13px JetBrains Mono uppercase
   tracked 0.18em, trailing `→` arrow 10px after the text. 4px Coffee
   soft drop shadow. Min-width 200px on the page-closer variant
   (`ORDER NOW` centered, with a mono subline "Ships within 3–5
   business days" 16px below it).
4. **Circular stamp badge** — A 110px Marigold disc with a 4px
   Marigold Deep ring offset 6px outside. Text wraps the ring via
   SVG `textPath` (`LIMITED ★ FAMILY ★ COLLECTION ★`) and a 2-line
   center wordmark sits inside (`hearth / KIDS` in Hanken 800
   Coffee). Used once per page max.
5. **Starburst radial** — 24–32 thin black lines tapering from a
   center point outward, lengths varying 60–110px so the burst feels
   organic, not mechanical. Rendered as inline SVG with `<line>`
   elements rotated around 0,0. Used as the "vision" / mission
   divider — appears once per page maximum.
6. **Italic-emphasis serif headlines** — Newsreader roman with 1–3
   italic emphasis words ("it's a *device* that lives *outside*",
   "*slow* tech for *every* day"). Always sentence case, never
   all-caps.
7. **Stroke-icon comparison row** — 3 thin (1.5px) black SVG line
   icons in a row — eye / battery / sun — with a small body label
   below each. Hand-drawn-looking, never crisp. Sits inside a
   Cream Warm rounded card.
8. **Tweet-style testimonial card** — Coffee fill, 18px rounded,
   contains a 32px round avatar + name + handle/role + quote in
   Newsreader 500 16px + a JetBrains Mono uppercase timestamp
   (`8:28 PM · MAY 23, 2026`). Avatar tints follow the palette
   (Marigold, Moss, Cream Warm).
9. **Dive-deeper dark icon cards** — 4 Coffee-fill cards in a row,
   each with a 1.5px Cream Warm stroke icon, a mono uppercase
   category label, and a small Marigold pill button at the bottom
   (`PRODUCT →`).
10. **Spec column grid** — A 4-column flat layout of paired
    `LABEL` (mono Coffee/60) + `value` (Inter 500 Coffee) rows,
    grouped under Newsreader 500 section heads (`Display`,
    `Performance`, `Connectivity`, `Device`, `Software`).
11. **Realistic product copy** — Invented but plausible: company
    name **Hearth** (not Daylight), flagship **H-1** (not DC-1),
    employees `Maren Lukas` / `Rohan Patel` / `Sasha Vance`, spec
    numbers (`10.5in Live Paper`, `1600×1200 · 190dpi`,
    `8000mAh`, `MediaTek Helio G99`), realistic timestamps
    (`8:28 PM · May 23, 2026`). **No lorem ipsum.**
12. **Night-mode amber-glow section** — One section per page flips
    the canvas to Charcoal/Coffee, places a CSS-rendered device
    silhouette in the center, and lights the device screen with the
    amber-glow radial gradient. Coffee body type becomes Paper.
    The headline ("When the lights go off, enjoy the amber glow.")
    sits on the glowing screen.

## Components
Use **Tailwind CSS** (CDN). Component shapes:

- **Buttons**:
  - **Primary CTA**: Marigold fill, Coffee text, JetBrains Mono 600
    uppercase 13px tracked 0.18em, trailing `→`, padding `14px 28px`,
    fully rounded (`border-radius: 999px`), 4px Coffee/15 soft
    drop-shadow. Hover: Marigold Deep.
  - **Page-closer CTA**: Same as Primary but min-width 220px and
    paired with a centered 14px Coffee/60 Inter "Ships within 3–5
    business days" subline.
  - **Text link in nav**: Inter 500, 14px, Coffee text, no
    underline. Active link gets a 1px Marigold underline 4px below.
  - **Dark card pill button**: Marigold fill, Coffee text, same
    typography as Primary, used inside Coffee-fill cards in the
    Dive-deeper / Night-mode sections.
- **Inputs**: Paper fill on Paper bg (relies on a 1px Coffee/30
  border), 14px Inter, 22px radius, padding `13px 18px`. Placeholder
  = Coffee/50. Focus = 1.5px Coffee border.
- **Pills / chips** (mono uppercase): Cream Warm fill, Coffee mono
  500 11px tracked 0.18em, padding `7px 14px`, fully rounded.
- **Cards (photo product card)**: Cream Warm fill, **20px**
  border-radius, padding 0 with a 4:3 photo placeholder at the top
  (rounded only on top via `rounded-t-[20px]`) and a 20px padding
  body block. No drop shadow, no border. Title in Newsreader 500
  18–22px Coffee + Inter 14px Coffee/70 body.
- **Cards (dark icon card)**: Coffee fill, 18px radius, padding
  24px. 1.5px Cream Warm stroke icon at the top (40×40), a small
  mono uppercase label, and a Marigold pill button at the bottom.
- **Cards (testimonial)**: Coffee fill, 18px radius, padding 24px.
  Top row: 32px round avatar + name (Inter 600) + handle (Inter 500
  Coffee/60). Quote: Newsreader 500 16px Paper. Timestamp: mono
  Coffee/50 11px.
- **Newsletter floating chip**: Paper fill, 1.5px Marigold border,
  20px radius, 14px padding, fixed bottom-right with 24px offset
  from both edges, z-index high enough to overlay any section.
- **Floating nav cluster**: Paper fill, 28px radius, padding 6px
  10px, fixed top-right with 24px offset. Contains 3 text links +
  the Marigold ORDER NOW pill flush-right (the pill has no border
  radius reset — it stays full-round inside the cluster).

Optional libraries: **none beyond Tailwind + Google Fonts**. Do not
pull in shadcn, MUI, DaisyUI, or any icon set. The few icons used —
the `→` arrow, the eye / battery / sun stroke icons, the starburst
lines, the textPath stamp — are all hand-rolled SVG.

## Logos & shapes
- **Logo mark / wordmark**: there is no separate sigil for the brand.
  The wordmark **is** the logo: `hearth` set in Hanken Grotesk 800
  lowercase, tracked `-0.04em`, Marigold on Paper or Marigold on
  Coffee. A small monogram-size variant uses the lowercase letter
  `h` inside a 36px Marigold disc, Paper text.
- **Allowed shapes**: fully-rounded pills (buttons, chips, nav
  cluster), 18–24px rounded cards, 110px circular stamp, the
  starburst lines, 1.5px stroke icons. Photo placeholders are
  always 20px rounded rectangles.
- **Banned**: drop shadows over 12px, glass / blur / backdrop-filter
  on UI, hard 90° corners on any user surface (only the page edge
  is allowed to be square), neon glow, chrome / metallic, italic on
  body or button text (italic is for emphasis words in headlines
  only), Marigold on body type, lorem ipsum, emoji, lucide,
  heroicons, any icon library.

## Accessibility
Coffee on Paper is AAA. Coffee on Marigold passes AA at all sizes —
that's why CTA labels are Coffee, not Paper. Marigold on Paper is
decorative only — never set body text in Marigold; reserve it for
the wordmark and CTA fills. Paper on Coffee is AAA. Amber Glow on
Coffee is decorative (the night-mode screen) — never set readable
type in Amber Glow alone; readable type on a glowing screen must be
Coffee (the simulated black-on-amber e-ink look).

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`,
fonts from Google Fonts (Newsreader with `opsz` axis, Hanken Grotesk,
Inter, JetBrains Mono). Apply the palette, motifs, typography rules,
and component shapes exactly as specified above. The page should
read like a slow-tech wellness brand's product monograph — paper
cream canvases, one perfectly rationed pop of Marigold doing all
the work, italic emphasis carrying the brand promise, a night-mode
amber-glow finale, and a giant lowercase `hearth` wordmark closing
the page.
