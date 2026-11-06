# PROMPT: Playful-Illustrative website

Copy everything inside the fence, fill the `{{PLACEHOLDERS}}`, and paste it into your coding agent.

````markdown
# ROLE
You are a senior creative developer and character designer who has shipped Awwwards Site-of-the-Day work for consumer brands. You draw with code: inline SVG characters, CSS springs, and tiny physics toys. You care about craft details (line weight, easing curves, the timing of a blink) and about accessibility.

# PROJECT
- Brand: {{BRAND_NAME}}
- Purpose: {{PURPOSE}}
- Audience: {{AUDIENCE}}
- Content / sitemap: {{CONTENT_OR_SITEMAP}}
- Local assets (use these first; read them before designing): {{LOCAL_ASSETS}}
- Reference URLs (study the techniques, never copy characters or layouts): {{REFERENCE_URLS}}
- Tech stack: {{TECH_STACK}}
- Unique hook (the ONE idea a visitor should remember): {{UNIQUE_HOOK}}

# STYLE BRIEF: "Playful-Illustrative" (Expressive × Warm)
The brand is a character. Custom illustration and a mascot carry the identity. The colour is saturated, the type is chunky and soft, and sticker and collage elements sit on a warm paper ground. Motion is springy, and interactions feel like poking a friendly toy. Under the fun there is a clean, calm, highly usable UI layer.

# HARD CONSTRAINTS

## Typography
- Display: ONE chunky, soft-cornered face (e.g. Bagel Fat One, Chango, Grandstander 900, Bricolage Grotesque 800 at a condensed width, or the brand's own). Set it with `clamp(3.5rem, 11vw, 10rem)`, line-height 0.85–0.95, letter-spacing -0.02em.
- Body/UI: ONE friendly sans (Figtree, Bricolage Grotesque, DM Sans) at 17–19 px, line-height 1.55.
- Optional hand/annotation voice (Shantell Sans, Gochi Hand), only for arrows, notes and tags.
- Maximum 3 families. Do NOT default to Fredoka + Poppins.

## Colour
- 4–6 saturated hues + ONE dark "ink" that is NOT #000 (e.g. aubergine #2A1740, navy #1B1F4B, chocolate #3A1F12) + a warm paper background (not #FFF).
- ALL outlines and ALL body text use the ink colour.
- Never put white text on yellow, coral, mint or pink. Use ink.
- Define everything as CSS custom properties.

## Layout
- A 12-column grid underneath, but illustrations must break it: overlap section edges, peek from behind cards, straddle dividers.
- At least one shaped container (arch, blob, ticket, or wavy SVG divider).
- Stickers and badges are absolutely positioned at small rotations (-8° to 8°) with hard offset shadows (`4px 6px 0 var(--ink)`).

## Mascot
- Design an ORIGINAL mascot as inline SVG built on baby-schema proportions: a head ≥ 50 % of total height, big low-set eyes, a small mouth, a round silhouette.
- Give it at least 3 expressions (idle, happy, surprised/sleepy) as swappable SVG groups.
- It must NOT resemble any existing brand character (no owls in green, chimps, blob monks, famous cats, or game characters).
- Use the mascot in ≥ 3 places: hero, an interaction, and the footer, 404 page or empty state.

## Motion
- Spring easing: `cubic-bezier(.34,1.56,.64,1)` or a CSS `linear()` spring. 350–600 ms for UI.
- Idle loop: the mascot blinks at random 3–6 s intervals and breathes subtly. Its eyes or pupils follow the pointer.
- Press feedback: squash and stretch (`scale(1.12,.88)` → rebound) and 3D button lips that collapse on `:active`.
- Everything decorative is wrapped in `@media (prefers-reduced-motion: no-preference)`, and the page still works with no motion at all.

# DO
- Build one signature toy: drag, squish, feed, dress up or recolour something, and make it explain the product.
- Add a looping marquee slogan or a frame (with a pause control).
- Use a consistent line language: either uniform 3 px ink outlines with flat fills, OR un-outlined grain-gradient shapes. Not both.
- Write copy with the brand's voice: short, cheeky, warm. Microcopy on buttons ("Yes please!", "Feed me").
- Reward moments: a sticker or confetti burst on the primary conversion, plus a mascot reaction.
- Give drag toys keyboard equivalents.

# DON'T
- No Corporate-Memphis people (flat purple humans with giant limbs).
- No generic 3D emoji blobs, stock illustration packs or Spline-clay filler.
- No rainbow gradients on everything. No confetti on every click.
- No blurred, soft "material" shadows. Use hard offsets or none.
- No pure-black outlines and no pure-white backgrounds.
- No hotlinked images. Use inline SVG, CSS art or `{{LOCAL_ASSETS}}`.
- Do not recreate any existing brand's mascot, palette-plus-character combination, or game look.

# UNIQUENESS: pick 2–3 levers and COMMIT (state your picks at the top of your answer)
1. A display-type quirk derived from the mascot's anatomy.
2. The brand promise as a toy (an interaction that demonstrates the product).
3. A non-black ink colour for all line work.
4. Shaped viewport windows (arch, blob, ticket) instead of rectangles.
5. A marquee frame around the hero or the whole page.
6. One rule-breaking scale moment (a giant mascot peeking from the fold, a wordmark bleeding off-screen).
7. The mascot as system UI (loader, 404 page, errors, empty states).
8. A context-aware mascot (time of day, idle → sleep, scroll speed → dizzy).
9. Collectable stickers for exploring.
10. Opt-in sound (squeaks, pops), muted by default.

# USING ASSETS AND REFERENCES
- Read every file in `{{LOCAL_ASSETS}}` first. Extract the logo colours, existing characters and copy tone. If the brand already has a mascot, use it and do not invent a new one.
- For `{{REFERENCE_URLS}}`: write 3 bullets per reference on the TECHNIQUE you are borrowing (e.g. "outlined wordmark with offset ghost layer"). Never copy their characters, illustrations or text.
- If no assets exist, generate everything as inline SVG and CSS.

# OUTPUT
- {{TECH_STACK}}. If unspecified: a single `index.html` with inline CSS/JS. Google Fonts are allowed. No build step.
- Sections: hero (mascot + wordmark + primary CTA), 2–4 content sections from the sitemap, the signature toy, and a footer with a mascot cameo.
- Responsive from 360 px to 1920 px. At 375 px the mascot stays visible and nothing overflows horizontally.
- Accessible: semantic landmarks, focus-visible styles (a chunky ink outline), alt or aria for SVGs, and AA contrast.
- Put the design tokens in `:root` at the top of the CSS.

# SELF-CRITIQUE (run before you finish and fix anything that fails)
- [ ] Could this mascot be mistaken for a famous existing character? If yes, redesign the silhouette.
- [ ] Does the mascot appear in ≥ 3 places with ≥ 3 expressions?
- [ ] Is every outline and all text the ink colour (not #000)? Is the background warm (not #FFF)?
- [ ] Is there ONE toy-like interaction that a visitor would screenshot or show a friend?
- [ ] Is the illustration line language consistent across all art?
- [ ] White text on a light saturated colour anywhere? Fix it.
- [ ] With `prefers-reduced-motion: reduce`, does everything still work without bouncing?
- [ ] At 375 px: no horizontal scroll, the CTA is visible above the fold, and the tap targets are ≥ 44 px.
- [ ] Is anything left that looks like a template (a generic 3-card feature row with icons)? Replace it with something shaped or illustrated.
- [ ] Do the 2–3 uniqueness levers you picked actually show?

# WORKED EXAMPLE
- {{BRAND_NAME}}: "Tumbleweed". A pocket-money app that lets kids aged 8–12 save toward goals.
- {{PURPOSE}}: a marketing site to get parents to download the app.
- {{AUDIENCE}}: parents aged 30–45 (decision makers) and kids (the delight factor).
- {{CONTENT_OR_SITEMAP}}: Hero / How it works (3 steps) / Goals jar toy / Safety for parents / Pricing / FAQ / Footer.
- {{LOCAL_ASSETS}}: `./brand/logo.svg`, `./brand/palette.json`, `./copy/home.md`
- {{REFERENCE_URLS}}: https://www.fruitful.com/ (calm fintech illustration), https://crumbskees.com/ (marquee frame, outlined wordmark)
- {{TECH_STACK}}: Astro + vanilla CSS, no UI kit.
- {{UNIQUE_HOOK}}: the mascot is a round tumbleweed that grows fluffier as you drag coins into its goal jar. Drop enough coins and it rolls across the page doing a victory lap.
````
