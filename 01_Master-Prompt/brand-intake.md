# Brand intake sheet

Fill this in before you run `MASTER_PROMPT.md`. Five minutes here saves hours of generic output. Paste the filled sheet into the `{{BRAND_INTAKE}}` slot of the master prompt.

> The single biggest cause of "AI-looking" sites is a thin brief. When the model knows nothing specific, it falls back to the most probable design: centred hero, Inter, purple gradient, three feature cards. Every answer below gives it something specific to work from instead.

---

## 1. Basics
| Field | Your answer |
|---|---|
| Brand / project name | |
| What it is, in one sentence | |
| Site type | portfolio · creative agency · corporate/finance · SaaS/dev tool · e-commerce (luxury) · e-commerce (consumer) · editorial/media · nonprofit/NGO · event/festival · personal blog · restaurant/hospitality · education · other: |
| Primary goal of the site (one only) | e.g. get hired, book a demo, sell product, get donations, sell tickets |
| Secondary goal | |
| Primary audience (who, age, context, device) | |
| What the visitor should **feel** in the first 3 seconds (3 adjectives) | |
| What they should **do** before leaving | |

## 2. Position on the style map
Score from 1 to 5. If you're unsure, leave it blank and the model will propose a score with its reasoning.

| Axis | 1 | 5 | Score |
|---|---|---|---|
| Aesthetic mode | Classical (orderly, clear, expected) | Expressive (original, surprising, artistic) | |
| Temperature | Cool (precise, technical, distant) | Warm (human, tactile, emotional) | |
| Density | Airy, lots of whitespace | Dense, information-rich | |
| Motion | Static | Kinetic, immersive | |
| Ornament | Bare | Decorated, textured | |
| Contrast | Soft, tonal | Hard, high-contrast | |

Brand personality (Aaker, 1997). Rank the top 2: **Sincerity** (honest, wholesome) · **Excitement** (daring, spirited, imaginative) · **Competence** (reliable, intelligent, successful) · **Sophistication** (upper-class, charming) · **Ruggedness** (outdoorsy, tough)

## 3. Assets (local data)
List paths. The model will read these and treat them as ground truth over its own defaults.

| Asset | Path / note |
|---|---|
| Logo (SVG preferred) | |
| Existing brand colours (hex) | |
| Brand fonts (files or names) | |
| Photography / illustration folder | |
| Copy: headlines, about text, product data | |
| Existing site / codebase | |
| Things that are **non-negotiable** (legal, brand rules) | |

## 4. References (external data)
| Type | URLs |
|---|---|
| 2–5 sites you **love** (any industry), with one line each on *what exactly* you love | |
| 1–3 sites you **dislike** or want to avoid looking like | |
| Direct competitors (to differentiate *from*) | |
| Non-web inspiration: posters, packaging, architecture, film, album art | |

## 5. The unique hook
One idea that only this brand could own. This is what turns a good site into a memorable one. Examples:
- A coffee roaster's whole site scrolls like a roast curve: colour shifts from green to dark brown as you go down.
- An architect's portfolio where the grid lines are the actual plan dimensions of their best building.
- A dev-tool where the hero is a real, typeable terminal running the product.
- A bakery whose section dividers are hand-torn paper edges scanned from their bag.

Your hook:

## 6. Constraints
| Field | Answer |
|---|---|
| Tech stack | plain HTML/CSS/JS · React/Next · Astro · Vue/Nuxt · Svelte · WordPress · Webflow · other |
| Performance budget | e.g. LCP < 2.5 s on 4G; no WebGL on mobile |
| Accessibility target | WCAG 2.2 AA (default) |
| Languages / RTL | |
| Pages needed | |
| Deadline / scope | one landing page · full site · design system only |
