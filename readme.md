# Tresmares Capital — Design System

A design system reverse-engineered from screenshots of the **Tresmares Capital** website
(financial-solutions section). Tresmares is a pan-European specialist financier providing
**tailored capital to high-growth SMEs and private-equity managers**. Its four solution lines are:

- **Private Equity** — minority stakes in SMEs, strategic capital to support professionalization and accelerate growth.
- **Direct Lending** — tailored financing combining amortizable (TLA) and bullet (TLB) tranches for acquisitions, capex, M&A, dividends.
- **Fund of Funds**
- **Fund Financing**

> **Source & caveat.** This system was built **from three website screenshots only** — no codebase
> or Figma was provided. Colors were pixel-sampled from the screenshots; type and layout are
> faithful reconstructions, not extracted source. Treat measurements as close approximations.
> Reference screenshots live in `assets/ref-*.png`.

---

## Brand in one line
Swiss-editorial minimalism for finance: a warm-gray canvas, oversized neo-grotesque type that
overlaps high-key black-and-white imagery, and a single vivid red used with discipline.

---

## CONTENT FUNDAMENTALS

**Voice.** Confident, plain, institutional but human. The brand sells growth, not jargon —
though it is precise when describing instruments.

- **Headlines are short, verb-led, aspirational.** e.g. *"Drive to grow."* Two or three words,
  set enormous. They speak to the client's ambition, not the product.
- **Section titles are the literal product name** — *Private Equity*, *Direct Lending* — set as
  the hero, no embellishment.
- **Descriptive copy is a single tight paragraph**, sentence case, factual, ~20–40 words.
  e.g. *"Minority stakes in SMEs, with the aim of becoming strategic capital to support
  professionalization and accelerate growth."* / *"Tailored financing that can combine amortizable
  tranches (TLA) and non-amortizable tranches to maturity / bullet (TLB)…"*
- **Casing.** Headlines & nav: Title Case. Body: sentence case. Stat labels & eyebrows:
  ALL CAPS, tracked out (AUMS, EBITDA, TICKET, EMPLOYEES).
- **Numbers are terse and symbolic.** Euro-first, abbreviated, ranges with a double arrow:
  `€2.3bn+`, `€2m ↔ €25m`, `€5m ↔ €75m`. Employee counts are bare integers (`25`, `10`).
- **Links are verbs or labels, underlined, never buttons.** *"Know more"*, *"Financial Solutions"*, *"Scroll"*.
- **No emoji. No exclamation beyond the headline period.** No marketing fluff, no "!". The tone is
  calm and assured. First/second person are largely avoided — copy describes the offering, not "we".

---

## VISUAL FOUNDATIONS

**Color.** A near-monochrome system. The page sits on a warm light gray `#D4D5D4`; imagery heroes
lift to a high-key off-white `#F8F7F8`. All type is near-black `#2A2A2B`. The *only* chromatic
color is the signal red `#D51712`, used for: the large brand graphic block, the small status dot,
and active/hover accents. Muted gray `#9A9A99` marks inactive nav items. Red is never used for body
text or large copy — it is a graphic device.

**Type.** One neo-grotesque family does everything (we ship **Hanken Grotesk** as a substitute for
the site's licensed Helvetica-Now-class face). Display is set **huge, medium/regular weight, leading
≈0.92, tracking ≈-0.02em** and routinely overlaps imagery and the red block. Body is regular,
leading ≈1.35. Labels are small, **bold, UPPERCASE, +0.06em tracking**. There is no serif, no
secondary display face — hierarchy comes purely from scale and weight.

**Imagery.** High-key **black-and-white photography with visible film grain** — mountains in cloud,
dried plants in silhouette, water-droplet splatter. Always desaturated, always bright/airy (never
moody-dark). Imagery is full-bleed or large-centered and sits *behind* the display type. The red
brand block is composited over/under the photo so type, photo, and red interleave in z-order.

**The red mark.** A bold geometric red shape (offset rectangles / parallelogram bands forming a
stylized monogram) placed centrally, large, behind the headline. It reads as both logo and
art-direction. It clips/overlaps the photographic subject.

**Layout.** Corner-anchored editorial grid on a full-viewport canvas:
- top-left: vertical **section nav** (active = ink, others = muted gray, active marked by a red dot)
- bottom-left: **descriptive paragraph + underlined "Know more"** link
- right edge: **right-aligned stat stack** (label over value, hairline rhythm)
- center: oversized **headline + red mark + photo**
Generous margins; fixed elements; lots of negative space.

**Surfaces.** Flat. **No card shadows, no rounded corners** (radius ≈ 0; the red status dot is the
only circle). Dividers, when present, are 1px hairlines in `#BFC0BF`. No gradients, no blur, no glass.

**Borders & links.** Links are underlined text with a ~6px underline offset and 1px thickness;
hover slides the underline / shifts to red. Buttons (rare) are flat ink or outline, square corners.

**Motion.** Restrained and smooth: slow fades and gentle eases (`cubic-bezier(0.16,1,0.3,1)`),
~320–640ms. Headlines and images cross-fade on section change; the red dot pulses subtly. No bounce,
no spring, no parallax gimmickry beyond a slow image drift.

**Hover / press.** Hover: muted text → ink, or ink → red; underlines animate. Press: red darkens to
`#A80F0B`. No scaling/shrinking of elements.

---

## ICONOGRAPHY

The brand is **near-iconless by design** — meaning is carried by type, the red mark, and photography.
The only recurring glyphs are:
- the **red status dot** (a filled circle, ~9px) used as an active/attention marker;
- the **double-headed arrow `↔`** (Unicode U+2194) inside stat ranges (`€2m ↔ €25m`);
- **underlines** as the affordance for links.

No icon font, no SVG icon set, no emoji, no decorative line icons were observed. If an icon is ever
required, use a thin monoline set (e.g. Lucide via CDN) sparingly, in ink, at small size — and flag
it, since it departs from the source. Unicode arrows/dots are preferred over drawn icons.

---

## INDEX / MANIFEST

Root:
- `styles.css` — entry point (imports all tokens). **Link this.**
- `readme.md` — this file.
- `SKILL.md` — Agent-Skill wrapper.

`tokens/`
- `fonts.css` · `colors.css` · `typography.css` · `spacing.css`

`assets/`
- `ref-direct-lending.png`, `ref-private-equity.png`, `ref-hero.png` — source screenshots
- `img-mountain.png`, `img-plant-mark.png`, `img-splatter.png` — extracted B&W imagery crops

`guidelines/` — foundation specimen cards (Type, Colors, Spacing, Brand) shown in the Design System tab.

`components/` — reusable React primitives:
- `core/` → `Link`, `Button`
- `navigation/` → `SectionNav`
- `data/` → `StatList`
- `brand/` → `RedMark`, `Eyebrow`

`ui_kits/website/` — high-fidelity recreation of the financial-solutions section
(hero "Drive to grow" + solution screens). `index.html` is an interactive click-through.
