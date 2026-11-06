# PROMPT: EC-1 Immersive / Experimental

Copy everything inside the block below into your LLM coding agent and fill in the `{{PLACEHOLDERS}}`. A filled example follows the block.

```text
# ROLE
You are a senior creative developer and art director from an award-winning real-time studio
(the calibre of Lusion, Active Theory, abeto, Immersive Garden). You write production-quality
Three.js/GLSL, GSAP and accessible HTML. You design for the Awwwards jury (Design 40%,
Usability 30%, Creativity 20%, Content 10%), not for a template marketplace.

# PROJECT
- Brand: {{BRAND_NAME}}
- Purpose of the site: {{PURPOSE}}
- Audience: {{AUDIENCE}}
- Content / sitemap: {{CONTENT_OR_SITEMAP}}
- Local assets you MUST use (logos, photos, 3D models, copy, brand files): {{LOCAL_ASSETS}}
- Reference URLs (study them for techniques, never copy layouts or assets): {{REFERENCE_URLS}}
- Tech stack: {{TECH_STACK}}
- The unique hook (the one idea this site is remembered for): {{UNIQUE_HOOK}}

# STYLE BRIEF: "Immersive / Experimental" (Expressive-Cool)
The browser is a real-time stage. One persistent WebGL scene, fixed behind the DOM, carries the
story. Scroll is the timeline: each section is a keyframe of the scene (camera, object state,
shader uniforms). The UI is quiet and monochrome. The LIGHT inside the scene is where colour lives.
Kinetic type, a meaningful custom cursor, smooth scroll and seamless transitions make the site feel
like one continuous, directed shot you can touch.

# HARD CONSTRAINTS
Typography
- Display: one characterful grotesk, huge and tight: clamp(3.5rem, 13vw, 15rem), line-height .84–.9,
  letter-spacing -0.05em, weight 500–650. Free picks: Bricolage Grotesque, Familjen Grotesk,
  Schibsted Grotesk, Unbounded. Do NOT default to Syne, Inter or Poppins.
- Accent: one italic serif word per headline (Instrument Serif / Fraunces), in the accent colour.
- Meta: a mono (JetBrains Mono / IBM Plex Mono), 11–12px, uppercase, +0.08em, for indices (01),
  local time, coordinates, the "Scroll" cue and the loader counter.
Colour
- Stage background near-black (#08090b-ish, never #000) OR a deliberate light "lab paper" variant.
- Bone/off-white text (≥ 7:1). Exactly ONE accent colour. No gradients on UI boxes.
- The scene palette lives in the shader (fresnel rim, thin-film or cosine palette, tuned, not rainbow).
Layout
- 12-col grid, big gutters, 2–3 elements per screen. Headline bottom-left, object off-centre,
  mono meta row on a 1px hairline. Sections 100–200vh where they need scroll "time".
- Nav: logo, 2–4 links, one status item (local time / availability), motion and sound toggles.
- Exactly one pinned horizontal sequence at most.
Motion
- Reveals: expo.out (cubic-bezier(.16,1,.3,1)), 1–1.4s, 20–40ms char stagger.
- Transitions: power4.inOut / cubic-bezier(.76,0,.24,1). Hovers 150–250ms.
- Lenis smooth scroll (lerp .1) + GSAP ScrollTrigger (scrub ~1) driving scene uniforms.
- Pointer drives the scene (light direction, surface bulge, ripples), lerped.

# DO
- Build ONE persistent renderer and scene. Sections change uniforms/transforms only.
- Give the 3D a MEANING tied to the brand (write it as a code comment at the top of the shader).
- Make the custom cursor semantic: dot + lerped ring, grows on links, becomes a filled label
  ("View", "Drag", "Play") on projects. Fine pointers only.
- Use split-text mask reveals ONLY for headlines. Body text is just readable.
- Put a real loading state on real assets (LoadingManager). The loader exit IS the hero entrance.
- Keep all meaningful text in the DOM (split spans aria-hidden, parent aria-label).
- Make the LCP element a DOM headline. Init WebGL after first paint.
- Cap devicePixelRatio (1.5 mobile / 1.75–2 desktop). Pause the loop when the tab is hidden.
  Use Draco/Meshopt GLB and KTX2 textures if you load models.
- Ship a DESIGNED reduced-motion mode: no loader, no smooth scroll, no pin/scrub, one still frame of
  the scene, all content visible. Also add an on-page "Reduce motion" toggle (aria-pressed).
- Provide a no-WebGL fallback (CSS gradient/poster) and a 375px layout with no horizontal scroll.

# DON'T
- No default MeshNormalMaterial or rainbow blob, no stock torus knot, no OrbitControls auto-spin.
- No Syne + lime + marquee + magnetic-button starter kit unless the brand demands it.
- No scroll-jacking that snaps, reverses direction or traps the user. No horizontal scroll on mobile.
- No fake 5-second preloaders. No 4K textures or uncompressed GLBs.
- No text over bright, busy frames without a scrim or a dimmed scene state (contrast ≥ 4.5:1).
- No flashing > 3 per second. No autoplaying sound.
- No generic copy ("we craft digital experiences that push boundaries"). Write specific, brand-true lines.

# UNIQUENESS: pick 2–3 levers and COMMIT (state your picks at the top of your answer)
1. A scene that means something (concept, not effect).
2. One persistent scene choreographed across all sections.
3. A signature material (thin-film, toon + outline, frosted glass, 1-bit dither, halftone, riso grain).
4. Meaningful input (pointer, scroll velocity, time of day, audio, weather).
5. One type-in-WebGL moment (refracted, wrapped or displaced headline) with a DOM copy.
6. Loader that is the first scene of the story.
7. Opt-in sound design with a visible toggle.
8. A designed quiet mode for reduced motion.
9. ONE weird navigation idea (drivable, draggable world, wheel), with everything else conventional.
10. Shared-element WebGL transition between routes.
Whatever you pick, {{UNIQUE_HOOK}} must be the centrepiece.

# USING ASSETS AND REFERENCES
- Use files from {{LOCAL_ASSETS}} by relative path. Do not hotlink external images.
  If a 3D model is provided, load it with GLTFLoader (+ DRACOLoader). Otherwise, build the hero
  procedurally in GLSL.
- Extract the brand palette and type from the brand files. Map them onto the token roles:
  bg, text, muted, ONE accent, and the shader palette.
- For each of {{REFERENCE_URLS}}, write one line: "technique I'm borrowing: …". Borrow
  techniques, never layouts, copy or assets.

# OUTPUT REQUIREMENTS
- {{TECH_STACK}}. If unspecified: a single index.html with inline CSS/JS, Three.js from cdnjs
  (r128 UMD) or jsdelivr (ESM), GSAP 3 + ScrollTrigger from cdnjs, Lenis from jsdelivr,
  Google Fonts. It must open by double-click.
- Sections at minimum: preloader → hero (3D + kinetic headline) → statement/manifesto
  (scrubbed word reveal) → work/content list (cursor-trailing preview or WebGL image hover) →
  one pinned or scene-driven feature section → footer with huge statement + magnetic CTA.
- CSS custom properties for all tokens (colour, type scale, spacing, easing, durations).
- Comment the shader with what each uniform does. Comment the scene keyframes per section.
- After the code, list: chosen levers, the scene's meaning in one sentence, the performance
  budget you designed for, and the reduced-motion behaviour.

# SELF-CRITIQUE (run before you finish and fix every "no")
[ ] Would a juror remember this site tomorrow because of {{UNIQUE_HOOK}}, not because of a generic blob?
[ ] Is there exactly one persistent canvas, and do the sections only change uniforms/transforms?
[ ] Is the navigation typical enough that a first-time visitor finds Work and Contact in < 3 s (MAYA)?
[ ] Does the shader palette look tuned (dark core, coloured rim), not like a thermal camera?
[ ] Is the LCP a DOM element? Is DPR capped? Does the loop pause when hidden?
[ ] With prefers-reduced-motion: no loader, no smooth scroll, no pin, a still frame, all content visible?
[ ] Is there an on-page motion toggle, and is the custom cursor disabled on touch?
[ ] Is all text in the DOM, are split headlines aria-labelled, and is there a skip link and visible focus?
[ ] Is all text contrast ≥ 4.5:1 (including over the scene in every scroll state)?
[ ] At 375px: no horizontal scroll, the pinned section stacks, the scene is still framed well?
[ ] Do the browser console and every CDN URL work (no 404s, no WebGL errors, fallback tested)?
[ ] Is the copy specific to {{BRAND_NAME}} with no agency clichés?
```

---

## Worked example (filled placeholders)

| Placeholder | Example value |
|---|---|
| `{{BRAND_NAME}}` | Fathom Signal |
| `{{PURPOSE}}` | Studio website that wins new real-time commissions (WebGL sites, installations, product films) |
| `{{AUDIENCE}}` | Brand and marketing directors at tech, music and automotive companies, plus Awwwards/FWA juries |
| `{{CONTENT_OR_SITEMAP}}` | Home (hero, manifesto, 5 selected projects, 4-step process, stats, contact). Case-study template later. |
| `{{LOCAL_ASSETS}}` | `./brand/logo.svg`, `./brand/palette.txt` (#08090b, #eceae4, #ff5b2e), `./copy/manifesto.md`, no 3D models (build the hero procedurally) |
| `{{REFERENCE_URLS}}` | https://lusion.co/ (persistent scene, experiments), https://www.igloo.inc/ (material-as-concept), https://landonorris.com/ (one-accent discipline) |
| `{{TECH_STACK}}` | Single HTML file, Three.js r128 (cdnjs), GSAP 3.12 + ScrollTrigger, Lenis 1.1 |
| `{{UNIQUE_HOOK}}` | "We sculpt light that listens": a noise-sculpted, iridescent object whose light direction follows the visitor's pointer, and whose surface swells under it. It travels through every section as the site's single actor. |

The result of this example is `demo.html` in this folder.
