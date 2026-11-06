# EW-2 · Retro-Nostalgic

## 1. One-line definition
A deliberate revival of a specific past visual era (70s soft-serif warmth, 80s neon and chrome, 90s old-OS and early-web, Y2K chrome and glitch, 8-bit pixel, risograph print) rebuilt with modern craft, so the site feels like a beloved artefact from a time the visitor half-remembers.

> **The golden rule:** pick ONE sub-era and commit. "Retro" in general is a mood board; "1974 Californian FM-radio print ad" is a design system.

---

## 2. Position on the map

| Axis | Score | Why |
|---|---|---|
| Classical ↔ Expressive | **4 / 5** (expressive) | Pastiche, period jokes and texture are expressive. But many eras (Swiss-influenced 70s, OS UIs) carry strong internal order, which keeps it usable. |
| Cool ↔ Warm | **4 / 5** (warm) | Nostalgia is an emotional, social feeling (Wildschut et al. 2006). 70s and print variants are very warm; 80s neon and Y2K chrome lean cooler (score them 3). |
| Density | **3–4 / 5** | OS pastiche and early-web pages are dense, with many windows and badges. 70s print layouts can be airy. |
| Motion | **3 / 5** | Era-true motion is limited: blinking, marquee, VHS wobble, stepped animation. Modern smoothness should be used sparingly. |
| Ornament | **5 / 5** | Grain, scanlines, halftones, bevels, stripes, starbursts. Texture is how era gets signalled. |
| Contrast | **3 / 5** | Varies: 70s is low-contrast and tonal, 80s neon on black is very high, pixel art is crisp. |

---

## 3. Best-fit purposes

| Purpose | Fit | Reason |
|---|---|---|
| Portfolio | ✅ | Creative devs and designers (EddyOS, Rubens Cantuni). A memorable concept beats a template. |
| Agency | ➖ | Good for studios with a cultural or music focus. It can signal "only does retro". |
| Corporate | ❌ | Except heritage anniversaries or a careers microsite. Pastiche undermines a forward-looking trust message. |
| SaaS | ➖ | Works for creative tools, music tech and indie apps (an OS metaphor for a desktop app). Avoid for enterprise. |
| E-commerce | ✅ | Streetwear, vinyl, vintage, cassette, craft beer, sneakers. Nostalgia boosts purchase intention (Muehling & Sprott 2004). |
| Editorial | ✅ | Music journalism and culture zines. Print-era grids and riso textures fit naturally. |
| Nonprofit | ➖ | Good for archives, museums and local history. Avoid for urgent causes. |
| Event | ✅ | Festivals, club nights, film releases, game launches. |
| Personal | ✅ | One of the best styles for a personality-rich personal site. |
| Indie games / music / radio | ✅ | The core audience. These genres trade on memory. |

---

## 4. Visual DNA

### Sub-era quick reference

| Sub-era | Type (free Google Fonts in **bold**) | Palette logic | Texture / motion signature |
|---|---|---|---|
| **70s warm / soft-serif** | Cooper Black, ITC Souvenir, Windsor, Helvetica Rounded (Luaka Bop) → **Fraunces** (SOFT 100, WONK 1, opsz 144), **Shrikhand**, **Bagel Fat One**, **Recoleta-like Young Serif** | Harvest gold `#E8A33D`, burnt orange `#D2601A`, rust `#A63A1E`, avocado `#7A7A2E`, chocolate `#3B2416`, cream `#F3E6CC` | Curved racing stripes, sunbursts, paper grain, slight misregistration, slow ease-in-out |
| **80s neon / chrome** | Chrome script, Eurostile → **Monoton**, **Michroma**, **Audiowide**, **Kaushan Script** | Black `#0B0221`, hot magenta `#FF2E97`, cyan `#00F0FF`, sunset gradient `#FFB86C → #FF2E97 → #7B2CBF` | Perspective grid floor, chrome gradients, glow, scanlines, laser stripes (VINYLCUTS) |
| **90s old-OS / early web** | Chicago, Geneva, MS Sans Serif → bitmap-style **Silkscreen**, **VT323**, **Pixelify Sans**, **Press Start 2P** | System grey `#C0C0C0`, title-bar navy `#000080`, teal desktop `#008080` (or invent your own like Poolsuite) | Bevelled 2 px borders (`outset`), windows, cursors, marquee, blink, under-construction GIF energy |
| **Y2K chrome / Frutiger Aero** | Eurostile Extended, Microgramma → **Michroma**, **Syncopate**, **Orbitron** (careful) | Iridescent silver, ice blue `#BFE6FF`, lilac `#C8B6FF`, lime `#C6FF3D` | Liquid chrome, bubbles, lens flares, glossy pill buttons, blur glass |
| **Pixel / 8-bit** | **Press Start 2P**, **Silkscreen**, **DotGothic16**, **Jacquard 12**, **Pixelify Sans** | Limited 4–16 colour palettes (PICO-8, NES, Game Boy `#0F380F #306230 #8BAC0F #9BBC0F`) | `image-rendering:pixelated`, `steps()` animation, dithering |
| **Risograph / print** | **Space Grotesk**, **Archivo Black**, **Instrument Serif**, condensed grotesks | Riso ink names: Fluorescent Pink `#FF48B0`, Federal Blue `#3D5588`, Yellow `#FFE800`, Teal `#00838A` | Halftones, `mix-blend-mode:multiply` overprint, 2–6 px misregistration, paper grain |

### Typography
- Use a **period display face** plus a **neutral, modern body face** (or a monospace for "technical" eras). Period-accurate body text (pixel fonts in paragraphs) kills readability.
- 70s: **Fraunces 900 italic at SOFT 100 / WONK 1** gives you Cooper-and-Windsor bounce in one free variable font. Set it at `clamp(4rem, 13vw, 13rem)` with line-height 0.82 and letter-spacing -0.03em.
- Catalogue numbers, timestamps and prices in monospace (**DM Mono**, **IBM Plex Mono**, **Space Mono**). It is the "label on a record sleeve" voice.

### Colour
- Desaturate and warm up modern brights for 70s (sun-faded print); push saturation to the maximum on black for 80s; use system greys and one saturated accent for OS.
- **Never use pure white.** Use paper cream, phosphor amber or CRT off-white.

### Layout and grid
- **70s:** centred poster compositions, curved stripes framing the content, rounded-rectangle "TV screen" frames, and ticket-stub and record-sleeve card shapes (square 1:1 cards).
- **OS:** draggable windows on a desktop, a menu bar, a taskbar and icon grids.
- **Early web:** a single centred table-like column, `<hr>` dividers, a guestbook, a visitor counter (a joke, not a tracker).
- **Print:** a strict modular grid with intentional overprint and misregistration.

### Imagery and art direction
- Treat photos to match the era: duotone, halftone dots, scanned-paper grain, faded colour (a lifted black point and warm highlights), VHS chroma bleed.
- Original illustration in period technique: airbrush gradients (80s), linocut or hand-inked patterns (70s, Luaka Bop), pixel sprites.

### Motion and interaction
- Prefer **era-true motion**: `steps()` animation, blinking cursors, CRT power-on and off, marquee tickers, a vinyl spin at 33⅓ rpm (1.8 s per turn), tape-reel rotation, a VHS tracking wobble on hover.
- **Signature toys:** a turntable you can scrub, a radio dial that tunes sections, draggable OS windows, an era slider (Rubens Cantuni), a boot sequence (Poolsuite).
- **Sound** is a strong nostalgia cue (Holbrook & Schindler 1989 on music preference formed in early adulthood). Always make it opt-in.

### Micro-details
- Custom cursors (the OS pointer, a pixel hand), `::selection` in an era colour.
- An SVG `feTurbulence` grain overlay at 6–12 % opacity, scanlines from `repeating-linear-gradient`, halftone dots from `radial-gradient`.
- Period microcopy: "Side A / Side B", "Now spinning", "Best viewed in 800×600", "Tracking…".

---

## 5. Why it works

### Nostalgia is a positive, social emotion
- Wildschut, Sedikides, Arndt & Routledge (2006, "Nostalgia: Content, triggers, functions", *JPSP*) show that nostalgia raises positive affect, self-regard and social connectedness.
- Svetlana Boym (2001, *The Future of Nostalgia*) distinguishes **restorative** nostalgia (rebuilding the past literally) from **reflective** nostalgia (playing with the longing). Award-winning retro sites are reflective: they wink (Poolsuite's martini close buttons).

### Nostalgia sells
- Muehling & Sprott (2004, "The power of reflection: An empirical examination of nostalgia advertising effects", *Journal of Advertising* 33(3)) found that nostalgic ads produce more favourable brand attitudes and purchase intentions.
- Loveland, Smeesters & Mandel (2010, "Still preoccupied with 1995: The need to belong and preference for nostalgic products", *Journal of Consumer Research*) found that the **need to belong** raises preference for nostalgic products.

### Taste is formed young
Holbrook & Schindler (1989, "Some exploratory findings on the development of musical tastes", *JCR*; 1991 "Echoes of the dear departed past") found that preferences peak for things people met in late adolescence and early adulthood (a peak around age 23–24). **Pick the era your audience was ~15–25 in:**
- Gen Z → Y2K and 2000s web
- Millennials → 90s OS and 8-bit
- Gen X → 80s

### Familiar yet new
- Processing fluency (Reber, Schwarz & Winkielman 2004, see `00_Research/`) predicts liking for the familiar.
- Hekkert (2006, "Design aesthetics: principles of pleasure in design") formalises Loewy's **MAYA** ("Most Advanced Yet Acceptable") principle: the sweet spot is typicality plus novelty.
- Retro gives the typicality and modern craft gives the novelty, which is why pure replicas underperform reinventions.

### The cultural view
Simon Reynolds (2011, *Retromania: Pop Culture's Addiction to Its Own Past*) documents how music and fashion recycle eras on a ~20–30-year loop. That loop is why this style keeps cycling back for music, streetwear and indie games.

### What juries reward
Every verified winner above re-invents rather than replicates:
- an invented OS (Poolside FM)
- era-switching as a mechanic (Rubens Cantuni)
- cinematic retro-futurism instead of kitsch (Retronova)
- a game as navigation (basement chronicles)

---

## 6. Uniqueness levers
1. **Hyper-specific era and place:** "1976 Gulf Coast AM radio" rather than "70s". Name it in a design note.
2. **Invent period UI that never existed:** a new OS, a fictional hi-fi brand, a mail-order catalogue for your product.
3. **Nostalgia as a control:** a radio dial, era slider, tape deck or channel knob that changes theme, content or audio.
4. **A physical artefact as the layout:** record sleeve, cassette J-card, ticket stub, VHS box, Polaroid, matchbook, Teletext page.
5. **An anachronism clash:** pair one modern element (crisp variable type, WebGL smoothness) with the period, the way basement layers neon script on chrome.
6. **Period microcopy and a fake "manual"** (liner notes, a care-instructions tag, a "Be kind, rewind" footer).
7. **Real print physics:** CSS overprint (`multiply`), 2–4 px misregistration and halftone in place of flat fills.
8. **Era-true motion only:** `steps()`, 33⅓-rpm spins, blink. No glossy modern easing.
9. **Opt-in sound** (a needle drop, a boot chime, a dial-up handshake) with a hardware-style toggle.
10. **Easter-egg depth:** a guestbook, hidden track, Konami code or "Side B" page.

---

## 7. Clichés and pitfalls
- **Generic synthwave:** a magenta sun with a grid floor and a palm tree, the most overused retro trope since about 2015. Avoid unless subverted.
- Fake Windows 95 dialogs with no idea behind them, and OS pastiche without new metaphors.
- Mixing eras by accident (70s fonts plus 80s neon plus Y2K chrome in one page). Do it only as a deliberate clash.
- Pixel fonts for paragraphs; VT323 body text at 14 px.
- Over-texturing: grain plus scanlines plus halftone plus VHS, all at full strength. Pick one primary and one secondary texture.
- Brown mud: a 70s palette with no light value, so everything is mid-tone. Keep a cream and a near-black for contrast.
- Directly copying a real album cover, game sprite or brand's period logo (it is an IP risk and lazy).
- "Retro" stock photos with an Instagram filter.

---

## 8. Accessibility and performance notes
- **Contrast:** 70s mid-tones fail easily. Test text against harvest-gold and orange; use chocolate `#3B2416` on cream `#F3E6CC` (≈11.7:1) for body. Neon on black is fine for large text, but thin neon (#FF2E97 at 14 px) can still fail.
- **Flashing:** CRT flicker, glitch and strobe must stay under 3 flashes per second (WCAG 2.3.1), and should be disabled under `prefers-reduced-motion`.
- **Pixel fonts:** keep them ≥ 16 px rendered and at integer multiples of their design size, with `-webkit-font-smoothing: none` only for display.
- **OS pastiche:** draggable windows still need real buttons, focus order and keyboard-accessible close and open. Do not hide navigation behind "double-click the icon" without a fallback list.
- **Grain overlays:** use one fixed, `pointer-events:none` SVG or a tiny tiled PNG. Avoid huge animated noise canvases (CPU cost). Animate grain with `steps()` at ≤ 8 fps if at all.
- **Audio** is opt-in and never autoplays, and the Web Audio context is created on a user gesture.

---

## 9. Neighbouring styles and hybrids
- **+ EW-1 Playful-Illustrative:** pixel mascots, rubber-hose 1930s cartoons, 70s cartoon stickers (Chocapic Nutri-Game).
- **+ EC-2 Brutalist-Raw:** the early web is raw HTML. Default blue links, Times and tables are the brutalist/90s overlap.
- **+ EC-1 Immersive-Experimental:** WebGL CRT shaders, 3D chrome type, retro-futurist worlds (Retronova).
- **+ CW-2 Warm-Organic:** 70s earth tones, macramé and sun-faded photography. A "slow living" retro.
- **+ CC-1 Swiss-Editorial:** 60s and 70s International Style is itself retro. Use a Swiss grid with a riso texture for museum or archive sites.
- **Avoid with CC-2 Corporate-Trust** unless it is a heritage or anniversary microsite.
