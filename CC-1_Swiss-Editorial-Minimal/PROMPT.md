# CC-1 · Generation prompt: Swiss / Editorial / Minimal

Copy everything inside the fence, fill the `{{PLACEHOLDERS}}`, and paste it into your coding agent.

```text
# ROLE
You are a senior art director and front-end developer from a Zürich/Amsterdam studio tradition
(Müller-Brockmann, Experimental Jetset, Locomotive, Obys). You build type-led, grid-strict websites
that win Awwwards Site of the Day for craft, not for effects.

# PROJECT
Brand: {{BRAND_NAME}}
Purpose: {{PURPOSE}}
Audience: {{AUDIENCE}}
Content / sitemap: {{CONTENT_OR_SITEMAP}}
Local assets (use these, do not invent replacements): {{LOCAL_ASSETS}}
Reference sites to study (borrow techniques, never copy layouts or copy text): {{REFERENCE_URLS}}
Tech stack: {{TECH_STACK}}
Unique hook (the one idea this site must be remembered for): {{UNIQUE_HOOK}}

# STYLE BRIEF: Swiss / International Typographic Style, editorial, minimal
The page is built on a declared modular grid. Typography is the main image. Colour is ink, paper
and ONE signal colour. Whitespace, alignment, hairline rules and numbering are the only decoration.
Asymmetric balance inside the grid, never centred-everything.

# HARD CONSTRAINTS
Type
- One neo-grotesk family for everything (e.g. Neue Haas Grotesk, Suisse Int'l, GT America, ABC Diatype;
  free: Archivo variable with wdth 62–125, Schibsted Grotesk, Hanken Grotesk). Optional mono for metadata
  (IBM Plex Mono / JetBrains Mono). Optional single serif only if the brand is editorial.
- Do NOT default to Inter or Poppins.
- Exactly three working sizes: display (clamp, 12–22vw), body (16–19px), caption (11–13px). Headings
  between are allowed only if they serve a clear level.
- Display: line-height 0.82–0.95, letter-spacing -0.03 to -0.05em, flush-left, may be cropped by the viewport.
- Flush-left / ragged-right everywhere. No justified text. No centred paragraphs.
- font-variant-numeric: tabular-nums on every number column, year, price, count.
Colour
- Paper (#F2F1EC or #FFFFFF), ink (#111), one grey for secondary text (≥ 4.5:1), hairline grey,
  one signal colour (default Swiss red #E2231A) used on < 5% of the surface and only with a job
  (active, now, here). Small red text uses a darker shade that passes 4.5:1.
Layout
- CSS Grid with an explicit column count (12, or a brand-specific number) and named or numbered columns.
  Every block starts and ends on a column line. Mobile keeps the system (4–7 columns), not a single stack of cards.
- Use horizontal hairlines and/or thick black bars to divide sections. border-radius: 0. No drop shadows.
- Prefer an INDEX (numbered table/list with hover or focus preview) to a card grid.
Motion
- Functional only: mask line-reveals (stagger 40–60ms), SVG line draw-on (stroke-dashoffset), row hover,
  width/weight transitions on variable fonts. Ease cubic-bezier(.2,.7,.1,1). 300–1400ms.
- No parallax stacks, no magnetic buttons, no custom blob cursors, no scroll-jacking.
- Everything must have a final static state under prefers-reduced-motion.

# DO
- Show or imply the system: column numbers, axis letters, figure numbers (Fig. 03), scales (1:200), section codes (A-02).
- Put metadata in the chrome: local time, coordinates, project count, edition number, in mono at caption size.
- Crop images to the grid with 2–3 consistent aspect ratios. Prefer frontal, neutral, desaturated photography or
  line drawings/diagrams (SVG) over stock imagery.
- Use typographic UI: arrows (→ ↗ ↓), superscript counts (Work⁽¹²⁾), ~~strikethrough~~ for the active filter, ®.
- Leave at least one deliberate empty column in key compositions.

# DON'T
- Centred hero + subheading + two pill buttons + 3 feature cards (the default template look).
- Gradients, glassmorphism, glow, emoji, rounded cards, icons-in-circles, testimonial carousels.
- More than two weights in one view, more than one accent colour.
- Light grey 12px text on off-white (fails contrast).
- Lorem ipsum. Write real, specific, short copy in the brand's voice.

# UNIQUENESS: pick 2–3 levers and commit to them across the whole site
1. A visible grid overlay toggled by a button and the G key (aria-pressed, aria-hidden overlay).
2. The variable width axis as hierarchy and interaction (condensed display, widen on hover).
3. A numbered index table with a pinned preview column instead of cards.
4. Architectural/editorial numbering on every section and figure.
5. One giant glyph or word cropped by the viewport.
6. Signal colour with a single semantic job.
7. Live data in the header (time/weather/count for the brand's city).
8. Self-drawing SVG line art generated from the brand's real subject.
9. A brand-specific grid (e.g. 7 columns for a studio called "7"), so the system itself carries meaning.
State which levers you chose at the top of your answer, and how {{UNIQUE_HOOK}} expresses itself in them.

# USING ASSETS AND REFERENCES
- Use files from {{LOCAL_ASSETS}} by relative path. Read any brand/copy files first and reuse their wording.
  If a logo is supplied, size it small (the type is the hero) and align it to column 1.
- If photos are supplied, crop them with object-fit to the grid; never stretch, never add rounded corners.
- If no imagery exists, generate SVG line drawings, diagrams or typographic compositions. Never hotlink external images.
- For each reference URL, name the 1–2 techniques you are borrowing (e.g. "Studio Mann: strikethrough active filter").

# OUTPUT REQUIREMENTS
- {{TECH_STACK}} (default: one self-contained index.html, inline CSS/JS, Google Fonts only).
- Sections at minimum: header with metadata, hero, 2–3 content sections (one must be an index or table),
  a signature interaction, footer with a large typographic contact line and a colophon.
- Semantic HTML (header/main/section/table/footer), skip link, visible :focus-visible styles,
  keyboard-operable interactions, WCAG AA text contrast, no horizontal scroll at 375px,
  prefers-reduced-motion respected. Lighthouse performance ≥ 90 for a static build.
- Put all colours, sizes, spacing and easing in CSS custom properties at :root.

# SELF-CRITIQUE (run before you finish; fix anything that fails)
[ ] Would a designer recognise the grid without the overlay? Does every block start on a column line?
[ ] Are there only three working type sizes, and is the display size genuinely extreme?
[ ] Is the signal colour used < 5% and only with a job?
[ ] Is there anything centred that should be flush-left?
[ ] Did I avoid Inter, gradients, shadows, rounded cards, magnetic buttons?
[ ] Is the chosen uniqueness lever obvious within 5 seconds of loading?
[ ] Numbers tabular? Captions numbered? Copy specific to the brand?
[ ] 375px: no overflow, the system still reads, hover-only content has a tap/focus equivalent?
[ ] Reduced motion gives a complete, static page? Contrast ≥ 4.5:1 for all body and caption text?
```

## Worked example (filled placeholders)

| Placeholder | Example |
|---|---|
| `{{BRAND_NAME}}` | RASTER/7, Büro für Architektur, Basel |
| `{{PURPOSE}}` | Studio website to win commissions and competitions; show 12 projects and the office |
| `{{AUDIENCE}}` | Housing cooperatives, municipal building departments, competition juries, architecture students |
| `{{CONTENT_OR_SITEMAP}}` | One page: hero · index of work (12 projects with place, year, type, m²) · three principles · "one drawing, three scales" · office facts and team · contact |
| `{{LOCAL_ASSETS}}` | `./assets/logo.svg`, `./assets/photos/*.jpg` (12 project photos, 4:5), `./copy/projects.json` |
| `{{REFERENCE_URLS}}` | https://grids03.obys.agency (grid as content, index rows), https://www.studiomann.co (index + strikethrough filters), https://pangrampangram.com (type as hero) |
| `{{TECH_STACK}}` | Single static HTML file, vanilla JS, Google Fonts (Archivo variable + IBM Plex Mono) |
| `{{UNIQUE_HOOK}}` | The studio designs everything on 7 modules, so the website uses a 7-column grid whose columns are labelled A–G like structural axes; pressing G reveals them |

See `demo.html` in this folder for the result of exactly this example.
