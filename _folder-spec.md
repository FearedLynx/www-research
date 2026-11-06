# Folder spec (shared by every style folder)

This library classifies web aesthetics on two primary axes, the way painters split colours into warm and cool:

| Axis | Pole A | Pole B | Source |
|---|---|---|---|
| **Aesthetic mode** | **Classical** (order, clarity, symmetry, restraint) | **Expressive** (originality, creativity, sophistication, surprise) | Lavie & Tractinsky (2004) |
| **Temperature** | **Cool** (rational, technical, distant, precise) | **Warm** (human, emotional, tactile, inviting) | colour/brand-personality research |

That gives four quadrants. Folder prefixes: `CC` = Classical-Cool, `CW` = Classical-Warm, `EC` = Expressive-Cool, `EW` = Expressive-Warm.

| Folder | Style |
|---|---|
| CC-1_Swiss-Editorial-Minimal | Swiss / International Typographic, editorial grids, minimal |
| CC-2_Corporate-Trust | Enterprise, finance, consulting, institutional clarity |
| CC-3_Tech-Product | SaaS / dev tools: dark UI, gradients, glow, bento grids, product-as-hero |
| CW-1_Luxury-Refined | Fashion, hospitality, jewellery, real estate: serif, whitespace, slow motion |
| CW-2_Warm-Organic | Wellness, food, sustainability, NGOs: earthy palettes, natural texture, soft shapes |
| EC-1_Immersive-Experimental | WebGL/3D, shaders, scroll-driven storytelling, creative agencies and dev portfolios |
| EC-2_Brutalist-Raw | Brutalism, anti-design, raw HTML, oversized type, culture, art, music |
| EW-1_Playful-Illustrative | Consumer brands and apps: illustration, mascots, bright colour, bouncy motion |
| EW-2_Retro-Nostalgic | Y2K, 70s/80s, pixel, risograph, early-web and vintage-print revival |

Secondary axes, scored 1–5 in each README: **Density** (airy → dense), **Motion** (static → kinetic), **Ornament** (bare → decorated), **Contrast** (soft → hard).

## Each style folder must contain

```
<style>/
  README.md        style definition and analysis (template below)
  PROMPT.md        ready-to-paste generation prompt (template below)
  references.md    real awarded sites and the creators behind them
  tokens.css       CSS custom properties: colour, type scale, spacing, radius, shadow, motion (+ 2 variants)
  demo.html        one self-contained page for a FICTIONAL brand, built in this style
  images/          reference screenshots/og-images + images/CREDITS.md
```

### README.md template
1. **One-line definition**
2. **Position on the map**: Classical↔Expressive (1–5), Cool↔Warm (1–5), Density, Motion, Ornament, Contrast (each 1–5, with a one-line justification)
3. **Best-fit purposes**: portfolio / agency / corporate / SaaS / e-commerce / editorial / nonprofit / event / personal, each rated ✅ strong, ➖ possible, ❌ avoid, with the reason
4. **Visual DNA**: typography (named families, free alternatives on Google Fonts), colour (hex palette and its logic), layout and grid, imagery and art direction, motion and interaction, micro-details (cursors, borders, grain, etc.)
5. **Why it works**: the psychology and research behind it (cite papers by author and year; full refs live in `00_Research/academic-findings.md`) plus what award juries reward
6. **Uniqueness levers**: 6–10 concrete ways to make a site in this style NOT look like a template
7. **Clichés and pitfalls**: what makes it look generic or AI-made
8. **Accessibility and performance notes**
9. **Neighbouring styles and hybrids**: how it blends with other folders

### PROMPT.md template
A copy-paste prompt for an LLM coding agent, containing:
- Placeholders: `{{BRAND_NAME}}`, `{{PURPOSE}}`, `{{AUDIENCE}}`, `{{CONTENT_OR_SITEMAP}}`, `{{LOCAL_ASSETS}}` (paths to logos, photos, copy, brand files), `{{REFERENCE_URLS}}`, `{{TECH_STACK}}`, `{{UNIQUE_HOOK}}` (one memorable idea specific to this brand)
- Role and context, style brief, hard constraints (type, colour, layout, motion), explicit DO / DON'T lists, a uniqueness section ("pick 2–3 levers and commit"), how to use local assets and external references, output requirements, and a self-critique checklist the model runs before finishing
- A short worked example of filled placeholders

### references.md
- At least **8 real sites** with: name, URL, studio or creator, the creator's portfolio URL, the award (Awwwards SOTD/SOTM/SOTY/Honorable, CSSDA, FWA, Webby, ADC, TDC, D&AD, Red Dot, etc.) and year, and **"what to steal"**: specific techniques, not adjectives
- At least **4 creators or studios who specialise in this style**, with portfolio links and their signature moves
- Mark every award claim **✔ verified** (you saw it on the award page or the studio's site) or **? unverified**. Never invent awards, URLs or names.

### images/
- Download real reference images with `curl -L` (the page's `og:image` / `twitter:image`, or images from the award-gallery page). Use descriptive filenames: `<site-name>_og.jpg`.
- `images/CREDITS.md` lists each file with its source URL, owner, and "for private study/reference only".
- If an image can't be fetched, say so in CREDITS.md. Never hotlink in the demo.

### demo.html
- Single file, inline CSS/JS, opens by double-clicking. Google Fonts and cdnjs/jsdelivr libraries are allowed.
- Use a fictional brand that fits the style's best purpose. Show at least: hero, 2–3 content sections, a signature interaction, and a footer.
- Responsive at 375px, honours `prefers-reduced-motion`, WCAG AA contrast on text.
- Put the "uniqueness levers" into practice. It should look like an award entry, not a template.
- Images: CSS/SVG art, generated gradients, or `images/` files. No external hotlinked photos.

## Quality bar
- Specific beats general: "Neue Haas Grotesk at 14vw, tracking -0.04em" beats "big bold type".
- Every factual claim (award, creator, paper) must be traceable to a source. Mark anything uncertain.
- Write for a human reader: clear headings, short paragraphs, tables where they help.
