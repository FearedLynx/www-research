# CC-3 · Tech Product

## 1. One-line definition
The visual language of modern SaaS and developer tools: dark, precise interfaces where **the product itself is the hero**, lit by soft gradient glows, organised in bento grids and command-palette chrome, and written for people who read changelogs.

---

## 2. Position on the map

| Axis | Score | Justification |
|---|---|---|
| Classical ↔ Expressive | **2.5 / 5** | Classical bones (grids, alignment, restraint, one typeface family) with expressive light: glows, gradient text, 3D objects, micro-interactions. |
| Cool ↔ Warm | **1.5 / 5** (Cool) | Near-black surfaces, monochrome greys, mono type, technical vocabulary. Warmth comes only from an accent hue or playful details (Raycast's red, Arc's colour). |
| Density | **3.5 / 5** | Heroes are airy, but bento sections, changelogs, code blocks and logo walls are information-dense on purpose. |
| Motion | **3.5 / 5** | Hover spotlights, animated borders, typing terminals, scroll-triggered UI demos. Fast and crisp (150–400ms), rarely cinematic. |
| Ornament | **2.5 / 5** | Ornament is *light*: glows, noise, grid lines, beams, 1px gradient borders. No illustration in the classic sense. |
| Contrast | **4 / 5** | White on near-black, with sharp hierarchy built from a 10-step grey ramp. |

---

## 3. Best-fit purposes

| Purpose | Fit | Why |
|---|---|---|
| SaaS / developer tools / AI products | ✅ strong | The home turf: Linear, Vercel, Raycast, Resend, Supabase, Cursor, Clerk, Warp. |
| Event (tech conferences, launch weeks) | ✅ strong | Next.js Conf (Awwwards SOTD 2024) and Vercel Ship (HM 2024) show it scales to event microsites. |
| Portfolio (design engineers, product designers) | ✅ strong | Rauno Freiberg, Emil Kowalski and Paco Coursey's sites are canonical; craft in micro-interactions is the CV. |
| Agency (product / dev studios) | ➖ possible | basement.studio does it with more 3D and attitude. Pure Linear-style reads as "a SaaS", not "a studio". |
| Corporate / fintech | ➖ possible | Product-led fintech borrows the product-as-hero (Mercury, Clear Street) but should stay lighter and calmer (see CC-2). |
| E-commerce | ➖ possible | Only for hardware and gadgets (Daylight Computer by basement, SOTD 2024; Teenage Engineering-style). |
| Editorial | ❌ avoid | Dark, small, grey text is poor for long reading (positive polarity is easier to read: Piepenbrock et al. 2013; Budiu 2020). |
| Nonprofit / healthcare / hospitality | ❌ avoid | Reads cold, technical and "startup"; erodes warmth and inclusivity. |

---

## 4. Visual DNA

### Typography
- **One neo-grotesk family plus its mono.** Linear has used Inter (with display optical sizes); Vercel uses **Geist / Geist Mono** (designed by Vercel with basement.studio and Andrés Briganti, inspired by Swiss typography, free and open source); Raycast uses Inter; Stripe uses Söhne.
- **The escape hatch is a contrasting display face.** Resend sets "Email for Developers" in a high-contrast *serif* with a silver gradient (see `images/resend_og.jpg`), instantly distinct from every grotesk SaaS. Other options: a wide grotesk (Cursor's wide caps logo), a pixel or bitmap face (Geist Pixel), or a variable mono for headlines.
- **Display:** 48–80px, weight 500–600 (not 800), tracking −0.03 to −0.045em, line-height 1.0–1.08. Gradient text running top-to-bottom from white to about 60% white (Raycast's "Your shortcut to everything.", Linear's headlines).
- **Body:** 15–16px at 60–70% white; labels in mono, 12–13px, sometimes uppercase.
- **Google Fonts:** **Geist**, **Geist Mono**, **Inter Tight**, **Manrope**, **JetBrains Mono**, **IBM Plex Mono**, **Space Grotesk** (overused), **Instrument Serif** or **Newsreader** for a serif twist, **Bricolage Grotesque** for a quirkier display.

### Colour
Logic: **a 10–12 step grey ramp on near-black + ONE brand hue used as light, not paint.**

| Role | Typical hex |
|---|---|
| Background | `#08090A` (Linear-like), `#000` (Vercel), `#0A0A0A`, warm black `#0B0A08` |
| Surface 1 / 2 | `#111214`, `#17181B`, with 1px borders at `rgba(255,255,255,.06–.10)` |
| Text primary / secondary / tertiary | `#F7F8F8`, `#B4B8BF` (≈ 9:1), `#8A8F98` (≈ 5.6:1) |
| Brand light | Raycast red `#FF6363`-ish, Supabase green `#3ECF8E`, Linear's indigo `#5E6AD2`, Vercel pure white |
| Glows | the brand hue at 10–30% alpha in large blurred radial gradients |

The hue appears as a *light source*: glow behind the product screenshot, a lit top border, a beam travelling along a line, the focus ring. Raycast's OG image is a masterclass: red diagonal light shafts and a red-lit window edge on black.

### Layout and grid
- Centred hero (headline, subline, two CTAs) then a **large product screenshot or live UI** (often tilted in 3D perspective, cropped by the fold, lit from behind).
- **Logo wall** directly under the hero (monochrome, 40–60% opacity).
- **Bento grid**: 2–4 column CSS grid with mixed spans (`grid-auto-flow: dense`), each cell containing a *working micro-demo* rather than an icon. Popularised by Apple's keynote slides and adopted across SaaS from around 2023.
- **Visible structure:** Vercel draws its grid lines and puts "+" crosshairs at intersections. Linear uses fine section dividers with fading ends.
- Changelog / "what's new" strip, a docs or code block, a pricing table, a big final CTA with glow, and a dense multi-column footer.

### Imagery and art direction
- **Product UI as hero**, rendered in HTML/CSS where possible (crisper, smaller, animatable), with real-looking data such as issue IDs (ENG-2381), commit hashes, latency numbers.
- Abstract 3D objects lit from behind (Vercel's backlit black triangle, Resend's dark 3D renders), grain/noise overlays to stop banding in gradients.
- Code as imagery: syntax-highlighted samples with language tabs (Resend's OG card).
- Keyboard keycaps (⌘ K), command palettes and terminal windows as recurring motifs.

### Motion and interaction
- **Spotlight hover:** a radial gradient follows the cursor inside cards and borders (`--x/--y` custom properties).
- **Animated gradient borders / beams:** conic-gradient borders that rotate, or light beams travelling along SVG paths.
- **Typed terminals and live demos:** the hero UI actually *does* something (a palette filters, a deploy log scrolls, a queue drains).
- **Keyboard-first:** ⌘K opens a real command palette (cmdk by Paco Coursey is the open-source reference).
- **Timing:** 120–250ms for UI, 400–800ms for reveals, `cubic-bezier(.16,1,.3,1)` (expo-out). Rauno Freiberg's essay *Invisible Details of Interaction Design* (2023) is the canonical text on this level of craft.

### Micro-details
- 1px borders with a lighter top edge (simulated top light): `box-shadow: inset 0 1px 0 rgba(255,255,255,.06)`.
- Radii: 8–12px for cards, 6px for buttons, 999px for pills and badges.
- Noise texture at 3–6% opacity over gradients; `backdrop-filter: blur()` navbars.
- `kbd` styling, status dots ("All systems normal"), version tags (v2.4), "New" pills linking to the changelog.
- Selection colour, scrollbar and caret tinted with the brand hue.

---

## 5. Why it works

**Showing beats telling.** The product UI as hero makes the abstract concrete at first glance. First impressions form in about 50 ms (Lindgaard et al. 2006) and depend heavily on visual appeal and low complexity (Tuch et al. 2012). A crisp, recognisable UI is both appealing and *informative*.

**The aesthetic-usability halo.** Visitors infer that a polished marketing site means a polished product (Kurosu & Kashimura 1995; Tractinsky et al. 2000). For tools that people use eight hours a day, that inference is the sale.

**In-group signalling.** Dark mode, mono type, keyboard shortcuts and code samples are the native environment of developers. Matching it creates processing fluency (Reber, Schwarz & Winkielman 2004) and an "built by people like us" signal. Linear's CEO Karri Saarinen has described brand and website craft as a deliberate competitive moat in talks with Y Combinator.

**Prototypicality, double-edged.** The style is now so typical of the category (Daryl Ginn, *The Linear effect*, 2023: "Dark… subtle blurred background gradients… animated glowing artefacts"; "can you tell they are 4 different websites? I'm not sure I can") that it scores as safe and familiar (Tuch et al. 2012) but forgettable. Hekkert et al. (2003) predict that the winners are "most advanced, yet acceptable": the familiar dark shell plus one genuinely novel element.

**Clear sequencing.** Schwarz (LogRocket, 2025) describes "linear design" as straightforward, sequential layouts that reduce cognitive load with one direction of travel and few competing CTAs (Hick's law in practice).

**What juries reward.** Recent Awwwards winners in this space (Next.js Conf 2024 SOTD; Vercel Ship, Trunk, Tailscale, Stytch, Coder and VoidZero Honorable Mentions) earn credit for *craft in the details*: performant WebGL or 3D used sparingly, perfect type, interactive demos and a strong single art-direction idea, not for the generic glow.

---

## 6. Uniqueness levers
1. **Own a non-purple light.** Pick a hue nobody in your niche uses (sodium amber, phosphor green, signal red, ice cyan) and use it *only* as light.
2. **A contrasting display face.** A serif (Resend), a wide or condensed grotesk, a pixel face or a mono headline. Break the Inter monoculture in one place.
3. **The hero UI works.** Make the product demo interactive or alive (palette filters, queue drains, logs stream). Not a PNG.
4. **A domain-specific visual metaphor.** Draw the thing your product manipulates (queues, packets, edges, tokens, branches) as the art direction, not abstract blobs.
5. **Keyboard as navigation.** A real ⌘K palette that jumps to sections, toggles themes and runs demo commands.
6. **Show the seams.** Visible grid lines, coordinates, version numbers, build hashes and latency readouts make the site feel like an instrument (Vercel's crosshair grid).
7. **Bento cells with mini-apps.** Each tile proves one claim with a working micro-interaction or real data, never an icon and two lines.
8. **Copy with a point of view.** Opinionated, specific and slightly funny (Linear's "Linear Method", Raycast's "Your shortcut to everything"). Ban "supercharge", "seamless", "unlock".
9. **A light mode or warm-black twist.** Warm black (`#0B0A08`), paper-white docs sections or a full light theme (Ginn reports Linear's co-founder joking about moving to light mode in 2023).
10. **Physicality.** Keycaps, LED dots, CRT scanlines or hardware-panel details give tactility to a cold category.

---

## 7. Clichés and pitfalls: the "AI-generated SaaS look"
The generic version that LLMs produce by default (because it is the statistical centre of thousands of templates):
- Inter everywhere, 72px bold headline ("Supercharge your workflow with AI"), a gradient text word in **purple → pink → blue**.
- A purple/indigo radial blob behind the hero, plus glassmorphism cards with `backdrop-filter: blur(20px)`.
- **Three feature cards** in a row, each with a Lucide icon in a rounded square, a two-word title and one sentence.
- Fake logo wall (Acme, Globex), "Trusted by 10,000+ teams", a 3-tier pricing table with "Most popular" on the middle card, and an FAQ accordion.
- A dashboard screenshot with lorem metrics, or worse, a generic illustration where the product should be.
- Sparkle emoji ✨ for "AI", a "Get started for free" CTA twice side by side.

**Why it reads as generic:** every element is prototypical *and* nothing is specific to the product. The fix is specificity: real UI, real data, the product's own metaphor, a non-default hue and typeface, and copy only this company could write.

Other pitfalls: low-contrast grey-on-black body text (fails WCAG), glows that band without noise, 6MB hero videos, scroll-jacked "storytelling" that hides pricing, and dark mode forced on long docs.

---

## 8. Accessibility and performance notes
- Grey ramps on black fail easily: secondary text ≥ 4.5:1 (`#8A8F98` on `#08090A` ≈ 5.9:1 is the floor; `#6B6F76` fails). Check gradient text at its *darkest* stop.
- Provide a light theme or respect `prefers-color-scheme` for docs and long reading (Budiu 2020).
- Glows and blurs are GPU-expensive: prefer static radial gradients plus a noise PNG/SVG over animated `filter: blur()` on large layers; animate `transform`/`opacity` only.
- Interactive product demos need keyboard access, `aria-live` for streaming logs (polite, throttled), and pause controls for anything that moves longer than 5 seconds (WCAG 2.2.2).
- Command palette: `role="dialog"` with `aria-modal`, a combobox/listbox pattern, focus trap, Esc to close, and a visible button alternative to ⌘K.
- `prefers-reduced-motion`: stop beams, rotating borders and auto-typing; show the final state.
- Render product UI in HTML/SVG rather than huge PNGs (sharper, lighter, translatable, selectable).

---

## 9. Neighbouring styles and hybrids
- **+ CC-2 Corporate Trust:** fintech and security products (Clear Street, Mercury, Evervault, Stytch). Keep product-as-hero, lighten the palette, add disclosures.
- **+ CC-1 Swiss-Editorial:** Vercel's visible grid, Geist's Swiss roots, docs sites and changelogs set like editorial pages.
- **+ EC-1 Immersive-Experimental:** launch weeks and conference sites (Next.js Conf, Vercel Ship by basement.studio) push WebGL and 3D further.
- **+ EW-2 Retro-Nostalgic:** terminal, CRT, pixel-font and early-Mac twists (Geist Pixel; many AI devtools' ASCII art) are the fastest route out of the generic look.
- **+ EW-1 Playful:** Arc browser and Raycast's playful extension store show where warmth and colour can enter.
