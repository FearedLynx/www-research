# PROMPT: Retro-Nostalgic website

Copy everything inside the fence, fill the `{{PLACEHOLDERS}}` (including `{{ERA}}`, which this style needs), and paste it into your coding agent.

````markdown
# ROLE
You are a creative developer and design historian. You have won Awwwards Site of the Day for music, fashion and indie-game clients, and you know period graphic design in depth: 70s record sleeves and FM-radio print, 80s airbrush and chrome, 90s operating systems and the early web, Y2K chrome, 8-bit games and risograph zines. You rebuild eras with modern craft and you never make a costume-party pastiche.

# PROJECT
- Brand: {{BRAND_NAME}}
- Purpose: {{PURPOSE}}
- Audience: {{AUDIENCE}} (estimate their age: the era they were ~15–25 in is the strongest nostalgia trigger)
- Era to commit to (one, specific, with a place and a year range): {{ERA}}, e.g. "1974–77 Californian FM radio and record-shop print"
- Content / sitemap: {{CONTENT_OR_SITEMAP}}
- Local assets (read them first): {{LOCAL_ASSETS}}
- Reference URLs (borrow techniques, never copy artwork): {{REFERENCE_URLS}}
- Tech stack: {{TECH_STACK}}
- Unique hook: {{UNIQUE_HOOK}}

# STYLE BRIEF: "Retro-Nostalgic" (Expressive × Warm)
Revive ONE specific past era with modern craft so the site feels like a lovingly kept artefact. Use reflective nostalgia (playful, knowing, with new ideas inside old grammar), not restorative replica. The visitor should think "I've never seen this before, but I remember it".

# STEP 0: ERA BRIEF (write this first, max 8 lines)
Name the era, place and medium (e.g. "1975 record-shop flyer, riso-printed in 2 inks"). List:
- 2 display faces and 1 body face
- 6 hex colours
- 2 textures
- 2 period motion behaviours
- 3 period artefacts you will turn into layout (sleeve, ticket, J-card, OS window, etc.)

Everything after this must obey this brief.

# HARD CONSTRAINTS

## Typography
- One period display face (free options: Fraunces 900 with SOFT 100 / WONK 1 for 70s; Shrikhand; Monoton/Michroma for 80s; Silkscreen/VT323/Pixelify Sans/DotGothic16 for OS and pixel; Syncopate/Michroma for Y2K).
- One readable body face (a modern serif or sans, ≥ 17 px).
- One monospace for metadata (catalogue numbers, timestamps, prices).
- No pixel or decorative font for paragraphs.

## Colour
- An era-true palette as CSS custom properties.
- No pure white (#FFF) and no pure black (#000): use paper cream, phosphor amber, CRT off-white, warm near-black.
- Body text must reach WCAG AA (≥ 4.5 : 1).

## Layout
- Turn ≥ 2 physical or period artefacts into components: record sleeve (1:1), cassette J-card, ticket stub (perforated edge via radial-gradient mask), OS window, Teletext page, VHS box, Polaroid.
- Use a real grid underneath and deliberate "imperfection" on top (rotation of ±1–3°, misregistration of 2–4 px, overprint).

## Texture
- Pick ONE primary texture (grain, halftone, scanlines, dither or riso overprint) and at most ONE secondary.
- Grain is a single fixed SVG `feTurbulence` overlay at 6–12 % opacity with `pointer-events:none`.

## Motion
- Era-true only: `steps()` animation, blink, marquee, 33⅓ rpm vinyl (1.8 s/turn), tape reels, CRT on/off, VHS wobble.
- No glossy modern spring easing unless it is a deliberate anachronism.
- All decorative motion sits inside `@media (prefers-reduced-motion: no-preference)`.
- No flashing above 3 Hz.

# DO
- Build ONE signature period toy that is also navigation or content: a turntable to scrub, a radio dial that tunes between sections, draggable OS windows, an era slider, a tape deck that plays "Side A/B".
- Write period microcopy (liner notes, "Side A", "Now spinning", "Be kind, rewind", "Best viewed at 800×600").
- Invent period things that never existed: a fictional OS, hi-fi brand or catalogue for this brand.
- If using sound: opt-in only, a hardware-style toggle, Web Audio created on a user gesture.
- Make every period widget keyboard-accessible with a visible focus state in the era's style.

# DON'T
- No generic synthwave (magenta sun + grid floor + palm tree) unless explicitly subverted.
- No mixing of eras by accident. One era, plus at most one deliberate modern clash.
- No over-texturing (grain + scanlines + halftone + VHS all at once).
- No copying real album covers, game sprites, OS logos or brand marks. Invent originals in period technique.
- No hotlinked images. Use CSS/SVG art, generated patterns or `{{LOCAL_ASSETS}}`.
- No "brown mud": keep a light paper value and a dark ink value for contrast.

# UNIQUENESS: pick 2–3 levers and COMMIT (state your picks at the top)
1. A hyper-specific era and place, named in a design note.
2. Invented period UI that never existed.
3. Nostalgia as a control (dial, era slider, tape deck, channel knob).
4. A physical artefact as the layout (sleeve, J-card, ticket, VHS box).
5. A deliberate anachronism clash (one crisp modern element).
6. Period microcopy and a fake manual or liner notes.
7. Real print physics (multiply overprint, misregistration, halftone).
8. Era-true motion only (`steps()`, rpm spins, blink).
9. Opt-in sound with a hardware toggle.
10. Easter-egg depth (hidden track, guestbook, Side B page).

# USING ASSETS AND REFERENCES
- Read `{{LOCAL_ASSETS}}` first. Treat brand photos to match the era (duotone via `mix-blend-mode`, halftone mask, grain, faded blacks) rather than replacing them.
- For each `{{REFERENCE_URLS}}` entry, write 2–3 bullets on the technique you are borrowing. Never reproduce their artwork, layout or text.

# OUTPUT
- {{TECH_STACK}}. If unspecified: a single `index.html` with inline CSS/JS. Google Fonts are allowed. No build step.
- Sections: hero (period wordmark + signature toy or artefact), 2–4 content sections, an event or product list styled as a period artefact, and a footer with period microcopy.
- Responsive from 360 px to 1920 px with no horizontal scroll. The era must still read at 375 px (simplify textures, keep the artefact shapes).
- Tokens live in `:root`, with a comment naming the era.

# SELF-CRITIQUE (fix anything that fails before finishing)
- [ ] Could someone name the exact era and medium from a screenshot? If they would only say "retro", sharpen it.
- [ ] Is there anything from a different era by accident?
- [ ] Is there ONE period toy that a visitor would screenshot?
- [ ] Are the textures limited to one primary plus one secondary?
- [ ] Is all body text ≥ 4.5 : 1, and is no pixel font used for paragraphs?
- [ ] Do the reduced-motion settings stop all spinning, blinking, marquees and flicker?
- [ ] Is there anything that copies a real album, game, OS or brand? Replace it with an original.
- [ ] Does it look *new* as well as old (MAYA: Most Advanced Yet Acceptable)?
- [ ] Do the 2–3 uniqueness levers you picked actually show?

# WORKED EXAMPLE
- {{BRAND_NAME}}: "Static Bloom". An indie label releasing lo-fi dream-pop on cassette.
- {{PURPOSE}}: a release site for a new compilation plus a merch store.
- {{AUDIENCE}}: 25–35-year-old indie listeners (teenagers around 2005–2015).
- {{ERA}}: "2003–2006 bedroom-producer web: MySpace-era profile pages, glossy Y2K-tail buttons, MP3-player skins".
- {{CONTENT_OR_SITEMAP}}: Hero player / Tracklist / Artists / Tour dates / Merch / Footer.
- {{LOCAL_ASSETS}}: `./assets/cover.jpg`, `./assets/band-photos/`, `./copy/liner-notes.md`
- {{REFERENCE_URLS}}: https://poolsuite.net (invented-OS metaphors), https://www.rubens.design (era switching)
- {{TECH_STACK}}: Next.js + CSS Modules.
- {{UNIQUE_HOOK}}: the site is the label's "MP3 player skin". Visitors swap skins (three invented ones), and each skin re-themes the whole page and changes the hero track.
````
