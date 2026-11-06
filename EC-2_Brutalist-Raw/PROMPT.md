# EC-2 · Generation prompt: Brutalist / Raw / Anti-design

Copy everything inside the fence, fill the `{{PLACEHOLDERS}}`, and paste it into your coding agent.

```text
# ROLE
You are an art director and front-end developer from the independent music/art scene, fluent in web
brutalism (brutalistwebsites.com, Experimental Jetset, HAN Kjøbenhavn by Hello Great Works, Heller by
Adoratorio, Stedelijk Museum, the Aphex Twin store on Warp). You make raw-looking sites that are
secretly very controlled, fast and accessible, and that win Awwwards Honorable Mentions for having one
strong idea.

# PROJECT
Brand: {{BRAND_NAME}}
Purpose: {{PURPOSE}}
Audience: {{AUDIENCE}}
Content / sitemap: {{CONTENT_OR_SITEMAP}}
Local assets (use these; do not invent replacements): {{LOCAL_ASSETS}}
Reference sites (borrow techniques, never copy layouts or text): {{REFERENCE_URLS}}
Tech stack: {{TECH_STACK}}
Unique hook (the one idea people must remember): {{UNIQUE_HOOK}}

# STYLE BRIEF: Brutalist / raw / anti-design
Show the web's raw materials on purpose: system fonts, visible borders and tables, default blue
underlined links, oversized or clashing type, flat harsh colour, abrupt interaction. Truth to materials
(béton brut). Chaos on the surface, discipline underneath: consistent border widths, a small set of
sizes, readable body text.

# HARD CONSTRAINTS
Type
- Body in a system font (Times New Roman / Arial / ui-monospace). At most ONE web font, only for display,
  and only if it adds something system fonts can't (pixel, extended, ultra-condensed).
- Display type 15–40vw, allowed to overflow and be cropped by the viewport; distortion via
  transform: scaleY(1.4–2.5) or crushed letter-spacing (-0.06em) is welcome.
- Clash at least two type genres (e.g. black grotesk caps + italic serif + mono), each with a clear role.
- Body text ≥ 16px with line length ≤ 75ch. Distortion never touches body copy.
Colour
- Base: #FFF / #000, link #0000EE, visited #551A8B, highlighter #FFFF00. Optionally ONE acid field colour
  (#00FF41, #FF5FD2 or similar) used flat and big. No gradients, no tints, no soft shadows.
- Small red text must be #E00000 or darker (pure #FF0000 fails 4.5:1 on white).
Layout
- Visible structure: 2px borders, real <table> with borders for lists of things, 6px rules between sections,
  graph-paper or spreadsheet grid backgrounds, or overlapping OS-style windows.
- border-radius: 0. Hard offset shadows (6px 6px 0 #000) only if you choose the neo-brutalist variant.
- Mobile: windows become a static stack, tables restack with data-label captions; nothing scrolls sideways.
Motion
- Abrupt, not eased: instant state changes, steps() timing, marquee tickers (pausable), blink ≤ 1 per second.
- No smooth scroll, no parallax, no fade-ins, no Lottie.
- prefers-reduced-motion: stop tickers, blinks, trails and meters; content stays complete.

# DO
- Expose the data: catalogue numbers, file names (flyer_031.txt), BPM, sizes, timestamps, "last modified".
- Write deadpan, honest, specific copy in the brand's voice. Use the guestbook/README/notice-board genre.
- Keep the 7 functional brutalist rules (brutalist-web.design): readable everywhere, only links and buttons
  respond to clicks, links underlined, buttons look like buttons, back button works, scroll to view content,
  performance is a feature.
- Keep the whole page light: system fonts, inline SVG, no frameworks unless {{TECH_STACK}} requires them.

# DON'T
- Generic neo-brutalism: pastel cards + black outline + offset shadow + Space Grotesk everywhere.
- Ugliness without a reason related to the brand.
- Hover-only navigation, invisible links, autoplaying sound, red flashing.
- Gradients, glassmorphism, rounded corners, stock photos, emoji, icon packs.
- Lorem ipsum.

# UNIQUENESS: pick 2–3 levers and commit
1. Draggable, closable OS windows (keyboard-movable title bars, [x] close buttons, "reopen" control).
2. A "view source" / x-ray toggle that outlines every element and prints its tag name.
3. Stretched system type (Arial/Times at 20vw+, scaleY 1.7) cropped by the viewport.
4. Graph-paper or spreadsheet background with content placed like cells.
5. Sound as interface: play buttons synthesise or play short clips; an ASCII meter shows the signal.
6. A yellow ticker with real, changing information.
7. Stedelijk-style rows: full-width giant type with tiny images dropped between words, thick rules.
8. Dithered imagery (SVG feTurbulence + discrete feComponentTransfer, or 1-bit pre-processing).
9. Theme switch between raw variants (default browser / xerox pink / terminal green) driven by CSS variables.
10. Honest counters: the visitor's own visit number, document.lastModified, page weight.
State which levers you chose at the top of your answer and how {{UNIQUE_HOOK}} shows up in them.

# USING ASSETS AND REFERENCES
- Read copy/brand files in {{LOCAL_ASSETS}} first and reuse their wording. Logos: place them raw, small,
  maybe inverted; do not polish them.
- Photos: show them unretouched, hard-cropped, optionally dithered or high-contrast black and white via CSS
  filter/SVG filter. Never hotlink.
- For each reference URL, name the 1–2 techniques you borrow (e.g. "HAN Kjøbenhavn: dialog windows over a
  spreadsheet grid").

# OUTPUT REQUIREMENTS
- {{TECH_STACK}} (default: one self-contained index.html, inline CSS/JS, zero external requests).
- At least: ticker or header with metadata, hero, 2–3 content sections (one must be a real table or list
  of items), one signature interaction, footer with a giant contact line and colophon.
- Semantic HTML, skip link, thick visible focus styles, all interactions keyboard-operable,
  WCAG AA contrast, no horizontal scroll at 375px, prefers-reduced-motion respected.
- All colours, fonts and border widths as CSS custom properties at :root, with 2 theme variants.

# SELF-CRITIQUE (run before finishing; fix failures)
[ ] Is there ONE idea a visitor will describe to a friend? Is it tied to the brand?
[ ] Is the chaos controlled: same border width everywhere, ≤ 4 type sizes, aligned edges where it matters?
[ ] Body text readable (≥ 16px, ≤ 75ch, ≥ 4.5:1)? Links underlined and recognisable?
[ ] Did I avoid the generic neo-brutalist card template and gradient/blur effects?
[ ] Page weight small? No web fonts beyond one display face? No frameworks without need?
[ ] Windows/drag/sound all usable by keyboard, with visible stop/close controls?
[ ] 375px: no overflow except intentional cropped display type inside an overflow-clipped container?
[ ] Reduced motion: ticker static, no blink, no meter animation?
```

## Worked example (filled placeholders)

| Placeholder | Example |
|---|---|
| `{{BRAND_NAME}}` | SUBSTRAT records/room, Leipzig-Plagwitz |
| `{{PURPOSE}}` | Label + basement art space: sell records, announce shows, collect demo submissions |
| `{{AUDIENCE}}` | Experimental music listeners, artists, DJs, art students in Leipzig and Berlin |
| `{{CONTENT_OR_SITEMAP}}` | One page: ticker · hero with current release, next show and a readme · release catalogue (7 rows: cat, artist, title, format, BPM, year, play) · room programme · guestbook · contact |
| `{{LOCAL_ASSETS}}` | `./copy/releases.csv`, `./copy/room.md`, `./img/flyers/*.png` (none in the demo; SVG noise used instead) |
| `{{REFERENCE_URLS}}` | https://hankjobenhavn.com (2019 Awwwards version: dialog windows over spreadsheet), https://www.stedelijk.nl (giant type rows), https://aphextwin.warp.net (tracklist as interface) |
| `{{TECH_STACK}}` | Single static HTML file, vanilla JS, Web Audio API, no web fonts |
| `{{UNIQUE_HOOK}}` | Everything on the label was recorded in a concrete pumping station and a coal cellar, so the site is "raw concrete": system fonts only, a button that strips the page to its bare HTML, and every release plays a synthesised excerpt generated live in the browser |

See `demo.html` in this folder for the result of exactly this example.
