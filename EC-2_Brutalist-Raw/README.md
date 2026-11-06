# EC-2 · Brutalist / Raw / Anti-design

## 1. One-line definition

A style that shows the web's raw material on purpose: default or system fonts, visible borders and tables, blue underlined links, oversized or clashing type, harsh colour and broken conventions, used to look honest, urgent and unmistakably non-corporate.

The name borrows from architectural Brutalism (*béton brut*, "raw concrete"; Banham 1966). On the web it took off after Pascal Deville founded **brutalistwebsites.com** in 2014, a curated list he describes as "a reaction by a younger generation to the lightness, optimism, and frivolity of today's web design" (quoted from the site's header). It has two branches:

| Branch | What it means | Examples |
|---|---|---|
| **Raw / functional brutalism** | Truth to materials: HTML as HTML, fast, content-first, few styles. | Low←Tech Magazine's solar site, brutalist-web.design (David Bryant Copeland's guidelines), Experimental Jetset's archive, Gerrit Rietveld Academie |
| **Expressive / anti-design brutalism** | Deliberate ugliness, clash and confrontation as brand language. | HAN Kjøbenhavn (pop-up windows over a spreadsheet grid), Aphex Twin store on Warp (pixel font, black bars), MSCHF, Stedelijk Museum (huge type rows) |

Award-winning versions usually combine both: raw materials plus one very controlled, surprising idea.

---

## 2. Position on the map

| Axis | Score | Why |
|---|---|---|
| Classical ↔ Expressive | **4.5 / 5** | Breaks norms of beauty and convention by design; originality over polish. It can still use a strict grid underneath. |
| Cool ↔ Warm | **2 / 5** (cool-leaning) | Machine aesthetics (default fonts, tables, monospace) feel cold and ironic. Humour and handmade chaos can warm it up. |
| Density | **4 / 5** | Lots of text, lists, tables and links visible at once; little whitespace management. |
| Motion | **2 / 5** | Mostly static; motion is abrupt (blink, marquee, instant jumps, cursor trails), never eased and smooth. |
| Ornament | **2 / 5** | No decorative polish, but "anti-ornament" (stickers, ASCII, stamps, clip-art) can pile up in the expressive branch. |
| Contrast | **5 / 5** | Pure black on white or acid colours, 2–4px borders, giant type next to 11px mono. |

---

## 3. Best-fit purposes

| Purpose | Fit | Reason |
|---|---|---|
| Portfolio (designer, artist, developer) | ✅ strong | Signals independence and taste for those who "get it" (Candy Chiu, Keith Alva "Fake Designer" HM 2017). |
| Agency / studio | ➖ possible | Works for small, culture-facing studios (Foreign Policy Design, Heller). Risky for agencies selling to corporates. |
| Corporate | ❌ avoid | Reads as unserious or hostile to buyers who need reassurance (see CC-2). |
| SaaS | ➖ possible | "Neo-brutalism" (flat colours, hard black shadows, thick outlines) works for dev tools and indie products; full raw brutalism hurts conversion. |
| E-commerce | ➖ possible | Streetwear, records, zines and fashion drops (HAN Kjøbenhavn HM 2019, MSCHF drops). Avoid for mass retail. |
| Editorial / magazine / archive | ✅ strong | Content-first, fast, text-heavy; Low←Tech Magazine, Bloomberg features, institutional archives. |
| Nonprofit | ➖ possible | Activism, art collectives, open-source projects. Not for charities needing empathy and trust. |
| Event / festival / club | ✅ strong | Line-ups, timetables and urgency suit raw lists and loud type (Art Night London HM 2019, DesignThinkers 2020 HM). |
| Culture: art space, museum, music label | ✅ strong | Its native home: Stedelijk, MCA Chicago, Rietveld Academie, Warp Records' Aphex Twin store. |
| Personal / blog | ✅ strong | Cheap, fast and personal. |

---

## 4. Visual DNA

### Typography

| Role | Typical choices | Free / system |
|---|---|---|
| Body | The browser default: **Times New Roman**, or Arial/Helvetica | `font-family: "Times New Roman", Times, serif` — zero download |
| Monospace UI and data | Courier, Courier New, Monaco | `ui-monospace, "Courier New", monospace`; Google: Space Mono, IBM Plex Mono, Courier Prime |
| Display | System fonts set huge, stretched with `transform: scaleY()`, or one ugly-beautiful display face: pixel fonts (Aphex Twin store), grotesk at 20vw (Stedelijk), wide extended monospace (MAGWAI's "SPOMENIK") | Google: Anton, Archivo Black, Rubik Mono One, Bowlby One, VT323 / Silkscreen (pixel), Darker Grotesque |
| Clash partner | A second family that "shouldn't" be there: italic serif against mono, script against grotesk (Foreign Policy: italic Caslon-like logo + grotesk nav) | Instrument Serif italic, Playfair italic, Pinyon Script |

Rules:
- **Scale shock**: 15–40vw headlines that overflow or get cut off by the viewport, next to 11–13px mono.
- **Distortion as a tool**: `transform: scaleY(1.4–2.5)`, negative letter-spacing until letters touch, `writing-mode: vertical-rl` labels (Roze Bunker's vertical `M E N U`).
- **Default link styling**: blue `#0000EE`, visited purple `#551A8B`, underlined.
- **ALL CAPS** for headlines and buttons; lowercase for everything else is also common. Pick one and be extreme.

### Colour

| Token | Hex | Logic |
|---|---|---|
| White | `#FFFFFF` | The unstyled page. |
| Black | `#000000` | Pure, never `#111`. |
| Link blue | `#0000EE` | Browser default link (9.4:1 on white). |
| Visited purple | `#551A8B` | Browser default visited (11:1). |
| Highlighter yellow | `#FFFF00` | `<mark>`, ticker bars, stickers; black on it is 19.6:1. |
| Alarm red | `#E00000` | Text-safe red (5.0:1 on white). Pure `#FF0000` is only 4.0:1, so use it for shapes or ≥24px. |
| Acid options | `#00FF41` (terminal green), `#FF5FD2` (fluoro pink), `#3A3AFF` (Klein-ish blue) | One acid colour per site, used in big flat fields. |

Logic: **either almost no colour (black/white/default blue) or one acid field used at full intensity.** No gradients, no tints, no soft shadows. Art Night's pink-to-blue gradient is the exception that shows how "festival brutalism" borrows from retro (EW-2).

### Layout and grid

- **Visible structure**: `border: 2px solid #000` on boxes, `<table border="1">` aesthetics, cells that touch, `<hr>` as section break.
- **Single-column document flow** (raw branch) or **collage of overlapping windows** (expressive branch: HAN Kjøbenhavn's pop-up dialogs over a spreadsheet grid, Heller's stacked image cards behind a running headline).
- Spreadsheet or graph-paper backgrounds (HAN Kjøbenhavn, Roze Bunker's square grid).
- Content ordered like a list or database: numbered items, catalogue numbers, timestamps, file names (`flyer_031.txt`).
- Stedelijk pattern: full-width rows of giant type with small images dropped in between words, rows separated by thick black rules, text cut off at the right edge.

### Imagery and art direction

- Unretouched, flash-lit, low-res or dithered photos (Low←Tech Magazine dithers every image to save energy).
- Screenshots, scans, photocopies, stickers, xerox texture, ASCII art, default OS icons.
- Product shots dropped on grids without shadows (Roze Bunker bottles on graph paper, Coal Drops Yard images cut into arches and stairs).
- Blurred or glitched portrait photography (HAN Kjøbenhavn, DesignThinkers' RGB-split "SOUND ON").

### Motion and interaction

- Abrupt: `steps()` timing, instant show/hide, blinking cursors, CSS marquee tickers.
- **Draggable windows** and pop-ups that look like OS dialogs, with an `[x]` close button.
- Cursor effects: text or image trails, crosshair cursors, hover that inverts colours (black ↔ white) with no transition.
- "View source" or debug modes that expose outlines and tag names.
- Sound: play buttons, raw WebAudio tones, radio streams (music and art sites).

### Micro-details

- Hit counters, "last updated" dates, file sizes, `<blink>`-style indicators, `[brackets]` around links.
- Default form controls left unstyled, or styled as hard 2px boxes.
- Hard offset shadows (`box-shadow: 6px 6px 0 #000`) in the "neo-brutalist" branch only.
- Selection colour inverted (`::selection { background:#000; color:#fff }`).
- Copy written in an honest, deadpan or confrontational voice.

---

## 5. Why it works

**Novelty and arousal.** Berlyne's (1971) arousal theory predicts that novelty, complexity and surprise raise interest up to a point. Hekkert, Snelders & van Wieringen (2003) showed that preference peaks at "most advanced, yet acceptable" (MAYA): designs that are novel *and* still typical enough to be understood. Successful brutalist sites are novel in surface but keep a typical structure (nav top, list of items, readable text). Failed ones lose typicality and become unusable.

**The cost of low prototypicality.** Tuch et al. (2012) found that low prototypicality and high complexity reduce first-impression beauty ratings. Brutalism deliberately pays this price with the general public in exchange for distinction with a niche audience. That is why it fits culture, music and art (audiences who value distinction) and fails for banks.

**Expressive aesthetics.** Lavie & Tractinsky (2004) separate classical aesthetics (order, clarity) from expressive aesthetics (creativity, originality, fascination). Brutalism scores low on the first and high on the second, so it is remembered but not necessarily perceived as usable.

**Style-specific research.**
- Ganci & Ribeiro (2017), *On Web Brutalism and Contemporary Web Design* (Dialectic 1(1)), is a two-sided position paper: Ganci argues brutalism is a healthy reaction to the homogenisation of web aesthetics (templates, frameworks); Ribeiro argues it distracts from usability, scalability, adaptability and accessibility.
- Suárez-Carballo (2019), *The visual language of brutalist web design* (Doxa Comunicación 28, 111–131), uses content analysis of brutalist sites to test whether web brutalism is a movement with differentiated visual characteristics.
- Rebelo, Rebelo & Rebelo (2021), *Algorithmic Experiments in the Design of Brutalist Web Pages* (ARTECH 2021, ACM), generate brutalist pages algorithmically, which shows the style has learnable rules (useful for LLM prompting).
- Copeland's *Guidelines for Brutalist Web Design* (brutalist-web.design) define the functional branch: readable on all screens, only links and buttons respond to clicks, links underlined and buttons look like buttons, the back button works, view content by scrolling, decoration only when needed, performance is a feature.

**Why juries reward it.** Awwwards Honorable Mentions and SOTDs in this folder share three things: (1) one memorable concept executed hard (HAN's pop-up shop, Heller's running headline over stacked cards, Roze Bunker's graph-paper still life); (2) tight control underneath the chaos (consistent borders, type sizes, spacing); (3) sharp culture-facing content. Raw brutalism without an idea rarely wins awards; it lives on brutalistwebsites.com instead.

> Full general references are in `00_Research/academic-findings.md`. Style-specific sources are listed in `references.md`.

---

## 6. Uniqueness levers

Pick 2–3 and commit.

1. **OS-window collage.** Draggable, closable windows (`flyer_031.txt [x]`) that stack on click. Keyboard-movable for accessibility.
2. **X-ray / view-source mode.** A button that outlines every element and prints its tag name. Turns "truth to materials" into a feature.
3. **Stretched system type.** Times or Arial at 20–30vw, `scaleY(1.8)`, cropped by the viewport. Free, fast, and unlike any template.
4. **Spreadsheet or graph-paper ground.** A visible cell grid behind everything, with content placed like cells (HAN, Roze Bunker).
5. **Sound as interface.** Every catalogue row can play a raw WebAudio tone or a 10-second clip; an ASCII waveform shows it.
6. **Ticker of truth.** A yellow marquee with real, changing information (stock count, door time, next release), not slogans.
7. **Database-honest copy.** Catalogue numbers, file names, BPMs, sizes in KB, "last modified" dates as visible design.
8. **Stedelijk rows.** Full-width giant-type rows with small images inserted between words and thick black rules.
9. **Dither everything.** Process all images to 1-bit or 4-colour dither (Low←Tech) via SVG filters or pre-processing; it is both an aesthetic and a performance win.
10. **Default-blue system.** Use only the browser's own link blue and visited purple as the palette; the history of the visitor colours the page.

---

## 7. Clichés and pitfalls

- **"Neo-brutalist" template**: pastel fills + 3px black borders + hard 4px offset shadows + Space Grotesk on every card. Now as generic as glassmorphism. Use it only with a real idea.
- **Ugly without a reason**: randomness that does not relate to the brand reads as broken, not brave.
- **Unreadable body text**: distortion and clash belong in display type; body copy still needs 16px+, real line length and contrast.
- **Fake rawness**: 4MB of JavaScript to look like 1998 HTML contradicts the idea. Raw should be fast.
- **Pure `#FF0000` small text on white** (4.0:1) fails WCAG; use `#E00000` or darker.
- **Hover-only discovery** and invisible links: anti-design must not mean anti-user (Ganci & Ribeiro 2017).
- **Copying the Balenciaga 2017 look** (black Arial on white, nothing else) without its brand power: on an unknown brand it looks unfinished.

---

## 8. Accessibility and performance notes

- System fonts mean zero font requests: an advantage to keep. If you add one display font, subset it.
- Contrast is easy (black/white) but check acid colours: white on `#00FF41` fails; black on it passes (15.4:1).
- Draggable windows: give them `role="dialog"` or `role="group"` with a label, a real close `<button>`, and keyboard moving (arrow keys on the focused title bar). On small screens make them static blocks.
- Marquee/ticker: pause on hover and focus, stop entirely with `prefers-reduced-motion`; provide the same text statically.
- Blinking: keep below 3 flashes per second (WCAG 2.3.1); avoid red flashes entirely.
- Tables should stay real `<table>` elements with `<th scope>`; on mobile, restack rows with `display:block` and `data-label` captions.
- Sound must never autoplay; every play has a visible stop; keep volume low.
- `prefers-reduced-motion`: disable trails, tickers, shakes and glitch animations.

---

## 9. Neighbouring styles and hybrids

| Blend with | Result |
|---|---|
| **CC-1 Swiss** | "Swiss brutalism": strict grid and grotesk, but raw borders, system fonts and huge cropped type (Stedelijk, Experimental Jetset, Lyon Béton SOTD 2024). The most award-friendly version. |
| **EC-1 Immersive** | Raw HTML chrome around one WebGL or 3D object (Candy Chiu's spinning type ring, MAGWAI's SPOMENIK concrete monument over repeated type). |
| **EW-2 Retro / Y2K** | OS windows, pixel fonts, early-web GIFs: "web 1.0 revival" (Aphex Twin store, Art Night's retro gradient). |
| **EW-1 Playful** | Neo-brutalism: flat bright fills, black outlines, offset shadows, friendly copy (Gumroad-style, Coal Drops Yard's coloured shapes). |
| **CW-2 Warm Organic** | Raw layout + natural materials and handwritten notes: zines, food co-ops, collectives (Roze Bunker). |
