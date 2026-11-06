# CC-3 Tech Product: generation prompt

Copy everything inside the fence, fill the `{{PLACEHOLDERS}}`, and paste into your coding agent.

````markdown
# ROLE
You are a design engineer of the calibre behind Linear, Vercel, Raycast and Resend, and of the studios that win awards in this space (basement.studio: Next.js Conf, Awwwards SOTD 2024; Together: Tailscale, Stytch, Coder). You design in code. You care about 1px borders, easing curves, keyboard paths and real data. Your job is to build a SaaS / developer-tool site that is unmistakably *this* product, not "another Linear clone".

# PROJECT
- Brand: {{BRAND_NAME}}
- Purpose of the site: {{PURPOSE}}
- Audience (role, stack, what they're sceptical about): {{AUDIENCE}}
- Content / sitemap: {{CONTENT_OR_SITEMAP}}
- Local assets you MUST use (logo, product screenshots, copy, brand files, code samples): {{LOCAL_ASSETS}}
- Reference URLs (study, never clone): {{REFERENCE_URLS}}
- Tech stack: {{TECH_STACK}}
- Unique hook (the one idea people will screenshot and share): {{UNIQUE_HOOK}}

# STYLE BRIEF: "Tech Product" (Classical-Cool, expressive light)
A dark (or deliberately light) precision interface where the PRODUCT IS THE HERO. Structure is classical: centred hero, product UI, logos, bento proof, changelog, pricing, CTA, dense footer. Expression comes from LIGHT (glows, lit edges, beams), micro-interaction and one contrasting typographic moment. First impressions form in about 50 ms (Lindgaard et al. 2006) and a polished site implies a polished product (aesthetic-usability effect). But the genre is now so prototypical that it is forgettable (Ginn 2023, "The Linear effect"). Aim for "most advanced, yet acceptable" (Hekkert et al. 2003): familiar shell, one or more genuinely novel, product-specific ideas.

# HARD CONSTRAINTS
Typography
- One neo-grotesk family plus its mono (e.g. Geist + Geist Mono, Inter Tight + JetBrains Mono). PLUS one contrasting display moment: a serif italic word (Instrument Serif, Newsreader), a wide/condensed grotesk, a pixel face or a mono headline.
- Hero 48–88px, weight 500–600, tracking −0.04em, line-height ≈ 1.0; vertical gradient text from white to ~60% white is allowed. Check contrast at the darkest stop.
- Body 15–17px at ≥ 4.5:1; labels in mono 12–13px.

Colour
- A 10–12 step grey ramp on near-black (or warm black `#0B0A08`, or a light theme). Borders `rgba(255,255,255,.06–.16)`.
- ONE brand hue, used as LIGHT: glows behind the product, lit top borders, focus rings, selection, a travelling beam. Never large flat fills.
- **Default hue must NOT be purple/indigo/violet** unless {{BRAND_NAME}} already owns it. Choose from what the product does (amber = heat/build, green = terminal/health, red = speed/alerts, cyan = network/data).
- Status colours (ok/warn/error) are always paired with icons or text.

Layout
- Max width 1120–1200px, visible structure allowed (grid lines, crosshair "+" marks at intersections).
- Hero: version pill (links to changelog) → headline → one-sentence subline → primary CTA + copyable install command → PRODUCT UI below (HTML/CSS, not a PNG if possible), lit from behind, optionally tilted in perspective and flattening on scroll.
- Bento grid (`grid-template-columns: repeat(6,1fr)`, mixed spans): every cell is a working micro-demo that proves ONE claim. No icon + two lines cards.
- A "receipts" area: benchmarks, uptime, changelog with dates and versions.

Motion
- UI 120–250ms, reveals 600–900ms, easing `cubic-bezier(.16,1,.3,1)`. Animate transform/opacity only.
- Pointer-following spotlight on cards and borders (CSS custom properties `--x/--y`).
- A real command palette (⌘K / Ctrl+K and a visible button) that navigates and runs demo actions.
- `prefers-reduced-motion`: stop loops, beams and typing; show final states. Provide a pause control for any loop longer than 5 s (WCAG 2.2.2).

# DO
- Render the product with realistic data: IDs, hashes, timestamps, latencies, names. Make it ALIVE (streaming logs, filtering lists, draining queues).
- Draw the product's own metaphor (queues, packets, branches, edges, tokens) as the art direction.
- Put a copy-to-clipboard install command or code sample with language tabs above the fold.
- Write opinionated, specific copy with numbers. One idea per section.
- Use noise (3–6%) over gradients to prevent banding; `backdrop-filter` only on small areas (nav, palette).
- Make the logo wall monochrome and consistent in visual weight.
- Ship a dense, useful footer: docs, changelog, status, security/SOC 2, legal.

# DON'T (the "AI-generated SaaS look")
- No purple → pink → blue gradient headline words or blurry indigo blobs.
- No three equal feature cards with Lucide icons in rounded squares.
- No "Supercharge / Unlock / Seamless / Revolutionize / AI-powered ✨" copy.
- No generic dashboard screenshot with lorem metrics, no stock 3D shapes unrelated to the product.
- No glassmorphism everywhere; no low-contrast grey body text (#666 on #000 fails).
- No fake logo walls (Acme, Globex) and no "Trusted by 10,000+ teams" without a source.
- No scroll-jacking and no autoplaying heavy video as the only hero.

# UNIQUENESS: pick 2–3 levers and commit (state them in a comment at the top)
1. Own a non-purple light.
2. A contrasting display face (serif italic, wide grotesk, pixel or mono headline).
3. The hero UI works (interactive or live).
4. Domain-specific visual metaphor instead of abstract blobs.
5. Keyboard as navigation: a real ⌘K palette with demo commands (theme switch, run demo, copy install).
6. Show the seams: grid lines, coordinates, build hashes, latency readouts.
7. Bento cells as mini-apps.
8. Point-of-view copy only this company could write.
9. A light mode or warm-black twist.
10. Physicality: keycaps, LEDs, hardware-panel details.

# ASSETS AND REFERENCES
- Use {{LOCAL_ASSETS}} first: logo as inline SVG; real product screenshots only as supporting evidence. Prefer rebuilding the key UI in HTML/CSS for crispness and animation. Reference local paths relatively; never hotlink.
- From {{REFERENCE_URLS}}: list (in a code comment) 3–5 concrete techniques you are borrowing (e.g. "Vercel: crosshair grid", "Resend: serif headline", "Raycast: lit top edge on the palette"), then translate them into this brand's hue, type and metaphor.

# OUTPUT
- {{TECH_STACK}} (if unspecified: a single self-contained `index.html`, inline CSS/JS, Google Fonts allowed, no framework).
- CSS custom properties for the grey ramp, brand light, type, spacing, radii and motion; theme variants via `[data-theme]`.
- Semantic landmarks, skip link, visible focus rings in the brand hue, palette as `role="dialog"` + combobox/listbox with `aria-activedescendant`, Esc to close and focus return.
- Responsive 375 → 1440px: the console/product UI collapses to its essential pane; no horizontal scroll.
- Performance: no layout shift; animations on transform/opacity; no image heavier than 300 KB above the fold.

# SELF-CRITIQUE (fix anything that fails before finishing)
1. Blur test: if you remove the logo, could this be Linear, Vercel or a template? If yes, push the chosen levers harder.
2. Search your code for `#8b5cf6`, `#7c3aed`, `#6366f1`, "purple", "violet", "Supercharge", "seamless". Remove unless justified.
3. Does every bento cell prove something with interaction or real data?
4. Is the product visible and understandable within the first viewport at 1440px AND 375px?
5. Contrast: secondary text ≥ 4.5:1; gradient text at its darkest stop ≥ 3:1 for large text.
6. Keyboard: can you reach and use everything, including the palette, without a mouse?
7. Reduced motion: everything readable and static?
8. Is there at least one detail that would make a design engineer smile (keycap press, lit edge, perfect easing)?
````

---

## Worked example (filled placeholders)

| Placeholder | Example |
|---|---|
| `{{BRAND_NAME}}` | Fernlight |
| `{{PURPOSE}}` | Launch site for an open-source observability tool that traces LLM agent runs; goals: GitHub stars and cloud sign-ups |
| `{{AUDIENCE}}` | Backend and ML engineers at AI startups, tired of black-box agent failures and of dashboards that need a PhD |
| `{{CONTENT_OR_SITEMAP}}` | Home (hero, live trace demo, bento, benchmarks, OSS vs Cloud, changelog), Docs, Pricing, Blog |
| `{{LOCAL_ASSETS}}` | `./brand/fernlight.svg`, `./screens/trace-view@2x.png`, `./copy/home.md`, `./code/quickstart.py`, `./brand/colors.json` (ice cyan #7FE3FF) |
| `{{REFERENCE_URLS}}` | https://vercel.com (visible grid), https://resend.com (serif headline + code tabs), https://raycast.com (lit palette edge), https://evervault.com (domain metaphor) |
| `{{TECH_STACK}}` | Next.js App Router + Tailwind, Geist via `next/font` |
| `{{UNIQUE_HOOK}}` | The hero is a real, scrubbable agent trace: drag a timeline and watch each tool call, token count and cost light up like a fern unfurling |

Chosen levers in that example: Domain metaphor (fern-like trace tree), The hero UI works (scrubbable trace), Own a non-purple light (ice cyan).
