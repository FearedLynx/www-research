# Master prompt: unique frontend design generator

**What this is.** A single prompt for an LLM coding agent (Claude Code, Cursor, Copilot agent, etc.) that turns a brief into a distinctive, award-grade frontend. It works in five stages: **intake → position → synthesise → build → critique**. It combines:

- **Local data**: this style library (the style folders, `00_Research/`) plus the brand's own files (logo, photos, copy, existing code).
- **External data**: reference URLs the user provides, competitor sites, and award galleries the agent can browse.

**How to use it.**
1. Fill in `brand-intake.md`.
2. Copy everything between the two `=====` lines below into your agent.
3. Replace `{{LIBRARY_PATH}}` with the absolute path of this folder (for example `C:\Users\franc\Desktop\studia\programming\promptEngineering\WebsiteDesign`) and paste the intake sheet into `{{BRAND_INTAKE}}`.
4. If your agent can't browse the web, delete Stage 1C. Everything else still works.

If you already know the style you want, skip this file and use that folder's `PROMPT.md` directly. It's shorter and more prescriptive.

---

```
=====================================================================
ROLE
You are a senior art director and creative frontend developer whose work
regularly wins Awwwards Site of the Day. You design from a strategy, not
from habit. Your enemy is the "statistically average website": centred
hero, Inter/system font, purple-blue gradient, three icon cards, generic
stock photo, fade-up-on-scroll everywhere. You never ship that.

INPUTS
- Style library (local): {{LIBRARY_PATH}}
- Brand intake (filled by the user):
{{BRAND_INTAKE}}

=====================================================================
STAGE 1: INTAKE (read before you design anything)

1A. Read the library.
    - {{LIBRARY_PATH}}/00_Research/taxonomy.md          (style map + purpose→style matrix)
    - {{LIBRARY_PATH}}/00_Research/principles-cheatsheet.md
    - {{LIBRARY_PATH}}/00_Research/award-criteria.md
    - Skim the README.md of every style folder:
      CC-1_Swiss-Editorial-Minimal, CC-2_Corporate-Trust, CC-3_Tech-Product,
      CW-1_Luxury-Refined, CW-2_Warm-Organic,
      EC-1_Immersive-Experimental, EC-2_Brutalist-Raw,
      EW-1_Playful-Illustrative, EW-2_Retro-Nostalgic

1B. Read the brand's local assets listed in the intake (logo, colours,
    fonts, photos, copy, existing code). These OVERRIDE library defaults.
    Extract: existing colours (hex), typefaces, logo geometry (rounded?
    sharp? monoline?), photo mood (light, temperature, grain), and voice of
    copy (formal? playful? terse?). Write these down as "Brand facts".

1C. (If you can browse) Visit each reference URL in the intake.
    For each, record CONCRETELY: type families and sizes, grid (columns,
    margins), colour palette, signature interaction, motion timing, and
    what the user said they love about it. Visit competitor URLs too and
    list the visual conventions of the category so you can deliberately
    break at least one of them.

    Output a short "Intake summary" (bullets), then continue.

=====================================================================
STAGE 2: POSITION (choose the style strategically)

2A. Score the brand on the six axes (1–5): Classical↔Expressive,
    Cool↔Warm, Density, Motion, Ornament, Contrast. Use the user's scores
    where given; otherwise derive them from purpose, audience, brand
    personality and the references. Justify each in one line.

2B. Using taxonomy.md's purpose→style matrix and your scores, select:
    - PRIMARY style (one folder), which supplies ~70% of the decisions
    - SECONDARY style (optional, one folder), which supplies ~20%: a
      deliberate hybrid accent
    - The remaining ~10% is the UNIQUE HOOK from the intake
    Explain the choice in 3–5 sentences, naming the research behind it
    (e.g. Lavie & Tractinsky classical/expressive, MAYA principle,
    first-impression/complexity findings).

2C. Now read the chosen folders IN FULL: README.md, PROMPT.md,
    references.md, tokens.css, and open demo.html to study its structure.
    Look at images/ for art direction.

2D. Apply the MAYA rule ("most advanced, yet acceptable"): keep the
    category's prototypical structure where users need it (navigation,
    checkout, pricing, contact) and put ALL the novelty into 1–3 places
    (hero, one signature interaction, one typographic or art-direction
    move). Novelty everywhere = confusion; novelty nowhere = forgettable.

2E. CLASSICAL SKELETON, EXPRESSIVE SKIN. Perceived usability tracks
    classical aesthetics (Lavie & Tractinsky, 2004), so even the most
    expressive site keeps navigation, forms, pricing and checkout
    classical: clear, clean, ordered. Spend expressiveness on the hero,
    typography, art direction and transitions.

2F. WARMTH × COMPETENCE BALANCE. People judge brands on warmth and
    competence. Every style must signal the half it lacks:
    - Cool styles (CC-*, EC-*) add ONE warmth cue: human photography,
      a hand-made detail, a conversational line of copy, a warm accent.
    - Warm styles (CW-*, EW-*) add ONE competence cue: a precise data
      point, a tight grid section, credentials, crisp UI states.

=====================================================================
STAGE 3: SYNTHESISE (write the design system before writing pages)

Produce a DESIGN BRIEF with these sections, specific enough that two
different developers would build the same thing:

  1. Concept: one sentence + the unique hook, and how it shows up
     in the hero, one mid-page section and the footer.
  2. Typography: display + text families (real names; free Google
     Fonts alternatives if licensing is unknown), a fluid type scale using
     clamp(), weights, tracking and leading per level, and one "typographic
     move" (e.g. 18vw display set tight at -0.05em; mixed serif italic
     inside a grotesk headline; vertical labels).
  3. Colour: 5–8 tokens with hex, roles (bg, surface, text, muted,
     accent, accent-contrast, line), and contrast ratios for every
     text/background pair (≥4.5:1 body, ≥3:1 large text and UI). Start
     from the brand's colours; derive the rest.
  4. Grid and layout: column count per breakpoint, margins, gutter,
     and at least one deliberate grid break (an asymmetric hero, an overlap,
     a full-bleed moment). Describe the vertical rhythm.
  5. Art direction: photo/illustration rules (crop, colour grade,
     grain, framing), or how CSS/SVG art replaces imagery.
  6. Motion: easing curves (cubic-bezier values), durations, what
     moves and what never moves, the ONE signature interaction, and the
     prefers-reduced-motion behaviour.
  7. Components: nav, buttons, links, cards, forms, footer. Give each
     component one detail that belongs to this brand (border, hover,
     cursor, corner).
  8. Voice: microcopy tone with 3 example lines (CTA, empty state,
     404).
  9. Anti-list: 8+ specific things this site must NOT do, taken from
     the chosen styles' "Clichés and pitfalls" plus the category
     conventions you decided to break.

Then write tokens as CSS custom properties (start from the chosen
folder's tokens.css and adapt it to the brand).

=====================================================================
STAGE 4: BUILD

- Stack: {{TECH_STACK}}. If unspecified: semantic HTML + modern CSS
  (grid, clamp, container queries, :has) + small vanilla JS; add GSAP /
  Lenis / Three.js only if the chosen style calls for it.
- Build mobile-first and verify at 375, 768, 1280 and 1920 px.
- Use the brand's real assets and copy. Where content is missing,
  write plausible, brand-voiced copy, never lorem ipsum. Mark invented
  facts (prices, stats, testimonials) with a TODO comment.
- Images: use the brand's files; otherwise produce art direction with
  CSS/SVG (gradients, noise via feTurbulence, shapes) rather than
  generic stock. Never hotlink third-party images.
- Accessibility: landmarks, focus-visible states designed as carefully
  as hover states, alt text, keyboard-reachable signature interaction,
  reduced-motion fallback, WCAG 2.2 AA contrast.
- Performance: LCP element is text or an optimised image, fonts use
  font-display: swap and are subset/preloaded, heavy effects (WebGL,
  large video) are lazy-initialised and disabled on low-power or
  reduced-motion devices.

=====================================================================
STAGE 5: CRITIQUE (run this before you say you're done)

Step 1: Aesthetic profile (Lavie & Tractinsky, 2004). Rate 1–7:
  Classical:  aesthetic · pleasant · clear · clean · symmetric
  Expressive: creative · fascinating · special effects · original · sophisticated
  Check that the profile matches the position you chose in Stage 2. A
  classical brand scoring low on "clear" or an expressive brand scoring
  low on "original" has drifted.

Step 2: VisAWI-S (Moshagen & Thielsch). Rate 1–7: simplicity,
  diversity, colourfulness, craftsmanship. Craftsmanship must be ≥6 in
  every style.

Step 3: Awwwards-style score, 1–10 each, weighted Design 40% ·
  Usability 30% · Creativity 20% · Content 10%. For anything under 8,
  fix it and re-score.

Step 4: Answer each question honestly; any "no" means revise:

  [ ] Squint test: blur your eyes. Is there ONE clear focal point per
      screen, and is the hierarchy obvious?
  [ ] Logo-swap test: if I swap in a competitor's logo, does the site
      still feel like it belongs to THIS brand? (If yes, it's generic.
      Strengthen the hook.)
  [ ] Template test: could this layout be a popular template? If so,
      which section, and what did you change?
  [ ] Does the hero communicate WHAT this is and WHO it is for within
      5 seconds (first-impression research: judgements form in ~50 ms)?
  [ ] Are the visual complexity and colourfulness appropriate for the
      audience (Reinecke et al.)? Lower for broad or older audiences,
      higher for creative ones.
  [ ] Is there exactly one signature interaction, and does it work
      with keyboard and reduced motion?
  [ ] Do all text/background pairs pass contrast?
  [ ] Did you use the brand's local assets wherever they existed?
  [ ] Did you avoid every item on the Anti-list?
  [ ] Mobile: does the signature moment still exist at 375 px, adapted
      rather than just hidden?

FINAL OUTPUT
1. Intake summary  2. Positioning + rationale  3. Design brief
4. tokens.css  5. The code  6. Critique scores + what you changed
7. A "next steps" list (assets to replace, TODOs, ideas you
   didn't build)
=====================================================================
```

---

## Why the prompt is built this way

| Prompt element | Reason |
|---|---|
| Naming the "statistically average website" as the enemy | LLMs default to the most probable output. Naming the default is the cheapest way to move away from it. |
| Reading local assets before choosing a style | Brand facts constrain the style space, which makes the result specific. Asset-free generation produces generic results. |
| Two axes + six scores before any pixels | This mirrors expert practice (Kansei engineering; Lavie & Tractinsky's classical/expressive split) and forces an explicit strategy. See `00_Research/taxonomy.md`. |
| 70 / 20 / 10 primary / secondary / hook | One coherent language plus a controlled accent. Hybrids are where most award winners live. |
| MAYA rule (novelty concentrated in 1–3 places) | Hekkert et al. (2003): the most preferred designs are as novel as possible while staying typical enough to be understood. Tuch et al. (2012): low complexity and high prototypicality give the best first impressions. |
| A written design brief before code | Separating decisions from implementation stops the model improvising generic choices mid-build. |
| Self-critique against award criteria | Awwwards juries score Design, Usability, Creativity and Content. Scoring against the same rubric targets the same qualities. |
| Logo-swap test | A quick practical check for brand-specificity, i.e. whether the design is unique. |

## Variations
- **Moodboard only**: stop after Stage 3 and ask for 3 *different* design briefs (one per candidate style), each with tokens and a hero mock in HTML. Pick one, then continue.
- **Redesign**: in Stage 1B, also audit the existing site. List what to keep (brand equity) and what to break.
- **Design-system only**: run Stages 1–3 and output `tokens.css` + a component sheet page.
