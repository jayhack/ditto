You are styling a web UI in the **Reason** aesthetic. Apply the
design kit below verbatim — do not invent new colors, fonts, or
motifs.

## Mood
An open-source developer tool's documentation, typeset by a 1960s
book designer at 2 a.m. Coffee-black pages, cream parchment text,
hairline rules between thoughts, and one ember of ochre orange
lighting whichever word is doing the most work. Every headline is a
transitional-serif sentence with one or two italic words pulled in
ember; everything else is mono small-caps tracked wide, the way a
colophon labels a chapter. The page should read like a printed
essay that someone accidentally compiled to a binary — confident,
unhurried, terminal-adjacent, **dark but never neon**.

References: the README of a well-loved CLI tool reformatted for
print; a Penguin Classics colophon; a `man` page rendered in a
quiet bookstore café; the title page of a slim O'Reilly volume; a
JetBrains Mono-set release journal.

## Palette (use these hex values — no substitutions)
- Espresso:   `#14100C`  (page background — deepest coffee, near black)
- Coffee:     `#1C1612`  (alt panel surface — one shade up)
- Cask:       `#241B15`  (terminal / raised card surface)
- Hearth:     `#3A2C20`  (hairline borders, muted dividers)
- Ember:      `#D97639`  (THE accent — italic words, dot logo, status)
- Flame:      `#E89055`  (lighter ember — hover, secondary accent)
- Parchment:  `#E8DFCC`  (default body text on dark)
- Bone:       `#F4ECD8`  (display text + primary button fill)

Default page background is **Espresso (#14100C)**. Default body
text is **Parchment (#E8DFCC)**. Muted captions are
**Parchment at 60%** or **Hearth-lightened** to roughly `#8A7F6D`.

**Discipline rule (this vibe is built on it):** Ember is rationed.
Use it for: italic words inside serif headlines (max **two** words
per headline), the single dot in the wordmark, the active-nav
underline, the terminal's `>` prompt, and the **one** corner-mark
glyph (`●`, `§`). **Nothing else** gets ember. If you have used
ember in more than 4 places per viewport, promote one of them to
Parchment and ship. Ember is a flame, not a wash.

Flame is for hover / focus only. Bone is **strictly** for primary
button fills and the single largest display element on the page.

## Gradients (only two, ever)
Almost every surface is a flat field in one of the eight palette
colors. The system permits exactly two gradients:

1. **The hero ember-coffee gradient** (card-hero and page-hero
   backdrop only — never on panels or buttons):
   ```
   linear-gradient(135deg,
     #14100C 0%, #1C1612 45%,
     #2A1F18 70%, #3A2C20 86%,
     #D97639 100%)
   ```
2. **The cask raised-panel gradient** (terminal window + one
   "billboard" card per page):
   ```
   linear-gradient(180deg, #241B15 0%, #14100C 100%)
   ```

Beyond those two: no glass, no blur, no neon glow, no chrome, no
multi-stop pastels. Cards sit on flat Coffee or flat Cask. The
ember-coffee gradient appears **once per page**, full stop.

## Typography
Load these from Google Fonts:

- **Display + Italic Payoff**: `"Newsreader"` — variable serif with
  beautiful, narrow italics. Use weights **400 / 500 / 600** and
  italic axis `1`. Optical-size axis at `opsz 24–32` for hero, `12`
  for body. Italic is the **only** way ember appears inside type.
- **Body + Small-caps Labels**: `"Inter"` weights **400 / 500 / 600
  / 700**. Sentence-case for paragraphs. Body sits on the dark page
  in Parchment.
- **Mono (labels, terminal, version strings, captions)**:
  `"JetBrains Mono"` weights **400 / 500 / 600**. Always uppercase,
  always `letter-spacing: 0.18em` for labels. Use roman case for
  terminal contents only.

Type rules:

- **The Reasoned Headline pattern** is mandatory on every section
  opener. The headline is a single sentence set in Newsreader roman
  at display size, with **one or two** italic words pulled into
  Ember. Example:
  ```html
  <h1>
    A <em class="ember">DeepSeek</em>-native coding
    <em class="ember">agent</em>, for your terminal.
  </h1>
  ```
  `.ember` = Newsreader **italic** 500, color `#D97639`, no
  underline, no extra weight bump, line-height matches surrounding
  roman.

- **Section marks** are required above every major section. Format:
  `§ 00 · REASONIX` set in JetBrains Mono 500, 11px, tracked
  `0.22em`, color `#E8DFCC` at 60% alpha, with the section number
  in ember.
- **Stat blocks** use Newsreader **italic** 500 for the number
  (huge, ~64–96px) with a small mono superscript unit (`%`, `×`,
  `MS`), paired below with a 1-line mono uppercase caption tracked
  `0.22em` in Parchment/60. Example: `94%` → `CACHE HIT`.
- **Nav links** are mono uppercase 11px tracked `0.22em` in
  Parchment/70; active link gets a 1.5px **Ember** underline 4px
  below the text — never an ember fill.

## Visual motifs (include at least 6 per page)
1. **The Reasoned Headline** — Newsreader roman sentence with one
   or two italic Ember words. Required on every hero and section
   opener.
2. **The section mark** — `§ 00 · REASONIX`, mono uppercase, ember
   numeral. Anchors the top of every section.
3. **The hairline rule** — a single 1px Hearth line under every
   section mark and between every major content band. Never thicker
   than 1px, never dashed.
4. **The dot logo** — a 10px filled Ember circle followed by
   `Reasonix` in JetBrains Mono 600 + a mono `DS · V0.51.0`
   secondary lockup in Parchment/50. The dot is the only sigil.
5. **Terminal window** — a Cask-gradient card with three macOS
   traffic-lights (Ember `#D97639`, soft amber `#E89055`, dark
   `#3A2C20`), a centered mono titlebar (`~/app · reasonix code`),
   and a real prompt session inside. Lives at least once per page,
   usually as the hero's right-hand counterpart.
6. **Terminal prompts** — `›` (lowercase guillemet single) in Ember
   for user input lines, `●` in ember for status/system lines,
   `…` for in-progress, all in JetBrains Mono. Never use `$`.
7. **Editorial stat row** — 3–5 stat blocks divided by 1px Hearth
   verticals, each one Newsreader-italic number + mono unit + mono
   small-caps caption.
8. **Mono telemetry strip** — meta line beneath the masthead like
   `V0.51.0 · OPEN SOURCE · MIT · BUILT FOR TERMINALS`, JetBrains
   Mono uppercase, 11px tracked `0.22em`, Parchment/60.
9. **Bilingual language toggle** — top-right `EN · 中文` set in mono
   uppercase, active language in Bone, inactive in Parchment/40.
   Use Noto Sans SC for the CJK character if needed.
10. **Realistic dev-tool copy** — invented but plausible model names
    (`deepseek-v4-flash`, `o3-reasoner`, `claude-haiku-3`), real
    command shapes (`npx reasonix code`, `reasonix login`), real
    metrics (`cache: 94.2% hit · session: 18m23s · cost: $0.043`).
    **No lorem ipsum.**

## Components
Use **Tailwind CSS** (CDN). Component shapes:

- **Buttons**:
  - **Primary**: `bg: Bone` (`#F4ECD8`), text `Espresso`, Inter 600
    sentence case at 14px, trailing mono `→`. Padding `10px 18px`.
    Border-radius **4px** (subtle, not pill). Hover: lift to pure
    white background. No shadow.
  - **Secondary**: transparent fill, 1px Hearth-light border
    (`rgba(232,223,204,0.18)`), Parchment text, Inter 500 at 14px.
    Same 4px radius. Hover: border lifts to Parchment/40.
  - **Tertiary / link**: Parchment text, Inter 500, no underline by
    default; on hover, 1.5px Ember underline 3px below.
- **Inputs**: transparent fill, bottom-border-only 1px Hearth,
  Parchment text Inter 400 at 14px, mono uppercase label above in
  Parchment/60. Focus = bottom-border Ember, no glow.
- **Cards**: Coffee fill (`#1C1612`), 1px Hearth border, **2px**
  radius (just enough to soften, never pill), no drop shadow. The
  "billboard" card variant uses the Cask raised-panel gradient.
- **Section labels**: mono uppercase 11px tracked `0.22em`, ember
  numeral + Parchment/60 body. Always preceded by `§`.
- **Tables / index rows**: 1px Hearth `divide-y`, mono uppercase
  column headers in Parchment/50, body rows in Inter 400 Parchment,
  numeric columns in Newsreader italic 500. Never zebra striped.
- **Pills / tags**: 1px Hearth border, transparent fill, mono
  uppercase 10px tracked `0.18em`, Parchment text. Active variant
  carries a leading 6px Ember dot.
- **Nav**: Espresso bar, dot-logo left, mono uppercase links
  centered, language toggle + GitHub/CTA right. Active link = Ember
  underline only, never ember fill.

Optional libraries: **none beyond Tailwind + Google Fonts**. Do not
pull in shadcn, MUI, DaisyUI, or any icon set. The few icons used
— the `●` dot, the `›` prompt, the `→` arrow, the `§` section
mark, the macOS traffic-lights — are all hand-rolled.

## Logos & shapes
- **Logo mark**: a single 10px **Ember filled circle** to the left
  of the wordmark. That is the entire mark. No monogram, no glyph,
  no abstract shape.
- **Wordmark**: `Reasonix` set in JetBrains Mono 600 (or in
  Newsreader roman 600 for "headline-style" lockups), paired with a
  tiny `DS · V0.51.0` secondary lockup in mono uppercase
  Parchment/50.
- **Allowed shapes**: rectangles (2px radius on cards, 4px on
  buttons), 1px hairline rules, the dot, the three macOS
  traffic-light circles, and the optional cursor block (a 6×12 Ember
  filled rect that blinks). That is the entire shape system.
- **Banned**: drop shadows above 2px, glass / blur /
  backdrop-filter, neon glow, chrome / metallic effects, gradients
  beyond the two specified, organic blobs, illustration, emoji,
  lucide / heroicons / any icon library, rounded-full pills, and
  90° hard corners on user surfaces (everything is 2–4px radius).

## Accessibility
Parchment on Espresso is AAA at all sizes. Bone on Espresso is
AAA. Ember on Espresso passes AA at ≥18px italic — never use Ember
for body copy, only for italic words inside display type and the
prompt `›`. Parchment/60 (`~#8A7F6D`) on Espresso is AA-large
only; reserve for ≤14px mono labels. Always pair the dot logo
with the wordmark — the dot alone is not accessible.

## Deliverable
A single HTML file. Tailwind from `https://cdn.tailwindcss.com`,
fonts from Google Fonts (Newsreader with italic axis, Inter,
JetBrains Mono, optional Noto Sans SC for the CJK toggle). Apply
the palette, motifs, typography rules, and component shapes
exactly as specified above. The page should read like the title
page of a quiet, well-typeset developer manual — coffee-dark,
italic where it counts, with one ember of ochre lighting the room.
