You are styling a web UI in the **Oahu** aesthetic. Apply this design kit verbatim: dark Oahu sunset, volcanic glow, slightly cartoonish curves, and very usable product surfaces. The motifs should hint at surfing, lava bursts, palm silhouettes, ocean at night, and tiki-lounge geometry without turning the UI into a souvenir shirt.

## Mood
A south-shore operations app after sunset: plum-black sky, hot lava orange, hibiscus pink, torchlight amber, wet volcanic rock, palm silhouettes, and only a thin line of moonlit ocean. The style is slightly cartoonish and loungey, with rounded forms and lava-burst accents, but the product UX stays serious: high contrast, clear hierarchy, readable schedules, and obvious focus states.

## Palette
- **Nightfall** `#170B24` - page background, nav shell, dark cards.
- **Volcanic Plum** `#2A1238` - elevated panels and quiet dark surfaces.
- **Lava Burst** `#FF4E1F` - primary action, warning, molten motif.
- **Ember** `#FF8A2A` - hover states, heat rings, secondary accents.
- **Torchlight** `#FFC857` - small highlights, badges, tiki-torch flame.
- **Hibiscus** `#E93F6F` - flower accents and urgent highlights.
- **Palm Deep** `#1F6F45` - success, palm silhouettes, vegetation hints.
- **Moonfoam** `#FFF0D6` - primary text on dark and card interiors.

Use Moonfoam for readable text on dark surfaces. Lava Burst and Ember can carry Nightfall text in large buttons, but never use Torchlight as small body text on dark. Keep all key product data on Volcanic Plum or Moonfoam cards, never directly on busy lava-burst gradients.

## Required Gradients
- **Oahu sunset**: `linear-gradient(135deg, #170B24 0%, #2A1238 28%, #E93F6F 55%, #FF4E1F 76%, #FFC857 100%)`
- **Lava burst**: `radial-gradient(circle at 48% 54%, #FFC857 0%, #FF8A2A 18%, #FF4E1F 38%, #7A1E16 62%, transparent 63%)`
- **Torch panel**: `linear-gradient(180deg, #2A1238 0%, #170B24 70%, #3B160F 100%)`
- **Moonlit ocean line**: `linear-gradient(90deg, #170B24 0%, #1B4B5A 42%, #4FB6C1 52%, #1B4B5A 62%, #170B24 100%)`

## Typography
Load Google Fonts: **Baloo 2** for display, **Nunito Sans** for body, **JetBrains Mono** for numbers and labels. Display type uses Baloo 2 weight 800, sentence case or title case, `letter-spacing: -0.03em`, line-height 0.95. Body uses Nunito Sans 400/600/800 at 15-17px with line-height 1.55. Labels use JetBrains Mono 700 uppercase, `letter-spacing: 0.14em`, 10-12px.

## Visual Motifs
Use a **lava burst rosette**: concentric circles and short rounded rays in Torchlight, Ember, and Lava Burst, placed behind hero marks and empty states. Use a **moonlit wave line** as a thin teal contour, not a turquoise field. Add **palm shadow bands** as dark green-black diagonal leaf silhouettes. Use a **surf-fin marker** triangle with rounded corners for map pins, tab indicators, and logo accents. Add **tiki-lounge hints** as abstract torch posts, stacked rounded rectangles, chevrons, and carved notch patterns; never draw sacred masks, copied traditional motifs, or caricatures. Use **hibiscus sparks**: five tiny Hibiscus dots around a Torchlight center.

## Components
Buttons are rounded-full, 14px vertical / 22px horizontal, Nunito Sans 800. Primary is Lava Burst fill with Nightfall text and a 3px Torchlight hard shadow; hover shifts to Ember. Secondary is transparent, 2px Ember border, Moonfoam text, no blur. Danger/alert buttons use Hibiscus fill with Moonfoam text.

Cards use Volcanic Plum or Moonfoam, 24px radius, 1.5px Moonfoam/14 border, and soft but small `0 18px 36px rgba(0,0,0,0.22)` shadow. Product dashboards must keep dense tables readable: dark rows with Moonfoam text, JetBrains Mono numerics, 1px Ember/18 dividers, clear selected state in Lava Burst/18.

Inputs use Nightfall fill, 16px radius, 2px Ember/35 border, Moonfoam text, placeholder Moonfoam/45, focus ring `0 0 0 4px rgba(255,138,42,0.30)` plus Lava Burst border. Badges are pill shaped with a leading hibiscus spark or torch notch. Navigation uses a translucent Volcanic Plum pill bar over the Oahu sunset hero; active item gets Lava Burst fill and Nightfall text.

## Component Kits & Libraries
Use Tailwind CSS via CDN or project Tailwind. No full UI kit. Inline SVG and CSS are preferred for fins, lava bursts, torch posts, hibiscus sparks, ocean lines, and palm shadows. Optional icons must be simple rounded stroke icons, but avoid lucide defaults unless heavily customized.

## Logos & Shapes
Logo mark: a rounded Lava Burst surf-fin triangle rising from a Torchlight lava rosette, with two small tiki-torch notches at the base. Shape language is rounded, bubbly, and tactile: 16px inputs, 24px cards, full pills for chips/buttons, circular burst dots, and stacked rounded-rectangle tiki hints. Avoid sacred iconography, copied tribal patterns, real temple imagery, flags, mascots, photorealistic palm trees, neon nightclub palettes, and illegible novelty fonts.

## Accessibility
Maintain AA contrast for all functional text. Put text on Nightfall, Volcanic Plum, or Moonfoam panels when gradients are present. Motifs are decorative and must never be the only state indicator; pair color with labels, numbers, or icons. Motion, if added, should be slow and optional.

## Deliverable
Create a single HTML file that demonstrates the kit in order: identity, theme specification, and at least two real UX applications. Use realistic island product copy such as sunset surf lessons, night-market ordering, volcano-view shuttle operations, tide alerts, hotel concierge tasks, or torchlit event scheduling. The result should feel like a polished dark-mode Oahu app with lava-burst energy and usable product clarity.
