# CW-1 · Luxury-Refined

## 1. One-line definition
A web aesthetic of **restraint as a signal of value**: light high-contrast serifs at very large sizes, a near-monochrome warm palette, full-bleed photography or film, enormous negative space and slow, cinematic motion, used by fashion houses, jewellers, watchmakers, boutique hotels, fine dining, perfume and prime real estate.

## 2. Position on the map

| Axis | Score | Justification |
|---|---|---|
| Classical ↔ Expressive | **2 / 5** (Classical) | Symmetry, centred logos, strict grids and order. Hero moments (Cartier, Louis Vuitton microsites) can go Expressive with WebGL, but the frame stays classical. |
| Cool ↔ Warm | **3.5 / 5** (leans Warm) | Warm whites, brass, skin and wood in photography and human craft stories. Couture variants go cooler (pure black/white). |
| Density | **1 / 5** (airy) | Section gaps of 10–15 vh, one idea per viewport, body copy rarely more than 60 words per block. |
| Motion | **3 / 5** | Constant but slow: 1.2–2.4 s curtain reveals, images settling from 112% to 100%, smooth scroll. Never bouncy or fast. |
| Ornament | **2 / 5** | Hairline rules, monograms, italic flourishes and old-style numerals. No illustration, icons or badges. |
| Contrast | **3 / 5** | Type contrast is high (huge light serif vs tiny tracked caps), but colour contrast is soft (paper vs ink, no saturated accents). |

## 3. Best-fit purposes

| Purpose | Fit | Why |
|---|---|---|
| Portfolio | ➖ | Good for photographers, architects and interior designers; too slow for developers. |
| Agency | ➖ | Works for agencies that sell to luxury clients (Matter Of Form, Immersive Garden), otherwise reads as precious. |
| Corporate | ❌ | Low information density hurts scanning; the slowness reads as evasive in B2B. |
| SaaS | ❌ | Product UI, pricing tables and docs fight the restraint. |
| E-commerce | ✅ | Fashion, jewellery, watches, fragrance. Product photography carries all the colour (John Hardy, Coutumes). |
| Editorial | ✅ | Brand magazines and yearbooks (Cartier 365 by 14islands), long-form craft stories. |
| Nonprofit | ❌ | Feels exclusive, the opposite of inclusive fundraising, except for arts foundations and galas. |
| Event | ➖ | Galas, haute-joaillerie launches, fashion shows, private viewings. |
| Personal | ➖ | Couture designers, chefs, high-end stylists. |
| **Hospitality** | ✅ | Boutique hotels, safari lodges, private islands (Tengile MalaMala, Velaa, White Desert, Tandjung Sari). |
| **Real estate** | ✅ | Prime residential and branded residences (Lenval Properties, Mejuma Tuscany, Mr. C Residences). |

## 4. Visual DNA

### Typography
- **Display**: a light or regular high-contrast serif, set **huge** (8–15 vw) and tight (−0.02 to −0.04 em). It is often ALL CAPS with an **italic lowercase article** in front ("*Le* CHŒUR *des* PIERRES" on Cartier, "*Villas,* built for intimacy" on Velaa).
  - Commercial: Canela, GT Super, Ogg, Saol Display, Romie, Editorial New, Noe Display, Domaine, Freight Big, Self Modern, Reckless.
  - **Free (Google Fonts)**: Cormorant Garamond (300 is the workhorse), Bodoni Moda (Didone/fashion), Playfair Display (use sparingly, it is over-used), Gilda Display, Italiana, Bodoni Moda italic, Fraunces at `opsz 144, wght 300, SOFT 0`, Instrument Serif, Newsreader Display.
- **UI and text**: a geometric or neo-grotesk sans at 11–13 px, **tracked uppercase 0.18–0.3 em**, for navigation, captions and CTAs ("ENQUIRE", "MENU", "SOUND"). Free: Jost (Futura-like), Manrope, Inter Tight, Hanken Grotesk, Montserrat (light only).
- **Body**: serif or sans at 16–18 px, line-height 1.6–1.7, max 34–40 em measure. Old-style figures (`font-variant-numeric: oldstyle-nums`) for dates and room numbers.
- **Pairing rule**: 1 serif plus 1 sans, three sizes in active use per screen (mega, body, caption). The size gap is the drama.

### Colour
Neutrals carry about 90% of the surface; colour comes from photography.

| Token | Hex | Role |
|---|---|---|
| Salt paper | `#F4F1EC` | Page ground, never pure `#FFF` (except in the Couture variant) |
| Mat | `#EAE5DD` | Image mats, recessed panels |
| Ink | `#1C1A17` | Text, 15.4:1 on paper |
| Muted | `#6E665D` | Captions, 5.0:1 (AA) |
| Brass | `#A88653` | Hairlines, numerals, focus. Decorative or large text only |
| Night | `#15171B` | Footer, film sections |

Logic: **warm greige plus one metal**. Brand colours appear as a single field (Hermès orange, Tiffany blue, Cartier red) and never as gradients or multiple accents. Tandjung Sari shows the exception done right: a single Balinese red used as a full-bleed panel inside cream and taupe.

### Layout and grid
- 12-column grid with **asymmetric occupancy**: text sits in 4–5 columns, images bleed off-edge, and large areas are deliberately empty.
- **Centred wordmark header** with 2–3 tiny tracked links each side (Tengile: "ENQUIRE / logo / MENU"; White Desert: boxed nav buttons on a visible column grid).
- One idea per viewport. Full-bleed hero with the headline **staggered across lines** (Tengile's "ESCAPE INTO / THE THRIVING / WILD" steps right each line).
- Editorial splits: image 7 columns, text 4 columns, 1 empty column as breathing room. Mats around photos (Tandjung Sari puts photos on cream cards on a dark ground, like an album).
- Index lists: rooms, collections or residences as big serif rows with hover-revealed imagery.

### Imagery and art direction
- Full-bleed, **slow** film or high-dynamic-range photography with golden-hour warmth, deep shadows, and texture (wood, linen, stone, skin).
- Product as **object in a void**: gems on white silk (Cartier Le Chœur des Pierres), a single ring floating over the grid (John Hardy).
- People are photographed as atmosphere (backs, hands, silhouettes, profiles), never as stock-smiling customers.
- Archive and heritage: black-and-white archival photos beside colour (Tandjung Sari's 1960s Bali material).
- Unifying grade: slightly lifted blacks, warm highlights, 5–8% grain.

### Motion and interaction
- **Curtain reveals**: images unmask with `clip-path: inset()` over 1.2–1.6 s on `cubic-bezier(.76,0,.24,1)` while scaling from 1.12 to 1.
- **Line-by-line text rise**: each line in a mask, translating from 100% to 0 with a 60–120 ms stagger.
- **Smooth, weighted scroll** (Lenis or Locomotive) and subtle image parallax (5–10%, no more).
- **Sound toggle** in the corner (Cartier's "SOUND"): ambient audio, off by default.
- Hover: underline drawn from the left (scaleX), or an image fading in behind a list row. No scale-ups or colour pops.
- Page transitions as fades through the paper colour or a wipe in the brand colour.
- Preloaders are allowed only if they are brand theatre (a monogram drawing itself), and they must stay under 2 s.

### Micro-details
- 1 px hairlines at 12–16% ink opacity; numbered sections (I, II, III or 01 / 04).
- Tracked-caps micro-labels such as "EST. 1847", "N°12", "48°51′N".
- Custom cursor: a small ring or the word "VIEW" / "DRAG" on galleries. Keep the native cursor everywhere else.
- Booking or enquiry is an always-visible but quiet pill or text link, never a loud button.
- Ligatures and true italics on; `text-wrap: balance` on headlines; `hanging-punctuation`.
- Grain overlay (SVG `feTurbulence`) at 4–8% to remove digital flatness.

## 5. Why it works

**Restraint as a costly signal.** Luxury marketing theory says luxury must *not* behave like mass marketing. Kapferer & Bastien (2009, *The Luxury Strategy*) list "anti-laws": don't pander to demand, make access a little difficult, never justify the price. On the web this becomes few CTAs, slow pacing and withheld information (prices "on request"). Dion & Arnould (2011, *Journal of Retailing*) show luxury retail builds "charisma" through art-world and magical staging, which is the museum-like void and theatre of these sites.

**White space means prestige, and that meaning is learned.** Pracejus, Olsen & O'Guinn (2006, *How nothing became something: White space, rhetoric, history, and meaning*, JCR 33(1)) found that consumers and creative directors read white space as signalling prestige, quality, trust and leadership. They trace that meaning to the history of minimalist art and corporate modernism, not to anything inherent in empty space. Olsen, Pracejus & O'Guinn (2012, *Print advertising: White space*, J. Business Research 65(6)) extend this. Sevilla & Townsend (2016, *The space-to-product ratio effect*, JMR 53(5)) show more empty space around a product raises its perceived aesthetic appeal and store prestige.

**Serifs read as elegant and luxurious.** Brumberger (2003, *The rhetoric of typography: The persona of typeface and text*, Technical Communication 50(2)) showed readers consistently attribute personas such as "elegant" and "direct" to typefaces. Henderson, Giese & Cote (2004, *Impression management using typeface design*, J. Marketing 68(4)) map typeface features to perceived elegance and naturalness, with contrast, serifs and slight condensing driving "elegant". A 2024 International Marketing Trends Conference paper, *The Effect of using Serifs in Brand Names on Luxury Perception*, found serif versions of real and fictitious brand names scored higher on luxury, especially on opulence and elitism (Heine's luxury brand personality dimensions). A study of Chinese consumers and luxury fashion logotypes (UUM repository) found more nuanced effects, so treat the serif-luxury link as strong but culturally mediated.

**Fluency with a twist.** Processing-fluency theory (Reber, Schwarz & Winkielman, 2004) predicts liking for clear, low-noise layouts, which favours the Classical end of Lavie & Tractinsky's (2004) scale. Luxury adds just enough disfluency (huge italics, unusual layouts, slow reveals) to signal craft without hurting legibility. See `00_Research/academic-findings.md` for the general aesthetics literature.

**Low-saturation colour.** Labrecque & Milne (2012, *Exciting red and competent blue*, JAMS 40(5)) link colour to brand personality, with black linked to sophistication. Valdez & Mehrabian (1994) show saturation drives arousal. Luxury keeps saturation low (calm, high-status) and lets one brand hue mean something.

**What juries reward.** Awwwards SOTDs in this space (Cartier In Time 2023, Louis Vuitton Collectibles 2024, Tengile MalaMala 2026, White Desert 2026, Cartier Le Chœur des Pierres 2026) score on **design and content**. Juries reward cinematic, art-directed media, perfect typographic hierarchy, smooth 60 fps transitions and storytelling, which in luxury usually means craft, heritage or place. Generic hotel templates with booking widgets are filtered out.

## 6. Uniqueness levers
1. **Place- or material-derived system**: derive the palette and one motif from the real material (salt crystals, a watch's guilloché, a hotel's tiles). Tandjung Sari uses a Balinese red and an offering-flower mark.
2. **Time as interface**: the page changes with time of day, season or the scroll ("dawn → night"), which suits hotels and watches.
3. **One oversized word**: a single mega-word per page (White Desert's "ANTARCTICA" at about 17 vw in a condensed sans), with everything else tiny.
4. **Mixed-register headlines**: roman caps plus italic lowercase connectives ("*Le* CHŒUR *des* PIERRES"), or steps across the grid like Tengile.
5. **Archive layer**: mix in black-and-white heritage material, letters, sketches and ledgers, the "maison" story told with documents.
6. **Index instead of cards**: show rooms, collections or residences as a typographic list with a hover image, never a 3-up card grid.
7. **Sensory channel**: an opt-in ambient sound toggle (Cartier), a scent-note vocabulary, or a tactile hover (cloth ripple in WebGL).
8. **Correspondence-style booking**: enquiry framed as a letter ("Write to the concierge"), not a date-picker widget on load.
9. **Visible grid as ornament**: hairline column lines across full-bleed media (White Desert).
10. **Mats and frames**: photos printed on paper cards on a dark ground, like a lookbook or album (Tandjung Sari).

## 7. Clichés and pitfalls
- Playfair Display plus Montserrat, gold `#D4AF37` gradients, black backgrounds with "LUXURY" in letter-spaced caps: this reads as a Dubai template, not a maison.
- Stock photos of champagne, couples in robes or generic infinity pools.
- Booking widgets, cookie bars and chat bubbles stacked on the hero, destroying the void.
- Slow motion **everywhere**: a 3-second preloader, then 2-second reveals on every paragraph. Users bounce. Use slowness for 2–3 moments only.
- Script fonts for the logo or headings (wedding-invitation energy).
- Over-thin type (Cormorant 300 at 14 px is illegible); light weights belong to display sizes only.
- Too many accents (gold plus navy plus burgundy). One metal, one brand hue maximum.
- Scroll-jacking that breaks the back button or traps keyboard users.
- AI tell-tales: centred hero with "Experience Timeless Elegance", three feature cards with icons, "Discover More" buttons with arrows, gradient overlays on everything.

## 8. Accessibility and performance
- Light serifs must be **≥ 32 px** (prefer ≥ 48 px) if weight is 300; body text weight ≥ 400 at ≥ 16 px.
- Muted greys on cream fail quickly: keep captions at least `#6E665D` on `#F4F1EC` (5.0:1). Brass `#A88653` is decorative only (3.0:1); use `#7A5E33` for brass text.
- Text over photography: add a 20–40% scrim or place text on calm image areas, and check contrast at every breakpoint.
- `prefers-reduced-motion`: disable smooth-scroll libraries, curtain reveals and parallax, and show content immediately.
- Video heroes: `muted playsinline`, poster frame, an explicit pause control (WCAG 2.2.2), a < 6 MB first chunk and AV1/H.265 fallbacks.
- Images: AVIF/WebP, `srcset`, `fetchpriority="high"` on the hero only, lazy-load the rest; LCP < 2.5 s even with full-bleed media.
- Fonts: subset display fonts, `font-display: swap`, and preload only the hero weight.
- Smooth scroll must keep native keyboard scrolling, focus order and anchor links working.

## 9. Neighbouring styles and hybrids
- **CC-1 Swiss-Editorial-Minimal**: shares grids and whitespace. Luxury swaps the grotesk for a serif and adds photography and warmth. Hybrid: architecture studios and galleries (sans display, luxury pacing).
- **CW-2 Warm-Organic**: shares warmth and texture. Hybrid "quiet luxury / wabi-sabi" for Aesop-type skincare, Japanese ryokans and farm-to-table fine dining, with more grain and softer shapes but kept restrained.
- **EC-1 Immersive-Experimental**: luxury maisons commission WebGL microsites (Cartier In Time, Louis Vuitton Collectibles by Immersive Garden). Hybrid: a classical frame with one immersive 3D centrepiece.
- **EW-2 Retro-Nostalgic**: heritage houses use archival print styling (Tandjung Sari's 1960s photos). Hybrid: "heritage maison" with archive scans and period type.
- **EC-2 Brutalist-Raw**: avant-garde fashion (Balenciaga-style) uses brutalist anti-luxury as a status code. This is luxury's ironic opposite, for brands secure enough to break the rules.
