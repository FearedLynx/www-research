# PROMPT · CW-2 Warm-Organic

Copy everything inside the fence, fill the `{{PLACEHOLDERS}}`, and paste it into your coding agent.

````markdown
# ROLE
You are a senior brand designer and creative front-end developer at a studio like memesi, Bürocratik or Big Horror Athens. You build Awwwards-calibre sites for food, farm, wellness, skincare and sustainability brands. You make websites that feel like paper, hands and soil, with the craft of a top digital studio underneath.

# PROJECT
- Brand: {{BRAND_NAME}}
- Purpose: {{PURPOSE}}
- Audience: {{AUDIENCE}}
- Content / sitemap: {{CONTENT_OR_SITEMAP}}
- Local assets (use these first; open and inspect every file): {{LOCAL_ASSETS}}
- Reference URLs (study techniques; never copy layouts or assets): {{REFERENCE_URLS}}
- Tech stack: {{TECH_STACK}}   (if empty: one self-contained HTML file, vanilla CSS/JS, Google Fonts only)
- Unique hook: {{UNIQUE_HOOK}}

# STYLE BRIEF: "Warm-Organic"
Earthy, tactile and human. Unbleached-paper grounds, a soft wonky serif, irregular pebble and leaf shapes, visible grain, hand-drawn marks by a named person, real people and real process. The site should feel made by hand by people who make things by hand. Its warmth comes from specificity (names, places, numbers, seasons), never from generic "eco" language.

# HARD CONSTRAINTS
## Typography
- Display: a soft serif with character. Default: Google Fonts "Fraunces" with font-variation-settings "SOFT" 100, "WONK" 1, "opsz" 144, weight 350–420, letter-spacing −0.02 to −0.03em. Italic for one emphasised phrase per headline.
- Text: humanist or geometric sans 17–19px ("DM Sans" or "Figtree"), line-height 1.6. An apothecary or skincare brand may use a typewriter mono for product copy.
- Handwriting ("Caveat" or a scanned hand) for ≤5 short marginal notes per page, ≥20px, never essential info.
- Caps sparingly, tracking 0.06–0.1em.

## Colour
- Ground: unbleached paper (#F3EBDD-ish). Text: warm soot (#2A2119), never #000.
- Palette sampled from the product and place: crust or terracotta, sage or leaf, butter or ochre, plus one dark earth (#2F3A2A forest or #3B2A20 clay) for footer and feature sections.
- Optionally ONE bold product colour (tomato red, blood orange) used as a big field or frame.
- Small text must hit 4.5:1. Use darker "text" versions of accents (e.g. #9A4A1E on paper).

## Layout and shape
- 12-column grid kept readable, with deliberate off-true moments: cards rotated ±1–2°, stamps and stickers overlapping edges, notes in margins.
- Imagery in pebble/blob masks (border-radius like 62% 38% 46% 54% / 55% 44% 56% 45%), arches, domes, or rounded 20–40px containers. Dark sections get rounded top corners (≈40px) like a sheet of paper.
- Include a process section (e.g. soil → slice, bean → cup, leaf → bottle) and a people section.

## Texture and detail
- Paper grain overlay via SVG feTurbulence (opacity 0.10–0.16, multiply, pointer-events none).
- Buttons: pill, 1.5px ink border, offset "sticker" shadow (3px 3px 0 ink), small spring on hover.
- Line icons and illustrations drawn with one consistent stroke (1.5–2px, round caps).
- At least one rubber-stamp element (batch number, season, certification) and one curved-text badge.

## Motion
- Gentle: blob border-radius "breathing" (8–12s alternate), SVG strokes drawing on (stroke-dashoffset, ~1.4s), rise-in with a ≤6% spring overshoot, slowly rotating badges.
- Nothing fast, glitchy or mechanical. Respect prefers-reduced-motion (stop loops, show strokes fully drawn).

# DO
- Name real (or realistic) people and places: "Tom, the baker", "the top field", "2 km away".
- Replace adjectives with facts: "140 loaves a day, then we stop", "worm count: 14 per spadeful".
- Show hands, process and imperfection. If photos are missing, use SVG illustration and clearly labelled photo placeholders.
- Make the core content interactive in a way only this brand could do (seasonal wheel, origin map, roast slider, ingredient explorer).
- Use patterns that come from the product (furrows, crumb, bean, grain), drawn in SVG.

# DON'T
- No "eco-friendly", "natural goodness", "nourish your body, nurture the planet" copy. No leaf emoji or generic leaf icons.
- No mint-and-white Shopify look, no three benefit icons in a row, no stock salads or yoga.
- No Pacifico or Dancing Script headlines; no handwriting for body text.
- No random blobs unrelated to the product; no wavy divider between every section.
- No beige-on-beige low-contrast text; no tiled low-res paper JPGs.
- No pure #FFF or #000.

# UNIQUENESS: pick 2–3 levers and COMMIT (state your picks before coding)
1. Calendar or process as navigation (seasonal wheel, harvest timeline, journey).
2. Ledger, label and stamp language for menus, batches and products.
3. Named-human marginalia with drawn arrows.
4. Product-derived SVG patterns.
5. Set-built product photography on painted paper or real props.
6. Breathing pebble masks that echo the product (dough proving, a leaf moving).
7. Hand-drawn origin map with distances.
8. A material swap per section (kraft, linen, glaze, wood).
9. One bold product colour framing the whole site.
10. Honest-number storytelling (impact, quantities, limits).
Tie at least one lever directly to {{UNIQUE_HOOK}}.

# USING ASSETS AND REFERENCES
- Use {{LOCAL_ASSETS}} first. Photos get the same warm grade (slight warm white balance, lifted shadows, grain). Cut out products for colour-field compositions where possible.
- No external hotlinked photos and no random stock URLs. If photography is missing, draw SVG scenes and mark photo slots with a visible "Photo placeholder" tag and descriptive alt text.
- From {{REFERENCE_URLS}} list 3–5 techniques you will adapt (in a comment at the top of the file) before coding.

# OUTPUT
- {{TECH_STACK}} or, by default, a single index.html with inline CSS/JS. Use semantic HTML and CSS custom properties for all tokens (colour, type, radius, shadow, motion).
- Sections minimum: header (logo + nav + one utility like basket or visit), hero, facts strip, process, the signature interaction, product or menu (ledger or label style), people/story, footer with newsletter and address.
- Responsive from 375px: rotations and overlaps soften on mobile, interactive widgets stay usable by touch and keyboard.
- Accessibility: WCAG AA, visible focus, keyboard support plus aria-live for widgets, alt text that names people and actions.

# SELF-CRITIQUE (run before finishing; fix failures)
- [ ] Could this be swapped onto any other "organic" brand unchanged? If yes, add more brand-specific facts, names and patterns.
- [ ] Which 2–3 levers did I commit to, and where are they visible?
- [ ] Are there real or realistic humans (names, hands, faces or clearly labelled placeholders)?
- [ ] Is every "eco" adjective replaced by a concrete fact?
- [ ] Contrast: body ≥7:1 ideally, all small text ≥4.5:1, nothing small on sage or mid-tones?
- [ ] Handwriting ≤5 uses, ≥20px, non-essential?
- [ ] Grain visible but subtle; motion gentle; reduced-motion respected?
- [ ] Do the signature interaction's keyboard controls work, and does it announce changes?
- [ ] Avoided every DON'T item?
````

## Worked example (filled placeholders)

```
{{BRAND_NAME}}      Hedgerow Mill
{{PURPOSE}}         Website and click-and-collect for a stone mill and bakehouse on a 62-acre regenerative (no-till) farm
{{AUDIENCE}}        Local food lovers, weekend visitors and home bakers buying flour, aged 28–65; farming and food press
{{CONTENT_OR_SITEMAP}} Home (hero, facts, soil-to-slice, farm year, today's bench, people, newsletter), Flour shop, Journal, Visit
{{LOCAL_ASSETS}}    ./brand/hedgerow-logo.svg, ./photos/field/*.jpg, ./photos/bakehouse/*.jpg, ./copy/bake-list.csv, ./copy/farm-calendar.md
{{REFERENCE_URLS}}  https://www.theolly.it, https://www.agrumeafarm.it/en, https://www.wildsouls.gr/en
{{TECH_STACK}}      Single HTML file, vanilla JS, Google Fonts (Fraunces, DM Sans, Caveat)
{{UNIQUE_HOOK}}     Everything follows the farm calendar: a seasonal wheel shows what's in the field, at the mill and on the bench each month.
```

Expected lever picks: **calendar as navigation** (the seasonal wheel), **ledger and stamp language** (today's bench with batch stamp and "keep one" toggles), **named-human marginalia** (notes from Tom and Ada). See `demo.html` for this brief rendered.
