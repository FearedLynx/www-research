# EC-1 · Immersive / Experimental

> **One-line definition.** The browser used as a real-time stage: WebGL/WebGPU scenes, custom shaders and scroll-driven camera paths carry the story, while kinetic type, a custom cursor, smooth scroll and seamless page transitions make the whole site feel like one continuous, directed piece of film you can touch.

This is the style that dominates the Awwwards **Sites of the Year** gallery. Of the SOTY-badged sites from 2017 to 2025 on Awwwards, most are 3D, WebGL or shader-led. Examples are Igloo Inc (abeto, 2024), Messenger (abeto, 2025), Lando Norris (OFF+BRAND, 2025), Lusion v3 (2023), Prometheus Fuels (Active Theory, 2021) and Bruno Simon's driveable portfolio (2019). See `references.md` for the full list with verification marks.

---

## 1. Position on the map

| Axis | Score | Why |
|---|---|---|
| **Classical ↔ Expressive** | **5 / 5 Expressive** | Originality and surprise are the brief. Lavie & Tractinsky's (2004) *expressive aesthetics* factor (creative, fascinating, special effects, sophisticated) describes this style almost word for word. |
| **Cool ↔ Warm** | **2 / 5 (cool-leaning)** | Dark stages, technical precision, chrome, glass and light. It turns warm when the scene is illustrated, toy-like or playful (Messenger, Umami Land, Bruno Simon's car), so warm variants exist. |
| **Density** | **2 / 5** | Few elements per screen. One hero object, one line of type, lots of black. The density is *in time* (many states across the scroll), not in space. |
| **Motion** | **5 / 5** | Motion is the medium. Every scroll tick, pointer move and route change is animated. |
| **Ornament** | **3 / 5** | UI chrome is minimal (hairlines, mono labels), but the rendered scene is very ornate: noise, refraction, particles, post-processing, grain. |
| **Contrast** | **4 / 5** | Near-black against bone or white, a single neon or signal accent, and specular highlights. The contrast is high but rarely pure #000 on #fff. |

---

## 2. Best-fit purposes

| Purpose | Fit | Reason |
|---|---|---|
| Creative agency / studio site | ✅ strong | The site *is* the portfolio piece. It proves technical skill directly, and juries reward it (Lusion, Active Theory, Noomo, abeto). |
| Creative-developer portfolio | ✅ strong | It is the fastest way for an individual to stand out. Bruno Simon's 2019 driving-game portfolio is the canonical case. |
| Product launch / hero product | ✅ strong | A 3D product you can rotate and scroll around sells physical objects (Opal Tadpole, car and phone launches). Use it on a launch microsite, not the whole store. |
| Games, entertainment, film, music | ✅ strong | The audience expects spectacle and accepts load time (Star Atlas, Messenger, Dark: Netflix guide). |
| Brand storytelling / campaign / cultural | ✅ strong | Scroll-driven narrative suits one-off stories and museums (Persepolis Reimagined for Getty, The Other Side of Truth). |
| Event / festival | ➖ possible | It works for the hype page. Schedules, tickets and maps must stay plain HTML. |
| Personal / CV site | ➖ possible | Only if you can build it well. A broken shader portfolio is worse than a clean static one. |
| Editorial / news | ➖ possible | Use it for long-form "snowfall" features only. Never put WebGL in the reading flow of daily articles. |
| SaaS / B2B | ➖ possible | One WebGL hero moment can work (see CC-3). A fully immersive site slows evaluation and hurts SEO and conversion. |
| E-commerce catalogue | ❌ avoid | Shoppers scan and compare. Scroll-jacking and heavy GPU load hurt conversion. Use a 3D viewer on the product page only. |
| Corporate / finance / government | ❌ avoid | Trust signals come from clarity (CC-2). Spectacle reads as distraction, and these sites carry heavy accessibility obligations. |
| Nonprofit / public service | ❌ avoid as default | Low-end devices and accessibility come first. The exception is a one-off awareness campaign (The Other Side of Truth). |

---

## 3. Visual DNA

### Typography
- **The display face is a characterful grotesk or neo-grotesk, set huge and tight.** Common paid choices are Neue Montreal, PP Mori, Aeonik, Neue Haas Grotesk, Founders Grotesk and Monument Extended. Free Google alternatives are **Bricolage Grotesque** (optical sizes), **Familjen Grotesk**, **Schibsted Grotesk**, **Unbounded** (wide and techy) and **Syne** (overused, so use it with care).
  - Setting: `clamp(3.5rem, 13vw, 15rem)`, `line-height: 0.84–0.9`, `letter-spacing: -0.05em`, weight 500–650.
- **The accent is an italic serif for one word per headline.** Common choices are PP Editorial New, Canela or Reckless. Free alternatives are **Instrument Serif** and **Fraunces**. The serif/grotesk clash gives a "human in the machine" moment.
- **Meta text is a monospace.** Common choices are PP Supply Mono or Söhne Mono. Free alternatives are **JetBrains Mono**, **IBM Plex Mono** and **Space Mono**. Set it at 11–12px, uppercase, `letter-spacing: 0.08em`, for indices like `(01)`, timestamps, coordinates, "Scroll" cues and loader counters.
- Type is treated as an object. Headlines are split into lines, words and characters and revealed from a mask, scrubbed by scroll or distorted in WebGL (text rendered to texture, MSDF text in Three.js / troika-three-text).

### Colour
| Role | Default ("Stage") | Logic |
|---|---|---|
| Background | `#08090b` | Near-black, never pure `#000`. Shader glow reads better and gradients band less. |
| Text | `#eceae4` (bone) | A warm off-white softens the cool stage. About 17:1 contrast. |
| Muted | `#9b9ba4` | Mono labels. About 7.4:1 contrast. |
| Accent | `#ff5b2e` (signal orange), or acid lime `#d6ff3d`, or cobalt `#2a3cff` | **Exactly one** accent, used for the serif word, the cursor dot and the CTA. |
| Scene palette | iridescent stops `#5b7cff → #2ee6c5 → #c86bff → #ff5b2e` | Lives *inside the shader* (cosine palette, fresnel, thin-film). The UI never uses these colours as flat fills. |

Rule: **the UI is monochrome and the light is colourful.** The colour comes from the rendering (fresnel rims, subsurface glow, bloom), not from painted boxes.

### Layout and grid
- A 12-column grid with large gutters, but most screens use only 2–3 elements: a headline bottom-left, the 3D object off-centre right, and a mono meta row along a hairline.
- **A fixed full-viewport `<canvas>` sits behind the DOM.** The DOM scrolls over it, and the scene reacts to scroll position. This "one persistent scene" pattern makes the site feel continuous.
- Sections are scenes. Each section is a camera position, light state or object state, often 100–200vh tall to give scroll "time".
- There is one **pinned horizontal sequence** (process, timeline or gallery) per site at most.
- Navigation is minimal: logo, 2–4 links, a local time or "available" status, and a sound toggle. It often uses `mix-blend-mode: difference` so it reads over any frame.

### Imagery and art direction
- Real-time 3D: abstract blobs or metaballs, product models, low-poly worlds, particle fields, glass and refraction, toon-shaded dioramas.
- Photography, when used, goes into WebGL planes so it can be distorted (RGB shift, liquid ripple, curl-noise displacement on hover or scroll velocity).
- Film grain, noise and post-processing (bloom, chromatic aberration, vignette) unify CG and photos.
- Sound design is optional but frequent on award winners (ambient loop, UI ticks), always with a mute toggle and off by default until the user interacts.

### Motion and interaction
- **Curves:** `expo.out` (`cubic-bezier(.16,1,.3,1)`) for reveals and `power4.inOut` / `cubic-bezier(.76,0,.24,1)` for transitions. Durations are long (1–1.6s) for reveals and short (150–250ms) for hovers.
- **Scroll:** Lenis smooth scroll at `lerp: 0.1`, plus GSAP ScrollTrigger with `scrub: 1` to tie scene uniforms and camera to scroll progress.
- **Preloader to hero:** a counter from 000 to 100, then a mask wipe, then characters rising with a 20–40ms stagger, while the 3D object "inflates" into place.
- **Page transitions:** Barba.js / Swup, or SPA routing with a WebGL transition (the canvas persists across routes and only the DOM swaps).
- **Pointer:** a custom cursor (dot plus lerped ring) that morphs into labels ("View", "Drag", "Play"), magnetic buttons, and pointer-reactive shaders (bulge, light direction, ripples).

### Micro-details
- `(01)`, `(02)` indices and `©2026` / coordinates / local time in mono.
- 1px hairlines at about 14% opacity, sharp corners (radius 0), with pills only for the cursor and CTA.
- An SVG `feTurbulence` grain overlay at 5–10% opacity that steps at about 6fps.
- Hover underlines that wipe in from left to right and wipe out to the right.
- An outlined (`-webkit-text-stroke`) numeral as a section marker.
- Selection colour set to the accent.

---

## 4. Why it works

**Arousal and novelty (collative variables).** Berlyne (1960, *Conflict, Arousal, and Curiosity*; 1971, *Aesthetics and Psychobiology*) showed that hedonic value follows an inverted U against arousal potential. Arousal potential is driven by *collative* properties: novelty, surprisingness, complexity, incongruity and uncertainty. Immersive sites raise exactly these variables: an unexpected 3D object, a scene that changes as you scroll, a cursor that becomes a label. The craft is landing at the *top* of the curve, not past it into confusion. Silvia (2005, *Emotion*) refines this: interest is high when something is appraised as **novel-complex** *and* the viewer feels able to **cope with/understand** it. This is why winning sites pair a wild scene with a dead-simple navigation.

**MAYA: "most advanced, yet acceptable".** Hekkert, Snelders & van Wieringen (2003, *British Journal of Psychology*, "'Most advanced, yet acceptable': Typicality and novelty as joint predictors of aesthetic preference in industrial design") found that preference rises with novelty *and* typicality together. Immersive sites that win keep the **typical skeleton** (logo top-left, a few nav links, work list, contact) and put the novelty in the rendering. Sites that also make navigation novel usually drop out of the "acceptable" zone.

**Immersion and flow.** Csikszentmihalyi (1990, *Flow: The Psychology of Optimal Experience*) describes flow as clear goals, immediate feedback and a balance of challenge and skill. Scroll-scrubbed storytelling gives continuous, immediate feedback: every pixel of scroll changes the scene. Jennett et al. (2008, *IJHCS* 66(9), "Measuring and defining the experience of immersion in games") describe immersion as lack of awareness of time and the real world, and high involvement. Preloaders, sound, full-bleed canvases and hidden scrollbars are deliberate devices toward that state, which is why games and entertainment fit the style so well.

**Motion captures attention.** Abrams & Christ (2003, *Psychological Science*, "Motion onset captures attention") showed that the *onset* of motion captures attention automatically. Kinetic type and reveals direct the eye, but every moving element competes. Continuous ambient motion near body text increases distraction. Use motion to say "look here next", not as wallpaper.

**First impressions are aesthetic and fast.** Lindgaard et al. (2006, *Behaviour & Information Technology*, "Attention web designers: You have 50 milliseconds…") and Tuch et al. (2012, *IJHCS*, visual complexity and prototypicality) show that visual appeal is judged in roughly 50ms and that low complexity plus high prototypicality wins *first* impressions. Immersive sites rely on the *opposite* profile, high complexity and low prototypicality. They work for audiences who arrived *looking for* novelty (juries, design buyers, fans), and they risk failing for task-driven visitors. This is the main strategic trade-off of the style. Also see the aesthetic-usability findings (Tractinsky, Katz & Ikar 2000, "What is beautiful is usable") and Hassenzahl (2004) on the pragmatic/hedonic split, both summarised in `00_Research/`.

**What juries reward.** Awwwards scores sites on Design 40%, Usability 30%, Creativity 20% and Content 10% (shown on every Awwwards site page). Usability is 30% of the score, so the SOTY-badged sites pair spectacle with fast first paint, clear nav and working mobile versions. Jury write-ups and site tags on SOTY-badged sites keep returning to *storytelling*, *3D*, *transitions* and *micro-interactions*. For example, the Igloo Inc listing is tagged "Infinite Scroll, Transitions, 3D", and Lando Norris is tagged "WebGL, GSAP, Webflow".

---

## 5. Uniqueness levers (pick 2–3 and commit)

1. **Give the scene an idea, not an effect.** Write one sentence the 3D *means* ("the studio sculpts light", "a tiny planet you deliver mail on"). Igloo Inc's ice crystals and Messenger's miniature planet are concepts. A generic floating blob is an effect.
2. **Choreograph one persistent scene across the whole site.** One canvas with keyed states per section (position, scale, noise amplitude, hue), not separate WebGL widgets per block.
3. **Make the material yours.** Pick one shading model and push it: thin-film iridescence, toon/cel with outlines, frosted glass with transmission, dithered 1-bit, halftone, or risograph grain in a shader.
4. **Make the input meaningful.** Let the pointer, scroll velocity, microphone, time of day or the visitor's weather change the scene. Fathom Signal's light direction follows the pointer, and the surface swells under it.
5. **Use a type-in-WebGL moment.** Render the headline into the scene once (refracted through glass, wrapped on a cylinder, displaced by noise), and keep the rest as accessible DOM text.
6. **Turn the loader into the first scene.** Make the preloader part of the story (a counter that becomes the hero number, an object assembling), not a spinner.
7. **Treat sound as a design layer.** Add a single ambient bed plus UI ticks, opt-in, with a visible toggle. Very few sites do it well.
8. **Ship a designed quiet mode.** Give reduced-motion users a deliberate static composition (a rendered still frame, all content visible), not a broken page. Juries and users both notice.
9. **Pick one weird navigation idea, and only one.** For example a draggable world map, a drivable car, a circular project wheel or a text-only command line. Keep every other UI convention typical (MAYA).
10. **Add a signature transition between routes.** The canvas persists and the object morphs into the next page's hero (shared-element transition in WebGL), so the site feels like a single shot.

---

## 6. Clichés and pitfalls (what looks generic or AI-made)

- A **rainbow "holographic" blob** with default `MeshNormalMaterial` colours or an untuned cosine palette that looks like a thermal camera.
- **Syne + lime-on-black + a marquee + a magnetic button.** This is the 2022 Awwwards starter kit. Each element is fine, but all four together read as a template.
- A **custom cursor that only lags.** If the cursor never changes meaning (labels, states), it is friction without benefit.
- **Scroll-jacking that fights the trackpad:** wheel snapping, sections you cannot leave, or horizontal scroll triggered by vertical scroll on mobile. Nielsen Norman Group observed that most participants were at least mildly disoriented by scrolljacking (Paul, 2023, "Scrolljacking 101").
- **10-second preloaders** that load 40MB of uncompressed GLB and 4K textures.
- **Split-text on every paragraph.** Animate headlines. Body copy should simply be readable.
- **Generic "creative technologist" copy** ("We craft digital experiences that push boundaries"). Every studio says it.
- **Particles for the sake of particles,** with no lighting, depth or story role.
- **Stock Three.js examples** (the default torus knot, the Codrops demo pasted without changes, the default `OrbitControls` spin).
- **Text placed directly over a busy, bright scene** with no scrim, so contrast fails.
- **A desktop-only experience** where mobile gets a broken scene or a blank canvas.

---

## 7. Accessibility and performance notes

**Motion safety**
- Honour `prefers-reduced-motion: reduce`. Skip the preloader, disable smooth scroll, pinning and scrubbing, render **one still frame** of the scene, and show all content. Also provide an **on-page motion toggle**. WCAG 2.2.2 "Pause, Stop, Hide" (Level A) requires a pause mechanism for auto-playing motion longer than 5s, and 2.3.3 "Animation from Interactions" (AAA) covers motion triggered by scrolling.
- Vestibular triggers include large-scale zoom and parallax, spinning, scroll-linked motion moving at a different speed from the scroll, and full-screen camera moves (Val Head, 2015, "Designing Safer Web Animation for Motion Sensitivity", *A List Apart*). The sensory-conflict explanation of motion sickness (Reason & Brand, 1975) and cybersickness research (LaViola, 2000, *SIGCHI Bulletin*) both predict trouble when visual motion is decoupled from the user's own input. Scrubbed motion (motion tied 1:1 to scroll) is safer than autonomous camera flights.
- Avoid flashes over 3 per second (WCAG 2.3.1), which matters for glitch and strobe shaders.

**Content and semantics**
- All meaningful text lives in the DOM, not only in the canvas. Split-text spans get `aria-hidden="true"`, and the parent gets the full string via `aria-label` or a visually-hidden copy.
- The canvas gets `aria-hidden="true"`, or an accessible description if it carries meaning.
- Keyboard: every hover-only reveal (project previews, magnetic buttons) must also work on `:focus-visible`. The custom cursor is disabled on `(pointer: coarse)` and must never hide focus rings.
- Smooth-scroll libraries must keep native scrolling semantics. Lenis keeps native scroll and works with find-in-page and anchors. Avoid transform-based fake scroll containers on content sites.

**Performance budget (Core Web Vitals)**
- Google's "good" thresholds are **LCP ≤ 2.5s, INP ≤ 200ms, CLS ≤ 0.1** at the 75th percentile (web.dev). Make the **LCP element a DOM headline or poster image**, not the WebGL scene, and initialise WebGL after first paint.
- GPU budget: one persistent renderer, `devicePixelRatio` capped at 1.5–2, geometry compressed with Draco/Meshopt, textures as KTX2/Basis, baked lighting instead of real-time shadows, and adaptive quality (drop DPR or effects when frame time exceeds about 20ms).
- Pause the render loop when the tab is hidden or the canvas is off-screen, and render on demand when nothing animates.
- Ship a no-WebGL fallback (CSS gradient or poster image) and test on a mid-range Android phone, not only an M-series Mac.
- The transferred JS budget for a launch microsite is realistically 300–600KB gzipped plus assets. Lazy-load heavy scenes per route.

---

## 8. Neighbouring styles and hybrids

| Neighbour | Hybrid | How to blend |
|---|---|---|
| **CC-3 Tech-Product** | "Product-as-hero launch" | A WebGL product hero and one scrubbed explode-view section, with the rest as a clean SaaS layout. This is the safest commercial use of EC-1. |
| **CW-1 Luxury-Refined** | "Slow cinema" | Serif type, very slow camera dollies, photoreal materials, lots of black, no cursor gimmicks. Common for cars, watches and real estate. |
| **EC-2 Brutalist-Raw** | "Glitch brutalism" | Raw HTML grid and system fonts on top of a dithered or glitch shader. Anti-polish plus real-time tech. |
| **EW-1 Playful-Illustrative** | "Toy world" | Toon-shaded low-poly worlds, physics and bouncy springs. Examples are Bruno Simon's car, Messenger and Umami Land. EC-1 becomes warm. |
| **EW-2 Retro-Nostalgic** | "Y2K chrome / PS1" | Chrome blobs, low-res dithered PS1 shaders, CRT post-processing, pixel fonts. |
| **CC-1 Swiss-Editorial** | "Swiss + WebGL" | A strict 12-column type grid with a single precise shader moment (an image distortion on hover). Very common for studio sites, and restrained enough for content-heavy portfolios. |

---

### Files in this folder
- `PROMPT.md`: a copy-paste prompt for generating a site in this style
- `references.md`: 17 awarded sites and 14 creators, with verification marks
- `techniques.md`: a cookbook of 14 signature techniques with code sketches and caveats
- `tokens.css`: design tokens (Stage, Lab Paper, Neon Noir)
- `demo.html`: Fathom Signal, a fictional real-time studio (Three.js shader hero, GSAP ScrollTrigger, Lenis, custom cursor, reduced-motion mode)
- `images/`: 24 reference images and `CREDITS.md`
