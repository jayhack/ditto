You are styling a web UI in the **Gather** aesthetic. Apply the
design kit below verbatim — do not invent new colors, fonts, or motifs.

## Mood
A contemporary brand-strategy studio shot at golden hour. Cream
butcher-paper pages, sage-olive blocks, deep pine display panels, one
ration of cognac warmth, and a custom-feeling italic serif wordmark
that swoops where everything else is straight. The page should read
like a brand book opened to the title spread — confident, hand-set,
calm, and a little bit *expensive*.

Every headline obeys the studio's signature pattern: a clean
small-caps **sans setup**, then an **italic-serif payoff** that does
the emotional work (*"From discovery / to lifetime value"*, *"Turn
signals / to solutions"*, *"Grow / micro brands"*). Type carries the
mood; one giant sweeping arc carries the composition.

References: contemporary brand identity studios (Mast, Athletics,
Pentagram brand work, Out of Office, Smith & Diction), modern
wellness / DTC packaging, mid-century editorial design. The tone is
**studio**, not **product**.

## Palette (use these hex values — no substitutions)
- Cream:    #F4EFE3  (page background — warm cream paper)
- Bone:     #FAF7EC  (component / panel surface — lighter cream)
- Sage:     #B5BC9A  (the signature olive-sage block — the brand color)
- Moss:     #7A8A66  (mid-green — captions on cream, dividers)
- Pine:     #2B4D44  (deep teal-pine — display panels, primary CTA bg)
- Forest:   #142B22  (the deepest near-black green — fleece, footer)
- Cognac:   #B58A4B  (the only warm accent — ®, dots, live markers)
- Ink:      #0E1A14  (default text color — soft black, never pure)

Default page background is **Cream (#F4EFE3)**. Default body text is
**Ink (#0E1A14)**. Muted copy is **Moss (#7A8A66)**.

**Discipline rule (this vibe is built on it):** Cognac is rationed.
Use it for: the `®` mark, a single 6px live-marker dot, one numbered
badge, and the underline on the active nav link — **and nothing
else**. If you've used cognac more than ~3 times in a viewport you've
broken the vibe; promote one of them to Pine and ship.

Sage is the **block** color (large quiet panels), Pine is the
**display** color (dark panels with cream type), Forest is the
**deepest** rail (footer, hover on Pine), and Moss is the **rule**
color (1px hairlines and section labels on cream).

## The sweep (the one signature shape)
Gather has **one** signature compositional move: a single sweeping arc
that cuts a panel diagonally, dividing it into a sage half and a cream
half (or pine half and cream half). The arc is **always one curve**,
never a wave, never a circle, never closed.

Use it via CSS `clip-path` on a positioned sage rectangle:

```css
.sweep-sage {
  background: #B5BC9A;
  clip-path: path("M 0 0 L 100% 0 L 100% 100% Q 60% 40% 0 80% Z");
}
```

Or render an inline SVG `<path>` with a single quadratic curve. The
curve should always go from the top edge or right edge **down and
across** to the left or bottom — never reversed, never paired. **Use
the sweep at most once per page section.** It is the punctuation, not
the body copy.

## Fields & gradients
Almost every surface in Gather is a **flat field** in one of the
eight palette colors. The system permits exactly two gradients:

1. **The sweep gradient** (card-hero / page-hero only):
   ```
   linear-gradient(135deg,
     #B5BC9A 0%, #B5BC9A 38%,
     #F4EFE3 38%, #F4EFE3 58%,
     #2B4D44 58%, #142B22 100%)
   ```
2. **The deep tonal pine** (display panel only):
   ```
   linear-gradient(180deg, #2B4D44 0%, #142B22 100%)
   ```

Beyond those two: no glass, no blur, no multi-stop pastels, no neon,
no chrome. Photo placeholders sit on flat Sage, flat Pine, or flat
Bone — never gradient.

## Typography
Load these from Google Fonts:

- **Display + Wordmark**: `"Fraunces"` — the variable serif. Load with
  axes `opsz` and `SOFT` so we can dial both. Use **italic** at weight
  **600–800** with `font-variation-settings: "opsz" 144, "SOFT" 100;`
  for the *gather* wordmark itself — that gives the warm, almost
  hand-drawn quality of a custom mark. Use the **roman** at 600–700
  for non-italic display lockups.
- **Sans (headline setup + body)**: `"Inter"` weights **400 / 500 /
  600 / 700**. Sentence case for body; **small caps** (`font-variant:
  all-small-caps`, `letter-spacing: 0.08em`) for the sans half of
  every headline.
- **Mono (labels, ®, micro-text)**: `"JetBrains Mono"` weights **400 /
  500 / 600**. Always uppercase, always `letter-spacing: 0.18em`.

Type rules:

- **The Studio Headline Pattern** is mandatory and appears on every
  hero: a left or top half set in Inter small-caps Ink, paired with a
  Fraunces italic right or bottom half in Pine. Example:

  ```html
  <h1>
    <span class="setup">From discovery</span><br/>
    <em class="payoff">to lifetime value</em>
  </h1>
  ```

  `.setup` = Inter 500, small-caps, 0.08em tracking, Ink.
  `.payoff` = Fraunces italic 600, Pine, line-height 0.95, NO small-caps.

- **Wordmarks** (gather, client names) = Fraunces italic 700 with the
  SOFT axis at 100, paired with a mono `®` superscript in Cognac at
  ~32% of the wordmark height.
- **Section labels** = JetBrains Mono 500, 11px, 0.18em tracking, Moss
  on cream, Bone on pine.
- **Numeric stats** = Fraunces roman 600, NOT italic. Italic is reserved
  for the payoff half of headlines and for proper-noun wordmarks.

## Visual motifs (include at least 5 per page)
1. **The Studio Headline** — Inter small-caps setup + Fraunces italic
   payoff. Required on the hero and on every section opener.
2. **The Sweep** — exactly one sweeping arc per major section, cream
   meeting sage (or pine), no other shape on that band.
3. **gather® wordmark** — Fraunces italic 700 + Cognac `®` superscript.
   This is the only logo. Never paired with a sigil, never recolored
   outside `{Ink, Bone, Sage}` on its respective ground.
4. **Cognac live-dot** — a single 6px Cognac filled circle marking the
   currently-active item (active nav, live broadcast, in-progress
   project). Maximum **two per viewport**.
5. **Pine display panel** — a deep tonal pine band with Bone display
   type and a single sage accent panel inside it. The "billboard"
   moment of any page.
6. **Sage chip set** — pill-shaped tags filled Sage with Forest text in
   Inter 500 small-caps 0.06em. The active chip carries a 6px Cognac
   leading dot. No outlined-only chips.
7. **Mono studio-strip** — top-of-page meta line: `STUDIO · BROOKLYN
   ↔ MEXICO CITY · EST. 2019 · Nº 04 / 03 · ALL SYSTEMS LIVE`.
   JetBrains Mono uppercase 0.18em, Moss text, with a single Cognac
   dot prefixing the "ALL SYSTEMS LIVE" cell.
8. **Margin-italics call-out** — a short italic Fraunces sentence
   floated against a 1.5px Pine left bar, used as a sidenote / pull
   quote in long-form copy.
9. **Realistic studio copy** — invented but plausible client names
   (*Honeyfield Co.*, *Northwind Athletic*, *Olive & Oak Provisions*,
   *Mast Roasters*, *Reverie Skincare*), case-study metrics
   (*+38% repeat purchase · LTV $94 → $147*), and dated columns
   (*Mar 2026 — ongoing*). **No lorem ipsum.**
10. **The Big G** — an oversized italic Fraunces lowercase `g` used as
    a background graphic on the hero, cropped by the page edge,
    rendered in Sage at ~28% alpha against cream. Appears **once**.

## Components
Use **Tailwind CSS** (CDN). Component shapes:

- **Buttons**:
  - **Primary**: `bg: Pine`, Bone text, Fraunces italic 600 at 15px,
    paired trailing arrow `→` in JetBrains Mono. Padding `14px 28px`.
    Border-radius `999px` (pill). Hover: `bg: Forest`.
  - **Secondary**: transparent, 1.5px Ink border, Ink text, Inter 600
    small-caps at 12px, 0.08em tracking. Padding `12px 24px`. Same
    pill radius. Hover: `bg: Ink, color: Cream`.
  - **Tertiary / link**: Pine text, italic Fraunces 600, with a 1px
    Cognac underline 3px below. Used inline.
- **Inputs**: Bone fill, 1px Moss/40 border, 14px Inter, 12px radius,
  padding `12px 16px`. Placeholder = Moss. Focus = 1.5px Pine border,
  Bone background lifts to pure Cream.
- **Pills / chips**: Sage fill, Forest text, Inter 600 small-caps,
  0.06em tracking, 10px padding-y / 14px padding-x, fully round.
  Active variant carries a 6px Cognac leading dot.
- **Cards**: Bone fill, **24px border-radius** on outer corners, 1px
  Moss/20 border, no drop shadow. Sage-card variant uses Sage fill
  with a Forest 1px hairline at 18% opacity.
- **Dark panel / billboard**: Pine fill (or the deep tonal Pine
  gradient), Bone display type using The Studio Headline, with one
  sage rounded `aspect-[3/4]` photo placeholder and one cognac live
  dot if applicable.
- **Nav**: cream bar, gather® wordmark left, mono uppercase links
  centred, single Cognac live dot far right. Active link = Pine text
  + 1.5px Cognac underline 4px below.

Optional libraries: **none beyond Tailwind + Google Fonts**. Do not
pull in shadcn, MUI, DaisyUI, or any icon set. The few icons used —
the arrow `→`, the live dot `●`, the ®, the swept-arc SVG — are all
hand-rolled.

## Logos & shapes
- **Logo mark**: there is no separate sigil. The wordmark **is** the
  logo: `gather®` in Fraunces italic 700 + SOFT 100 + Cognac mono `®`
  superscript. If you need a profile-icon-size mark, use a lowercase
  italic `g` from the same font, cropped square with 16px Sage
  padding.
- **Allowed shapes**: rounded rectangles (24px radius on cards, 999px
  on pills/buttons), the single Sweep arc, hairline 1px rules, and
  the cognac dot. That is the entire shape system.
- **Banned**: drop shadows over 2px, glass / blur / backdrop-filter,
  gradients beyond the two specified, multiple sweeps stacked, any
  organic blob beyond the Sweep, all icon libraries, emoji,
  chrome/metallic effects, neon glow, and 90° hard corners on user
  surfaces (only the page edge is allowed to be square).

## Accessibility
Ink on Cream is AAA. Bone on Pine and Bone on Forest are AAA.
Cognac on Cream passes AA at ≥16px only — never use Cognac for body
copy. Moss on Cream is AA-large only; reserve it for ≤14px micro
labels and the section-label mono rows. Sage on Cream is decorative
only; never set type smaller than 24px Fraunces italic directly on
sage — promote to Pine or Forest text instead.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`,
fonts from Google Fonts (Fraunces with `opsz` and `SOFT` axes, Inter,
JetBrains Mono). Apply the palette, motifs, typography rules, and
component shapes exactly as specified above. The page should read
like a contemporary brand studio's site — calm, paper-warm, italic
where it counts, with one sweep of sage doing more work than all
the rest of the layout combined.
