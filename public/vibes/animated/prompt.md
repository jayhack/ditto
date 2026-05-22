You are styling a web UI in the **Animated** aesthetic. Apply the design
kit below verbatim — do not invent new colors, fonts, or motifs.

## Mood
A nature-aligned venture studio printed on mineral-soft paper. Each
section gets its own pale-tinted canvas — sage mineral, dusty lavender,
meadow green, almost-white — and every canvas is interrupted by one
big photographic 3D biological subject (driftwood with moss, anemone
clusters, lichen mats, sponge architecture) that the type either
floats over or cuts through. Type does two contrasting things at once:
a quiet transitional **serif hero** ("Growing nature-aligned ventures")
floats over the image, and bold **stencil-cut display heads** ("How we
work", "We are your partner", "Meet our team") anchor the sections
below. Every UI control is a **wobbly pill-blob** — soft, asymmetric,
two-corner-overlapping rounded shapes — never a hard rectangle. One
ration of warm **Citron** yellow-green is the CTA color; everything
else is mineral or biological.

The page should feel like a beautifully printed bio-tech monograph
opened on a studio table — confident but slow, organic but rigorous,
softly tinted but loud where it counts.

## Palette (use these hex values — no substitutions)
- Mineral:  #A8B0A6  (hero canvas — dusty sage-grey, the dominant ground)
- Lavender: #BAB5D1  (about / partner canvas — dusty cool purple-grey)
- Meadow:   #DDE4C4  (who-we-work-with canvas — pale yellow-green)
- Cream:    #FAF8F0  (paper warm white — cards, light alt surfaces)
- Citron:   #DEE89E  (the only CTA color — yellow-green pill fill)
- Sap:      #C9D49C  (duotone tint on portraits, secondary pills)
- Slate:    #5C6660  (body text muted, mono labels on tinted canvas)
- Ink:      #0E1612  (default text, near-black with green undertone)

Default body text is **Ink (#0E1612)**. Default mono labels are
**Slate (#5C6660)**. The dominant page background rotates section by
section through Mineral → Cream → Lavender → Cream → Meadow → Cream
so the gallery reads like a layered print quarterly. Cards on tinted
sections are always **Cream**.

**Discipline rule:** Citron is the only warm color and the only CTA
fill. Use it for the primary "KNOW MORE" / "READ MORE" / "MEET OUR
TEAM" pills and nothing else. Never set body type on Citron — it's
decoration for buttons. Sap is its quieter cousin used as a duotone
tint on portraits and as a secondary chip background.

## Required gradients
The system only permits two gradients. Every other surface is a flat
field.

1. **The hero card gradient** (multi-section sampler, card thumbnails
   only — never on a UX surface):
   ```
   linear-gradient(135deg,
     #A8B0A6 0%, #A8B0A6 26%,
     #BAB5D1 26%, #BAB5D1 52%,
     #DDE4C4 52%, #DDE4C4 78%,
     #DEE89E 78%, #DEE89E 100%)
   ```
2. **The duotone portrait gradient** (applied to grayscale portraits
   via `mix-blend-mode: multiply` on a Sap/Citron block):
   ```
   linear-gradient(180deg, #C9D49C 0%, #DEE89E 100%)
   ```

No glass, no blur, no chrome, no neon glow. Photos sit on flat
Mineral, Lavender, or Cream — never inside a gradient.

## Typography
Load these from Google Fonts:

- **Hero serif (display)**: `"Fraunces"` — roman 400 / 500. Used at
  clamp(4rem, 10vw, 9rem) for the studio's hero line ("Growing
  nature-aligned ventures"). Set `font-variation-settings: "opsz" 144,
  "SOFT" 50;` and a tight `letter-spacing: -0.02em`, `line-height:
  0.92`. **Never italic** in this vibe.
- **Stencil display (section heads)**: `"Workbench"` — Google's
  variable stencil font. Use weight 400 at clamp(3rem, 6vw, 5rem) for
  every section opener ("How we work", "We are your partner", "Meet
  our team"). Set `font-variation-settings: "BLED" 0, "SCAN" 0;` for
  the cleanest cuts. Color is always **Ink** on a tinted canvas,
  **never** Cream or Citron. Always sentence case.
- **Body sans**: `"Inter"` — weights 400 / 500 / 600. Sentence case,
  comfortable 16–18px line, 1.5 line-height.
- **Mono labels (numbered section indices, "KNOW MORE", chip text)**:
  `"JetBrains Mono"` — weight 500 / 600. ALWAYS uppercase, ALWAYS
  `letter-spacing: 0.22em`. Used for `001/ ABOUT`, `002/ MISSION`,
  `006/ TEAM`, `CONTACT +`, `MENU`, person-role pills.

Type rules:
- **Hero pattern**: Fraunces serif headline floats *on top of* a
  biological 3D subject. The subject extends out beyond the headline
  on both sides, so the type "cuts" through it.
- **Section pattern**: numbered mono index (`002/ MISSION`) on a
  perfectly centered single line above the stencil display head, with
  generous 24px breathing room between them. The stencil head sits
  left-aligned or centered, never right-aligned.
- **Hero serif is never italic.** Stencil display is never bold over
  weight 400. Mono labels are never lowercase.

## Visual motifs (include at least 6 per page)
1. **Mineral hero canvas** — full-bleed sage-grey panel, the
   Fraunces serif headline floated over a CSS/SVG-rendered driftwood
   subject (a horizontal earthy organic blob with 3–5 Citron/Sap moss
   dots). The headline must overlap the subject vertically.
2. **Floating chip badges** — small wobbly-pill capsules scattered
   around the hero corners with mono uppercase labels like
   `TECHNOLOGY'S BOUNDLESS POTENTIAL`, `NATURE'S TIMELESS EXPERIENCE`,
   `FOR INNOVATION`. Each is Cream fill with a 1px Slate border and a
   thin dashed outer halo (1px Slate dashed offset 4px out).
3. **Numbered section index** — mono uppercase `001/ ABOUT`,
   `002/ MISSION`, `003/ STUDIO`, `004/ PARTNERS`, `005/ STORIES`,
   `006/ TEAM` printed as a single row above every section head.
   Slate text on tinted canvas, max-tracked.
4. **Stencil-cut display heads** — Workbench at clamp(3rem, 6vw,
   5rem), Ink on the section's tinted canvas. The cuts in the
   letterforms are the whole point — don't tighten the axes too far.
5. **Wobbly pill-blob buttons** — every interactive control uses the
   asymmetric pill: `border-radius: 36px 28px 38px 26px / 28px 22px
   30px 24px;`. Each carries a trailing mono glyph: `+` for
   expand/more, `⌄` for scroll-down, `→` for next.
6. **Citron CTA pill** — the only saturated color in the layout.
   Wobbly pill-blob shape, Citron fill, Ink mono uppercase text,
   tracking 0.22em. One Citron CTA per major section maximum.
7. **Dashed perimeter brackets** — super-thin 1px Slate dashed Ls in
   each of the four corners of every major panel, offset 24px inward.
   Decorative framing, never a full border.
8. **Biological CSS/SVG subjects** — every major section gets its own
   3D-feeling abstract organism, rendered with stacked CSS radial
   gradients and SVG `filter: blur()` shapes:
   - **Driftwood** (Mineral section): horizontal earthy blob with
     Citron + Sap dots layered as moss.
   - **Anemone** (Lavender section): central Lavender radial with
     Sap/Citron tubular extensions radiating outward.
   - **Lichen mat** (Meadow section): clustered Sap + Cream rounded
     blobs in a soft mosaic.
   - **Cell cluster** (any white section): pale circles in a tight
     hexagonal arrangement, Slate hairlines connecting them.
9. **Duotone portrait treatment** — every team photo / person card is
   tinted with the duotone portrait gradient (Sap → Citron). Each
   portrait card carries an overlaid wobbly-pill nameplate
   (`SANDRA REY` / `CEO`) bottom-left, Cream fill, Slate border, mono
   uppercase.
10. **Cookie banner mockup** — a stacked wobbly pill-blob at the
    bottom-left of the hero, reading "This website uses cookies."
    with `ACCEPT REFUSE PREFERENCES` mono uppercase row. Cream fill,
    Slate border, never dismissable in the preview — it's part of
    the vibe.
11. **Realistic studio copy** — invented but plausible portfolio
    names (`Mycelium Materials`, `Bloom Logistics`, `Tessellate
    Robotics`, `Lichen Labs`), invented founder names, and
    venture-studio language (`We don't consult, we co-build`, `We
    work side-by-side to turn R&D into revenue`). **No lorem
    ipsum.**

## Components
Use **Tailwind CSS** (CDN). Component shapes:

- **Buttons**:
  - **Primary (Citron CTA)**: Citron fill, Ink text, JetBrains Mono
    600 uppercase 12px, tracking 0.22em, padding `16px 28px`, wobbly
    pill-blob radius (see motif #5), trailing `+` or `⌄` glyph 10px
    after a 20px gap. Hover lifts to Sap.
  - **Secondary (Cream chip)**: Cream fill, 1px Slate border, Slate
    mono uppercase 11px, tracking 0.22em, padding `10px 18px`,
    wobbly pill-blob radius. Used for `MENU`, `CONTACT +`, chip
    badges. Hover: 1px Ink border.
  - **Tertiary (text link)**: Ink Inter 500 with a 1px Slate
    underline 3px below. Used inline only.
- **Inputs**: Cream fill, 1px Slate/40 border, 14px Inter, wobbly
  pill-blob radius (smaller: `24px 18px 26px 20px / 18px 14px 20px
  16px`), padding `14px 20px`. Placeholder = Slate. Focus = 1.5px
  Ink border.
- **Pills / chips** (the floating badge type): Cream fill, 1px Slate
  border, mono uppercase 10px, tracking 0.22em, padding `8px 16px`,
  wobbly pill-blob radius. **Always** wrapped in a dashed Slate
  halo offset 4px outward.
- **Cards**: Cream fill, **28px border-radius** on outer corners
  (still round but less wobbly than pills), 1px Slate/15 border, no
  drop shadow. Stencil display head + body Inter 400 + a Citron CTA
  pill at bottom.
- **Photo cards (portraits)**: 4:5 aspect, duotone gradient overlay
  (Sap → Citron via `mix-blend-mode: multiply`) on a grayscale
  base, 24px border-radius, with a bottom-left overlaid wobbly-pill
  nameplate.
- **Nav**: Mineral or Cream bar, `animated®` wordmark left wrapped
  in a wobbly-pill Cream capsule, mono uppercase links centered,
  `CONTACT +` wobbly-pill chip far right.

Optional libraries: **none beyond Tailwind + Google Fonts**. Do not
pull in shadcn, MUI, DaisyUI, or any icon set. Glyphs are exactly
`+`, `⌄`, `→`, `↗`, and `●` — all rendered as Unicode in JetBrains
Mono.

## Logos & shapes
- **Logo mark**: the wordmark **is** the logo: `animated` set in
  Workbench 400 (the stencil display face) at 18px, wrapped in a
  Cream wobbly-pill capsule with a 1px Slate border. A mono `®`
  superscript at 32% of the wordmark height optional.
- **Shape language**: wobbly pill-blobs (asymmetric border-radius)
  for every interactive control, soft 28px-radius cards for static
  surfaces, perfect circles only for biological dots (moss spots,
  cell clusters). Dashed-1px-Slate Ls for perimeter framing.
- **Banned**: hard 90° corners on any user surface (only the page
  edge is allowed to be square), drop shadows over 12px, glass /
  blur / backdrop-filter on UI, chrome / metallic effects, neon
  glow, all-caps display headlines (display is always sentence
  case), italic anywhere outside an optional pull-quote, emoji,
  lucide / heroicons, any organic blob that isn't either a
  biological subject or a wobbly pill.

## Accessibility
Ink on Mineral, Lavender, Meadow, and Cream are all AA-large at
≥18px and AAA at ≥24px — body copy at 16–18px is safe. Slate on
Cream passes AA at ≥14px — reserve it for mono labels and chip
text. Cream on Ink passes AAA. **Never set body type on Citron** —
it only passes AA-large at 18px+, and the vibe asks for Citron to
stay reserved for CTAs. Mono labels on tinted canvases (Mineral,
Lavender, Meadow) must be Slate, not Cream, to maintain contrast.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`,
fonts from Google Fonts (Fraunces with `opsz` + `SOFT` axes,
Workbench with `BLED` + `SCAN` axes, Inter, JetBrains Mono). Apply
the palette, motifs, typography rules, and component shapes
exactly as specified above. The page should read like a
nature-aligned venture studio's printed monograph — mineral-soft
canvases stacked vertically, each interrupted by one biological 3D
subject, with stencil-cut heads, serif heroes, and wobbly Citron
pills doing all the work.
