# CC-1 · Swiss / Editorial / Minimal

## 1. One-line definition

A type-led style that builds every page on a visible-or-felt modular grid, uses one or two neo-grotesk families in strong scale contrast, keeps colour to ink, paper and at most one signal hue, and treats whitespace, alignment and numbering as the main decoration.

It is the web version of the International Typographic Style (Zürich and Basel, 1950s–60s: Müller-Brockmann, Ruder, Hofmann, Gerstner), filtered through the Dutch modernists (Experimental Jetset, Wim Crouwel) and today's type foundries and studios (Grilli Type, Dinamo, Pangram Pangram, Locomotive, Obys).

---

## 2. Position on the map

| Axis | Score | Why |
|---|---|---|
| Classical ↔ Expressive | **1.5 / 5** (strongly classical) | Order, alignment, symmetry of rhythm and restraint are the whole point. The expressive part comes from scale and cropping, not ornament. |
| Cool ↔ Warm | **1.5 / 5** (cool) | Grotesk type, neutral greys and a single signal red read as rational and precise. Warmth comes only from photography and paper-tinted backgrounds. |
| Density | **2 / 5** | Large fields of empty space, but index pages (project lists, type specimens) can be quite dense tables. |
| Motion | **2 / 5** | Motion is functional: line-draw reveals, list hovers, mask wipes. No bouncing, no parallax for its own sake. |
| Ornament | **1 / 5** | Rules (hairlines), numbers and the grid itself are the only ornament. |
| Contrast | **4 / 5** | Near-black on near-white, and extreme size contrast (12px captions next to 20vw headlines). |

---

## 3. Best-fit purposes

| Purpose | Fit | Reason |
|---|---|---|
| Portfolio (designer, photographer, architect) | ✅ strong | The work is the colour and image. The grid frames it without competing with it (Studio Mann, Victor Pattyn, Dennis Snellenberg). |
| Agency / studio | ✅ strong | Signals rigour and taste. Most "studio" Awwwards winners in this folder are agencies or foundries. |
| Architecture firm | ✅ strong | Architects already think in grids, sections and scales. Drawings and plans read naturally on a modular grid (Norm Architects, Wiemer furniture). |
| Editorial / magazine / type foundry | ✅ strong | It was born in print. Type specimens are its native genre (Pangram Pangram, Editorial New, Grilli Type, Nouvelle Noire). |
| Corporate | ➖ possible | Works for design-literate companies (furniture, engineering, galleries). For banks and insurers it can feel cold; see CC-2. |
| SaaS | ➖ possible | Good for docs, changelogs and pricing tables. Product marketing usually needs more warmth or product-as-hero (CC-3). |
| E-commerce | ➖ possible | Excellent for a small, curated catalogue (Wiemer, Pangram's shop). Weak for big catalogues that need promotion banners. |
| Event / exhibition | ✅ strong | The classic Swiss poster is an event poster. Timetables and lineups suit tabular grids. |
| Nonprofit | ➖ possible | Credible and clear, but may read as distant for causes that rely on empathy (see CW-2). |
| Personal / CV | ✅ strong | Cheap to build well; very hard to make look bad if the grid and type are disciplined. |

---

## 4. Visual DNA

### Typography

| Role | Reference families (paid) | Free alternatives (Google Fonts) |
|---|---|---|
| Neo-grotesk display and text | Neue Haas Grotesk, Helvetica Now, Akzidenz-Grotesk, Suisse Int'l (Swiss Typefaces), GT America / GT Haptik (Grilli Type), ABC Diatype / ABC Favorit (Dinamo), Neue Montreal (Pangram Pangram) | **Archivo** (variable width 62–125, very useful), Schibsted Grotesk, Hanken Grotesk, Inter Tight, Geist |
| Width contrast | GT America Condensed / Extended, Neue Haas Unica | Archivo at `wdth` 62 vs 125; Big Shoulders Text for condensed numbers |
| Metadata / captions | ABC Diatype Mono, GT America Mono, Suisse Int'l Mono | IBM Plex Mono, JetBrains Mono, Geist Mono |
| Editorial serif counterpoint (optional) | Editorial New (Pangram Pangram), GT Sectra, Tiempos | Newsreader, Instrument Serif, Fraunces (with low "softness") |

Rules that make it Swiss rather than just "minimal":
- **Flush-left, ragged-right**, never justified on screen. Headlines set tight: `line-height: 0.88–0.95`, `letter-spacing: -0.03em to -0.05em` above 80px.
- **Extreme scale jump**: one display size (12–22vw), one text size (16–20px), one caption size (11–13px). Avoid the 7-step "type scale" that makes everything medium.
- **Tabular figures** (`font-variant-numeric: tabular-nums`) for indexes, years, areas, prices.
- **Numbering as structure**: `01`, `02`, `(015)` counters, figure numbers, "Fig. 3" captions.
- Uppercase only for tiny labels with +0.04em tracking, never for paragraphs.

### Colour

| Token | Hex | Logic |
|---|---|---|
| Paper | `#F2F1EC` | Off-white reads as printed stock and avoids screen glare. Pure `#FFFFFF` is fine for foundries. |
| Ink | `#111111` | Near-black, softer than `#000` on large areas. |
| Grey 60 | `#5C5C58` | Secondary text; 5.9:1 on paper. |
| Hairline | `#CFCDC6` | 1px rules and grid lines. Decorative only. |
| Signal red | `#E2231A` | Swiss red for a single accent: active state, dot, a key word. Use only at 24px+ or as shape. |
| Signal red (text) | `#B3170F` | Darker red when the accent must be small text (6.1:1 on paper). |

Logic: **one accent, used less than 5% of the surface.** Colour lives in the photography or in the work shown. Alternatives: Klein blue `#1F3FFF`, signal orange `#FF4F00`, Basel green `#00A86B`.

### Layout and grid

- **12-column grid** on desktop (gutter 16–24px, margins 2–4vw), **4 or 6 columns** on mobile. Name your columns and make every element start on one.
- **Asymmetry inside the grid**: text in columns 1–5, image in 7–12, empty column 6. Swiss balance is asymmetric, not centred.
- **Hanging elements**: labels in the outer margin, numbers hanging left of the text column.
- **Horizontal hairlines** divide sections and table rows (Grids by Obys, Studio Mann). Vertical lines are rarer and more architectural.
- **Index pages beat card grids**: a table of projects (No., Name, Place, Year, Type) with hover-to-preview is the signature component of the genre.
- A **baseline** (8px or 4px) for vertical rhythm; section padding in multiples like 96 / 160 / 240px.

### Imagery and art direction

- Photography: frontal, orthogonal, neutral daylight, generous negative space, often desaturated or black and white (Pangram's monochrome Biosphère hero, Norm Architects' material close-ups).
- Crops are **aligned to the grid**, never floating or rounded. Aspect ratios limited to 2–3 (e.g. 4:5, 3:2, 1:1).
- Architectural line drawings, plans and axonometrics as SVG are ideal: they are literally grids.
- Type as image: a giant word or a single glyph filling the viewport (Nouvelle Noire's single "O", Pangram's "Neue Mtl (*Aa→ë) v2.0").

### Motion and interaction

- **Line draw-on** for drawings and rules (`stroke-dashoffset`), 600–1200ms, `cubic-bezier(.2,.7,.1,1)`.
- **Mask reveals**: text lines slide up from a clipped container, staggered 40–60ms.
- **Index hover**: row highlight + an image preview that appears in a fixed column or follows the cursor.
- **Grid overlay toggle** (keyboard `G`), as in Obys' Grids site: shows the system, which is a form of honesty and a jury favourite.
- Live **local time / coordinates** in the header (Koto, many studio sites).
- Smooth scroll (Lenis-style) is common on award sites, but optional; never hijack scroll on a reading page.

### Micro-details

- Thin 1px rules; no shadows; `border-radius: 0` (or a single, consistent 2px).
- Cursor: default, or a small crosshair / dot that turns into "View" over images.
- Registered marks and superscripts as typographic jokes: `Pangram Pangram® Foundry`, `Bag (0)`, `Cart⁰`.
- Strikethrough for the active filter (Studio Mann: ~~Everything~~ / ~~Work~~).
- Footnote-style captions: `Fig. 04 — Haus am Rhein, Basel, 2024, 1:200`.

---

## 5. Why it works

**Cognitive fluency.** Content that is easy to process is judged more beautiful and more true (Reber, Schwarz & Winkielman 2004). Strict alignment, few fonts and predictable rhythm reduce processing effort, so the style "feels right" without the user knowing why.

**Low complexity, high prototypicality wins first impressions.** Users decide on visual appeal in about 50ms (Lindgaard et al. 2006). Tuch et al. (2012) showed that websites low in visual complexity and high in prototypicality were rated most beautiful at first sight. Reinecke et al. (2013) and Reinecke & Gajos (2014) found that perceived complexity strongly predicts appeal, and that the preferred level varies with age, education and culture. Swiss/minimal sits on the "low complexity" side, which is why it is the safest award-quality style.

**Classical aesthetics drive usability perception.** Lavie & Tractinsky (2004) separated *classical* aesthetics (clean, clear, symmetric, pleasant) from *expressive* aesthetics. Classical aesthetics correlate most strongly with perceived usability. Moshagen & Thielsch (2010, VisAWI) list *simplicity* and *craftsmanship* as two of four facets of perceived visual aesthetics; this style is built from exactly those two.

**Layout measures.** Ngo, Teo & Byrne (2003) operationalised interface aesthetics as measurable properties (balance, alignment, grouping, regularity, economy...). A modular grid maximises several of these by construction. Bauerly & Liu (2006) found that symmetry and balance of compositional elements raise aesthetic ratings.

**Readability.** Moderate line lengths (around 55–100 characters) and generous spacing support reading on screen (Dyson & Haselgrove 2001; Dyson 2004). Larger text sizes improve online readability (Rello, Pielot & Marcos 2016). Swiss editorial pages, with a narrow text column inside a wide grid, naturally hit these targets.

**Design canon.** Müller-Brockmann's *Grid Systems in Graphic Design* (1981) argues the grid makes work "objective" and comparable; Hollis (2006, *Swiss Graphic Design*) documents how the style became the international language of corporate and cultural communication. Juries recognise this lineage.

**What award juries reward** (from the Awwwards winners in `references.md`):
- Typography as the hero (Pangram Pangram SOTD, Editorial New SOTD, Grids SOTD).
- A clear system that survives across pages, including mobile (Studio Mann, Dinamo).
- One surprising, well-executed interaction rather than many effects (Grids' grid-reveal, Pangram's live type tester).
- Perfect details: tabular numerals, consistent hairlines, crisp image crops.

> Full references are in `00_Research/academic-findings.md`. Style-specific sources not covered there are listed at the end of `references.md`.

---

## 6. Uniqueness levers

Pick 2–3 and commit to them. Each one alone is enough to escape the template look.

1. **Show the grid.** A toggleable column overlay (key `G`), visible baseline, or column numbers in the header. The system becomes the brand.
2. **Width as a variable.** Use a variable width axis (Archivo `wdth` 62–125, or GT Flexa/ABC Diatype Variable) and change width, not just weight, for hierarchy, or animate width on hover.
3. **An index, not cards.** Replace the 3-up card grid with a numbered project table: tabular figures, hairline rows, hover preview pinned to a fixed column.
4. **Architectural numbering.** Every section gets a drawing number (`A-101`), scale (`1:200`) or coordinate. Turn metadata into the visual layer.
5. **One giant glyph or word cropped by the viewport.** A single letter at 60vw that bleeds off the edge, or the brand name set so large only half fits.
6. **A single signal colour with a job.** Red only marks "now", "active" or "you are here". Never decorative.
7. **Live data in the chrome.** Local time, weather, sunrise for the studio's city, or the current project count, set in mono at 11px.
8. **Line-drawn imagery.** SVG plans, sections, axonometrics or diagrams that draw themselves on scroll instead of stock photography.
9. **Typographic jokes at caption size.** Superscript counts (`Work⁽¹⁵⁾`), strikethrough filters, `®` marks, arrows (`→ ↗`) as UI.
10. **Asymmetric hero.** Headline locked to columns 1–9 and a caption hanging in column 11–12, with a deliberate empty column between.

---

## 7. Clichés and pitfalls

- **Generic Inter + centred hero + 3 feature cards.** That is the default AI/template output, not Swiss style. Swiss is flush-left and asymmetric.
- **Too many sizes.** Seven type sizes and five weights kill the scale contrast. Use three sizes and two weights.
- **Fake grid.** Elements that "look aligned" but start at random pixel offsets. Juries notice. Use CSS Grid with named lines.
- **Helvetica-plus-nothing.** Grotesk type with no idea behind it is just bland. The idea (index, drawing, number system, giant glyph) must carry the page.
- **Grey-on-grey.** Light grey 12px captions on off-white fail WCAG. Keep secondary text at `#5C5C58` or darker.
- **Over-animated minimalism.** Smooth scroll + parallax + magnetic buttons + custom cursor on a minimal page reads as a template from a marketplace.
- **Rounded corners and drop shadows.** They belong to SaaS UI (CC-3), not Swiss.
- **Accent overuse.** Red on every link and button stops being a signal.

---

## 8. Accessibility and performance notes

- Contrast: `#111` on `#F2F1EC` ≈ 16.7:1; `#5C5C58` on paper ≈ 5.9:1; red `#E2231A` on paper ≈ 4.1:1, so use it only for large text (≥24px) or non-text marks, and `#B3170F` for small red text.
- Giant headlines: use `clamp()` so they never cause horizontal scroll at 320–375px; set `overflow-wrap: anywhere` on long words in German or Dutch names.
- Hover previews must have a non-hover equivalent: on touch devices, show a thumbnail inline in the row.
- Grid overlay is decorative: `aria-hidden="true"`, toggled by a real `<button>` with `aria-pressed`.
- Variable fonts: one variable file replaces 6–10 static weights. Subset to Latin; `font-display: swap`.
- Honour `prefers-reduced-motion`: skip draw-on and mask reveals, show final state.
- Tables of projects should be real `<table>` or `<ol>` elements so screen readers can navigate them.

---

## 9. Neighbouring styles and hybrids

| Blend with | Result |
|---|---|
| **CC-2 Corporate Trust** | Swiss grid + softer blue palette + reassurance content = credible enterprise or consulting site. |
| **CC-3 Tech Product** | Swiss docs-style layout, mono metadata, dark mode = developer tools (Linear and Vercel borrow heavily from this). |
| **CW-1 Luxury Refined** | Swap grotesk for a high-contrast serif, add slow fades = fashion house or hotel. Pangram's *Editorial New* sits here. |
| **EC-1 Immersive** | Keep the grid and type, add one WebGL hero (Dinamo's 3D brains, Koto's chrome gradients) = award-friendly studio site. |
| **EC-2 Brutalist Raw** | Remove polish, use system fonts, show borders, break the grid on purpose = "Swiss-brutalism" (Stedelijk Museum, Experimental Jetset archive). The two styles share the grid; they differ in finish. |
| **EW-2 Retro** | Swiss 1960s poster palettes (orange, olive, cream) + halftone = mid-century nostalgia. |
