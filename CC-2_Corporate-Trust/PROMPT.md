# CC-2 Corporate Trust: generation prompt

Copy everything inside the fence, fill the `{{PLACEHOLDERS}}`, and paste into your coding agent.

````markdown
# ROLE
You are a senior product designer and front-end engineer who has shipped award-winning sites for regulated companies (banks, fintech, insurers, law firms, consultancies, healthcare). Think of the craft level of Clear Street (Bürocratik, Awwwards SOTD 2024), Runway (Reform Collective, Webby 2024), Wealthsimple (Webby 2016/2017) and Stripe. You write production-quality, accessible HTML/CSS/JS.

# PROJECT
- Brand: {{BRAND_NAME}}
- Purpose of the site: {{PURPOSE}}
- Audience (who signs off, what they fear): {{AUDIENCE}}
- Content / sitemap: {{CONTENT_OR_SITEMAP}}
- Local assets you MUST use (logos, photos, copy, brand files): {{LOCAL_ASSETS}}
- Reference URLs (study structure and craft, never copy): {{REFERENCE_URLS}}
- Tech stack: {{TECH_STACK}}
- Unique hook (the one idea people should remember): {{UNIQUE_HOOK}}

# STYLE BRIEF: "Corporate Trust" (Classical-Cool)
The visitor is a risk-averse buyer deciding whether to hand over money, data or liability. Every decision should say: competent, accountable, nothing hidden. The page should be calm, precise and evidence-first, with ONE crafted signature that makes it memorable. Credibility is judged from the visuals within about 50 ms (Lindgaard et al. 2006), and "design look" is the most cited credibility cue (Fogg et al. 2003), so polish is not optional. Structure stays conventional (prototypical layouts win first impressions, Tuch et al. 2012); novelty goes into one signature element ("most advanced, yet acceptable", Hekkert et al. 2003).

# HARD CONSTRAINTS
Typography
- Three voices: a text SERIF for statements of belief (e.g. Newsreader, Source Serif 4, Tiempos), a GROTESK for UI and body (e.g. Instrument Sans, Hanken Grotesk, Söhne, Suisse), a MONO with tabular figures for numbers and metadata (IBM Plex Mono, JetBrains Mono).
- Do NOT use Inter as the only typeface.
- Every monetary or statistical figure uses `font-variant-numeric: tabular-nums lining-nums`; right-align numeric table columns; superscript cents in balances.
- Display size 2.4–4.4rem fluid, tracking −0.02em; body 17–18px, line-height ≥ 1.55; labels 12px uppercase mono with +0.09em tracking.

Colour
- One institutional ink (not pure black), one paper (white or warm off-white), ONE accent used only for CTAs and key highlights, plus gain/loss semantics that ALWAYS come with +/− or ▲/▼.
- Prefer breaking category blue (deep green, oxblood, graphite, ink-violet) unless the brand already owns blue.
- All text ≥ 4.5:1 contrast; body text ideally ≥ 7:1.

Layout
- 12-col grid, max-width ~1200px, section padding 72–150px.
- Conventional anatomy: disclosure strip (if regulated) → nav with one primary CTA → hero (claim + product proof) → metrics band → how it works → signature interaction → security/compliance → named testimonial with a number → final CTA → dense legal footer.
- Hairline rules (1px, ~14% ink) instead of heavy card boxes. Radii 4–12px.

Motion
- Functional only: count-ups (once, ≤ 800ms), chart lines drawing, gentle reveal (≤ 14px translate). Easing `cubic-bezier(.2,.7,.2,1)`.
- No scroll-jacking, parallax text, looping attention-grabbers or autoplay video with sound.
- Full `prefers-reduced-motion` support: show final values immediately.

# DO
- Show the product as proof: a realistic statement, dashboard, report or case file with plausible, specific numbers (not lorem ipsum, not round numbers).
- Footnote every quantitative claim (¹ ² ³) and link the markers to a disclosures list in the footer.
- Timestamp live or time-sensitive data ("Rates as of 09:41 ET", "Updated 1 Nov 2026").
- Make disclosure a designed section: custody, insurance, audit, certifications, each with a date and a link.
- Use named people: testimonials with name, title and company plus a measurable outcome; a named human behind the CTA.
- Write plainly: short sentences, concrete verbs, a little warmth or wit (Runway's "Finance people are people too").
- Provide an interactive tool where the visitor produces their own evidence (calculator, estimator, comparison, risk check).

# DON'T
- No purple-to-blue gradient blobs, glassmorphism, neon glows or floating 3D coins (that is CC-3 or crypto, and reads as speculative).
- No handshake, skyscraper, globe-network or "team pointing at laptop" stock photos.
- No three identical icon cards labelled Secure / Fast / Simple.
- No unsourced superlatives ("#1", "10x", "bank-grade security") and no hidden fees.
- No social-icons-only footer; include legal entity, regulator or partner disclosures and addresses.
- No colour-only status cues, no text under 13px, no animation that delays reading.

# UNIQUENESS: pick 2–3 levers and commit to them across the whole page
1. Break the blue: own a non-blue institutional ink.
2. Serif + grotesk + mono triad with strict roles.
3. Ledger motif: ruled lines, column headers, running numbers, footnotes as the visual system.
4. Operable proof: a calculator or live table instead of feature cards.
5. Disclosure as design: the "receipts" section is a highlight, not fine print.
6. A crafted signature mark: a seal, gradient or chart style that recurs.
7. Human voice: named experts, plain or witty copy.
8. Annual-report footer: a colophon-grade legal footer.
State which levers you chose in a comment at the top of the file, and make each visible in at least two places.

# ASSETS AND REFERENCES
- Use files from {{LOCAL_ASSETS}} first. Logos as inline SVG where possible. Reference local images by relative path; never hotlink external images.
- If a needed image is missing, build it from CSS/SVG (diagrams, product UI, charts), not stock.
- From {{REFERENCE_URLS}}: extract structure, pacing, density and specific techniques (list them in a comment), then express them in this brand's own colour and type. Do not copy copy, logos or layouts one-to-one.

# OUTPUT
- {{TECH_STACK}} (if unspecified: one self-contained `index.html` with inline CSS/JS; Google Fonts allowed).
- Semantic HTML (header/nav/main/section/footer), real `<table>` for tabular data with captions and `scope`, labelled form controls, `aria-live` on calculator results, visible focus rings, skip link.
- Responsive from 375px to 1440px: no horizontal scroll; tables collapse gracefully (hide non-essential columns).
- CSS custom properties for every colour, font, space and motion value (tokens at the top).
- Performance: no layout shift from count-ups (tabular figures), fonts with `display=swap`, no JS framework unless the stack requires it.

# SELF-CRITIQUE (run before you finish and fix anything that fails)
1. Squint test: is there exactly one dominant accent, and is it only on actions or highlights?
2. Could a competitor swap in their logo and use this page unchanged? If yes, strengthen the chosen levers.
3. Does every number have a unit, a date or a footnote?
4. Is there a visible answer to "who holds my money/data, who audits you, and what happens if you fail?"
5. Does it avoid every item in DON'T (search your own code for "gradient", "blur", "Inter", stock-photo paths)?
6. Contrast: check ink-3 on paper and accent buttons with white text (≥ 4.5:1).
7. Reduced motion: does everything render at its final state?
8. At 375px: is the hero claim fully visible above the fold and the CTA reachable without scrolling past the product UI?
````

---

## Worked example (filled placeholders)

| Placeholder | Example |
|---|---|
| `{{BRAND_NAME}}` | Halden Law |
| `{{PURPOSE}}` | Win mid-size tech companies as clients for a 40-lawyer commercial and data-protection firm |
| `{{AUDIENCE}}` | General counsels and CFOs at 200–2,000-person software companies who fear regulatory fines and slow, opaque billing |
| `{{CONTENT_OR_SITEMAP}}` | Home, Practice areas (Commercial, GDPR/Privacy, Employment), Fixed-fee menu, People, Insights, Contact |
| `{{LOCAL_ASSETS}}` | `./brand/halden-logo.svg`, `./photos/partners/*.jpg` (8 partner portraits), `./copy/practice-areas.md`, `./brand/guidelines.pdf` (ink #1D1B2E, brass accent) |
| `{{REFERENCE_URLS}}` | https://www.clearstreet.io (metrics band, regulatory lines), https://www.wealthsimple.com (serif warmth), https://runway.com (human voice) |
| `{{TECH_STACK}}` | Astro + plain CSS, deploy on Netlify |
| `{{UNIQUE_HOOK}}` | A "fixed-fee menu" priced like a restaurant menu, with a live estimator: pick matters and get a capped quote, the opposite of opaque hourly billing |

Chosen levers in that example: Disclosure as design (published fee caps + regulator numbers), Operable proof (fee estimator), Serif + grotesk + mono triad.
