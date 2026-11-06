# CC-2 · Corporate Trust

## 1. One-line definition
Design for organisations that hold other people's money, health or legal risk: calm, precise, evidence-first pages where every visual decision says "we are competent, we are accountable, and we have nothing to hide", without sliding into stock-photo blandness.

---

## 2. Position on the map

| Axis | Score | Justification |
|---|---|---|
| Classical ↔ Expressive | **1.5 / 5** (Classical) | Order, alignment, predictable navigation and conventional page anatomy are the point. Expression is spent in one or two controlled places (a hero visual, a signature chart). |
| Cool ↔ Warm | **2 / 5** (Cool, leaning neutral) | Rational palette and tabular data, but the best current examples (Mercury, Wealthsimple, Runway) add warmth through off-white paper tones, serif accents and human copy. |
| Density | **3 / 5** | Airy heroes, but proof sections (metrics, disclosures, comparison tables) are deliberately dense: density reads as substance. |
| Motion | **2 / 5** | Short, functional transitions (number count-ups, chart draws, accordion reveals). Nothing that delays reading. |
| Ornament | **1.5 / 5** | Hairlines, rules, a single gradient or texture at most. Ornament is replaced by *data* (charts, ledgers, product UI). |
| Contrast | **3.5 / 5** | Strong text contrast and crisp edges; colour contrast is restrained (one accent). |

---

## 3. Best-fit purposes

| Purpose | Fit | Why |
|---|---|---|
| Corporate / institutional | ✅ strong | The native habitat: banks, insurers, law firms, consultancies, public bodies. |
| SaaS (B2B, fintech, regtech, healthtech) | ✅ strong | Buyers are risk-averse committees; credibility beats delight. Overlaps with CC-3 for product-led companies. |
| Nonprofit / foundations | ✅ strong | Donor trust, transparency reports, annual-report pages. |
| Editorial (reports, research, insights hubs) | ➖ possible | Works for McKinsey-style insight pages; pair with CC-1 grids for long reads. |
| E-commerce | ➖ possible | Only for high-ticket or regulated goods (insurance, medical devices, pensions). |
| Agency / studio | ➖ possible | Only for consultancies selling to the same buyers. Too quiet for creative agencies. |
| Event | ➖ possible | Conferences for finance/legal. Otherwise too sober. |
| Portfolio / personal | ❌ avoid | Reads as a CV template unless you are a CFO or lawyer. |

---

## 4. Visual DNA

### Typography
- **The modern default:** a neo-grotesk with tabular figures. Stripe uses **Söhne** (Klim Type Foundry, Kris Sowersby), adopted around its 2020 redesign. Many fintechs use **Suisse Int'l**, **Graphik**, **GT America**, **ABC Diatype** or custom grotesks.
- **The trust accent:** a sober text serif for headings or pull-quotes (Wealthsimple's brand is the best-known fintech example; check current sites before quoting specifics). Serif = "established institution"; grotesk = "modern infrastructure". Mixing them says "modern AND established".
- **Numbers are typography.** Use `font-variant-numeric: tabular-nums lining-nums` everywhere money appears; use superscript cents (Mercury's dashboards show `$5,216,471.18` with smaller cents); right-align columns.
- **Free alternatives (Google Fonts):** Söhne → **Inter Tight**, **Hanken Grotesk**, **Instrument Sans**; Suisse/Graphik → **Schibsted Grotesk**, **Figtree**; serif accent → **Newsreader**, **Source Serif 4**, **Fraunces** (low "soft" axis); figures/code → **IBM Plex Mono**, **JetBrains Mono**.
- **Scale:** modest. Display 48–72px (clamp to ~3.2rem on mobile), tracking −0.02em; body 17–18px, line-height 1.55; small caps or 11–12px uppercase labels with +0.08em tracking for metadata.

### Colour
Logic: **one institutional ink + paper + one signal colour + semantic gain/loss colours.**

| Role | Typical hex | Notes |
|---|---|---|
| Ink (text, dark sections) | `#0A2540` (Stripe's navy), `#10261F` (deep bank green), `#111418` | Never pure black: slightly chromatic ink feels printed. |
| Paper | `#FFFFFF`, `#F6F4EE` (warm), `#F6F9FC` (Stripe's cool grey-white) | Warm paper adds the "annual report" feel. |
| Accent | `#635BFF` (Stripe blurple); Clear Street's saturated electric blue; Mercury's muted indigo on dark UI; Ramp's yellow (hues described from their OG images, not official hex values) | One accent, used for CTAs and data highlights only. |
| Gain / loss | `#0E8A5F` / `#C2412D` | Always paired with +/− signs or arrows (colour-blind safe). |
| Rules | `rgba(ink, .12)` | Hairlines do the work boxes would do elsewhere. |

Blue dominates the category because it maps to *competence* in brand-personality research (Labrecque & Milne 2012). That is exactly why a non-blue ink (green, oxblood, graphite) is the cheapest way to stand out while staying credible.

### Layout and grid
- 12-column grid, max content width 1120–1240px, generous 96–160px section padding.
- **Conventional page anatomy is a feature** (Tuch et al. 2012: prototypical layouts are judged more favourably at first glance): logo left, nav centre/right, primary CTA top-right, hero → logos → product proof → features → numbers → testimonials → security/compliance → CTA → dense footer.
- Comparison tables, pricing tables and "how it works" step sequences are first-class components, not afterthoughts.
- The footer is a trust surface: legal entity name, regulator numbers, banking partner disclosures, addresses (Clear Street prints "member FINRA and SIPC"; Mercury, Ramp and Brex all print their partner-bank disclosures).

### Imagery and art direction
- **Product as proof:** real-looking dashboards with plausible numbers (Mercury's OG image is a full dashboard; Clear Street's is an equity chart). Fake-but-specific beats abstract.
- **Diagrams over photos:** money-flow diagrams, ledger tables, maps of coverage (Clear Street maps its exchange coverage).
- **Photography, if any:** real staff and clients, environmental, warm daylight. Never handshake stock.
- **One signature visual system:** Stripe's animated WebGL mesh gradient (built with a tiny in-house WebGL helper, see bram.us 2021 write-up), Ramp's yellow, Mercury's dusk-blur backdrop.

### Motion and interaction
- Count-up numbers (once, on enter, < 800ms), chart lines drawing left-to-right, tabbed product tours, calculators (savings/yield/fee estimators) that let the visitor generate their own proof.
- Easing: `cubic-bezier(.2,.7,.2,1)`, 200–400ms. No parallax on text, no scroll-jacking.

### Micro-details
- Hairline rules (1px at 12% ink), 6–10px radii (never pill-everything), small "verified" or shield glyphs next to regulated claims, footnote markers (¹ ²) that link to disclosures, timestamps ("Rates as of 3 Nov 2026"), version numbers on legal docs, keyboard-focus rings in the accent colour.

---

## 5. Why it works

**Credibility is judged visually, fast.** In Fogg et al.'s (2003) study of 2,500+ people, "design look" was the most mentioned credibility factor (46.1% of comments). Lindgaard et al. (2006) showed visual appeal judgements form in about 50 ms and stay stable. Robins & Holmes (2008) found the same content was rated more credible with a higher-aesthetic design. Sillence et al. (2004) found people rejected health sites mainly for design reasons (busy layout, ads, poor navigation) before reading the content.

**Beauty that also seems to work.** The aesthetic-usability effect (Kurosu & Kashimura 1995; Tractinsky, Katz & Ikar 2000) means polished interfaces are perceived as easier to use. For a bank, "looks well made" stands in for "is well run".

**Classical aesthetics fit the job.** Lavie & Tractinsky (2004) separate classical aesthetics (clean, clear, symmetrical) from expressive ones. Corporate Trust deliberately maxes the classical dimension, since order and clarity signal control.

**Typicality lowers risk.** Tuch et al. (2012) showed low visual complexity and high prototypicality both raise first-impression ratings. Hekkert et al.'s (2003) "most advanced, yet acceptable" principle explains the sweet spot: familiar structure, one novel signature.

**Disclosure builds trust.** Nielsen Norman Group's four trust factors (Harley 2016) are design quality, upfront disclosure, comprehensive and current content, and connection to the rest of the web. Each maps to a component: polish, visible fees and terms, dated content, external links and logos. Baymard Institute's checkout research shows that about one in five shoppers have abandoned an order because they did not trust the site with card details (18–25% depending on the survey year), and that payment fields which *look* more robust feel safer. Perceived security is a visual problem.

**Social proof and authority** (Cialdini 1984): customer logos, named testimonials with titles, regulator badges and usage numbers ("~3,800 clients" on Clear Street) borrow credibility.

**Colour.** Blue maps to competence (Labrecque & Milne 2012), and green to growth and money in Western finance. Use colour meaning deliberately, then break category convention in one controlled way.

**What juries reward.** Awwwards SOTDs in this space (Clear Street 2024, NexBank 2021, Aston Currency Management 2022, Jeton 2025) all pair a conventional, scannable structure with *one* crafted signature: kinetic type in the hero, a 3D or gradient object, or an unusually good data visual. The Webby win for Runway (Reform Collective, 2024) rewarded human, witty copy in a finance context ("Finance people are people too").

---

## 6. Uniqueness levers
1. **Break the blue.** Deep bank-green, oxblood, graphite or ink-violet as the institutional colour, with paper off-white. Keep blue only for links if at all.
2. **Serif + grotesk + mono triad.** A serif for statements of belief, a grotesk for UI, a mono for figures. Three voices: institution, product, ledger.
3. **Ledger as motif.** Hairline-ruled sections, column headers, running totals and footnote numbers used as the visual language of the whole site.
4. **Proof you can operate.** A calculator, a live rate table, or an interactive statement instead of a static feature list. The visitor generates the evidence.
5. **Disclosure as design.** Turn the regulatory fine print into a designed "receipts" section with custodian, insurer, audit date and SOC 2 report status. Most competitors hide it; you headline it.
6. **Timestamped content.** "Rates as of…", "Last audited…", changelog dates. Currency signals honesty (NN/g's "current content" factor).
7. **One crafted signature visual** (Stripe's gradient, Clear Street's electric blue product panels): a seal, a gradient, a chart style that becomes recognisable.
8. **Human copy.** Runway's Webby-winning tone: plain sentences, a little wit, named humans ("Talk to Priya, our treasury lead").
9. **Real numbers with units and sources**, not "10x faster". Footnote every claim.
10. **A dense, beautiful footer.** Legal entity, regulator IDs, addresses, status page link, set like the colophon of an annual report.

---

## 7. Clichés and pitfalls
- **The generic fintech template:** blue-to-purple gradient blob, Inter at 64px, "The future of finance is here", three icon cards ("Secure · Fast · Simple"), a floating phone mockup with a credit card, a logo wall of the same 8 startups. AI generators default to this because it is the statistical average of the category.
- Handshake, skyscraper, globe-with-network-lines and "diverse team pointing at laptop" stock photos.
- Abstract claims without numbers ("enterprise-grade security") and unexplained badges.
- Glassmorphism and neon glow borrowed from CC-3. It looks speculative, which is the opposite of custodial.
- Over-animation: count-ups that loop, chart animations on every scroll, slow page loads (slowness reads as fragility).
- Dark patterns on pricing (hidden fees, pre-ticked add-ons). They destroy the trust the visuals build.
- Footers with only social icons. Missing legal entity and regulatory info is a red flag to finance buyers.

---

## 8. Accessibility and performance notes
- Text contrast AA minimum (4.5:1). Aim for AAA (7:1) on body copy for financial/health content with older audiences. Light-mode body text has a legibility edge for normal vision (Piepenbrock et al. 2013; Budiu 2020, NN/g).
- Never encode gain/loss by colour alone: add +/−, ▲/▼ and text.
- Tables need real `<table>` markup, `<th scope>`, captions. Charts need a text summary or data table fallback.
- Calculators: labelled inputs, `aria-live="polite"` on results, keyboard-operable sliders.
- Performance is part of trust: LCP < 2.0s, no layout shift on number count-ups (reserve width with tabular figures).
- Honour `prefers-reduced-motion` (show final numbers immediately).
- Legal and disclosure text: at least 13px, 1.5 line-height. Fine print must still be readable.

---

## 9. Neighbouring styles and hybrids
- **+ CC-1 Swiss-Editorial:** research hubs, annual reports, consultancy insight pages (strict grid, big serif headlines, long reads).
- **+ CC-3 Tech-Product:** product-led fintech (Mercury, Ramp, Stripe, Clear Street). Borrow the product-as-hero and bento proof, keep light mode and restraint.
- **+ CW-1 Luxury-Refined:** private banking, wealth management, family offices (more serif, more whitespace, slower motion).
- **+ CW-2 Warm-Organic:** healthcare, insurance, credit unions, impact investing (warmer palette, rounded shapes, real photography).
- **Avoid blending with** EC-2 Brutalist or EW-2 Retro unless the brand is deliberately contrarian (some crypto brands do this on purpose).
