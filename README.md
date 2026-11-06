# Website Design Style Library

A research-backed library for prompting LLM coding agents to produce **distinctive, award-quality frontends** instead of the "statistically average website".

Built in November 2026 from three kinds of sources:
1. **Award-winning sites**: Awwwards (SOTD/SOTM/SOTY), CSS Design Awards, FWA, Webby and others, plus the portfolios of the studios and developers who made them.
2. **Academic research**: about 60 verified papers on web aesthetics, first impressions, colour, typography and brand personality (`00_Research/`).
3. **Practitioner knowledge**: award-jury criteria, NN/g, Baymard, WCAG 2.2, Core Web Vitals.

---

## How the styles are categorised

Painters split colours into **warm and cool**. Web design has an equivalent backed by research: two primary axes.

| Axis | ← | → | Evidence |
|---|---|---|---|
| **Aesthetic mode** | **Classical**: clear, clean, symmetric, pleasant | **Expressive**: original, creative, fascinating, special effects | Lavie & Tractinsky (2004); users perceive website aesthetics on exactly these two factors |
| **Temperature** | **Cool**: precise, rational, competent | **Warm**: human, tactile, inviting | Colour-emotion research, warmth/competence (Fiske et al.; Aaker et al. 2010) |

```
                         EXPRESSIVE
                             ▲
    EC-2 Brutalist-Raw       │       EW-2 Retro-Nostalgic
    EC-1 Immersive-Exp.      │       EW-1 Playful-Illustrative
                             │
  COOL ◄─────────────────────┼─────────────────────► WARM
                             │
    CC-3 Tech-Product        │       CW-1 Luxury-Refined
    CC-1 Swiss-Editorial     │       CW-2 Warm-Organic
    CC-2 Corporate-Trust     │
                             ▼
                         CLASSICAL
```

Every style is also scored 1–5 on four secondary axes: **Density, Motion, Ornament, Contrast**. The full reasoning, coordinates and a Mermaid chart are in [`00_Research/taxonomy.md`](00_Research/taxonomy.md).

---

## Which style for which site?

Here are the top picks. The full ✅/➖/❌ matrix covering all 9 styles is in `00_Research/taxonomy.md` §4.

| Site purpose | First choice | Also strong |
|---|---|---|
| Designer / developer portfolio | EC-1 Immersive, CC-1 Swiss | EC-2 Brutalist, EW-2 Retro |
| Creative agency | EC-1 Immersive | CC-1 Swiss, EC-2 Brutalist |
| Corporate / finance / consulting | CC-2 Corporate Trust | CC-1 Swiss |
| SaaS / developer tools | CC-3 Tech Product | — |
| Fashion / luxury e-commerce | CW-1 Luxury | CC-1 Swiss |
| Consumer e-commerce / D2C | EW-1 Playful | CW-2 Organic |
| Editorial / media | CC-1 Swiss | CW-1 Luxury, EC-2 Brutalist |
| Nonprofit / NGO | CW-2 Organic | EW-1 Playful |
| Event / festival | EW-2 Retro, EC-1 Immersive | EC-2 Brutalist, EW-1 Playful |
| Restaurant / hospitality | CW-1 Luxury, CW-2 Organic | EW-2 Retro |
| Education | CC-2 Corporate, CW-2 Organic | EW-1 Playful (for children) |

---

## Folder map

| Folder | Contents |
|---|---|
| [`00_Research/`](00_Research) | `academic-findings.md` (papers → design implications), `taxonomy.md` (the style map and matrices), `award-criteria.md` (what juries score), `principles-cheatsheet.md` (evidence-based rules), `bibliography.md` (APA) |
| [`01_Master-Prompt/`](01_Master-Prompt) | `MASTER_PROMPT.md` (the general prompt that picks a style for you) and `brand-intake.md` (the brief you fill in first) |
| `CC-1` … `EW-2` (9 style folders) | Each one has `README.md` (analysis), `PROMPT.md` (ready-to-paste prompt), `references.md` (award winners + creators), `tokens.css` (design tokens), `demo.html` (an example site; double-click to open), `images/` (reference screenshots + `CREDITS.md`) |
| `_folder-spec.md` | The template every style folder follows |

---

## How to use it

**A. You know the style you want**
1. Open that folder's `demo.html` and `images/` to confirm the look.
2. Copy its `PROMPT.md`, fill in the `{{placeholders}}`, and paste it into your agent.

**B. You don't know the style yet (recommended)**
1. Fill in `01_Master-Prompt/brand-intake.md`. The more specific it is, the more unique the result.
2. Paste `01_Master-Prompt/MASTER_PROMPT.md` into an agent that can read this folder (Claude Code, Cursor and similar), with `{{LIBRARY_PATH}}` set to this folder.
3. The agent reads your assets and references, scores the brand on the axes, picks a primary style + a secondary accent + your unique hook, writes a design brief and tokens, builds the site, and then critiques it against the award rubric.

**C. Study**
Read `00_Research/principles-cheatsheet.md` first (one page), then a style's `README.md` → "Why it works" and "Uniqueness levers".

---

## The core rules in one screen

1. **Classical skeleton, expressive skin.** Perceived usability tracks *classical* aesthetics, so navigation, forms and checkout stay clear. Spend novelty on the hero, type, art direction and motion.
2. **MAYA: most advanced, yet acceptable** (Hekkert et al., 2003). Keep the genre's familiar structure (Tuch et al., 2012) and commit to 2–3 bold, novel moves.
3. **Judgements happen in ~50 ms** (Lindgaard et al., 2006), driven mostly by visual complexity and colourfulness (Reinecke et al., 2013). The hero must be legible at a glance.
4. **Warmth × competence.** Cool styles add one warm cue; warm styles add one competence cue.
5. **Juries weight Design 40 · Usability 30 · Creativity 20 · Content 10** (Awwwards). Craft and usability come before spectacle.
6. **Use real brand material.** Local assets + a unique hook are what separate a memorable site from a template. Run the logo-swap test.

---

## Notes on sources and images
- Award claims in each `references.md` are marked **✔ verified** or **? unverified**. Papers in `00_Research/` were checked against Crossref or publisher pages; unconfirmed items are listed separately.
- Images in `*/images/` were downloaded from the public `og:image`/share images of the referenced sites **for private study only**. Ownership and sources are in each `CREDITS.md`. Don't republish them.
- Every `demo.html` uses a **fictional brand** and original CSS/SVG art.
