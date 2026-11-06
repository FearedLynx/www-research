# EC-1 technique cookbook

Fourteen signature techniques of immersive / experimental sites. Each entry covers what it is, when to use it, the library, a minimal sketch, and the performance (⚡) and accessibility (♿) caveats. The code sketches are deliberately short; `demo.html` contains working versions of techniques 1, 2, 3, 4, 5, 6, 7, 9, 10, 12 and 14.

**Reference stack** (CDN-friendly):

| Need | Library | CDN |
|---|---|---|
| 3D / shaders | Three.js (r128 UMD on cdnjs; modern ESM on jsdelivr) | `cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js` |
| React 3D | React Three Fiber plus drei | npm |
| Minimal WebGL | OGL | npm / jsdelivr |
| 2D WebGL (images, text FX) | PixiJS | cdnjs |
| Timeline / scroll | GSAP 3 plus ScrollTrigger (SplitText ships free with GSAP 3.13+) | `cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/` |
| Smooth scroll | Lenis | `cdn.jsdelivr.net/npm/lenis@1.1.13/dist/lenis.min.js` |
| Page transitions | Barba.js, Swup, or the View Transitions API | npm |
| Camera choreography | Theatre.js | npm |
| No-code 3D | Spline (exports a runtime embed) | spline.design |

**Global rule:** every technique below has a `prefers-reduced-motion` branch. Write it first.

```js
const reduce = matchMedia('(prefers-reduced-motion: reduce)').matches;
const fine   = matchMedia('(hover: hover) and (pointer: fine)').matches;
```

---

## 1. Persistent full-screen WebGL stage

**What:** a single `<canvas>`, fixed behind the DOM, with one renderer and one scene for the whole site. Sections change *uniforms and transforms*; they do not create new canvases.
**When:** always, in this style. It is the backbone of the "one continuous shot" feeling.
**Library:** Three.js / OGL / R3F (`<Canvas>` at the app root plus `r3f-scroll-rig` for DOM-synced meshes).

```js
const renderer = new THREE.WebGLRenderer({ canvas, alpha: true, antialias: innerWidth > 768 });
renderer.setPixelRatio(Math.min(devicePixelRatio, innerWidth < 768 ? 1.5 : 1.75));
let running = true;
function loop(){ if(!running) return; update(); renderer.render(scene, camera); requestAnimationFrame(loop); }
document.addEventListener('visibilitychange', () => { running = !document.hidden; if (running) loop(); });
```
```css
canvas#gl { position: fixed; inset: 0; z-index: 0; pointer-events: none; }
main { position: relative; z-index: 2; }
```
⚡ Cap DPR. Pause when hidden or off-screen. Initialise *after* first paint so the LCP is the DOM headline. Use one draw call per hero object where possible.
♿ `aria-hidden="true"` on the canvas, with all meaning duplicated in DOM text. Provide a CSS/poster fallback when `WebGLRenderer` throws.

---

## 2. Noise-displaced shader object ("the blob", done right)

**What:** a sphere or icosahedron whose vertices are pushed along the normal by 3D simplex noise, shaded with fresnel plus a tuned palette (thin-film / iridescent).
**When:** an abstract hero for studios, AI or tech brands, and music. Make it *mean* something (light, sound, data), or it becomes a cliché.
**Library:** Three.js `ShaderMaterial` with Ashima/Stefan Gustavson simplex noise and Inigo Quilez's cosine palette.

```glsl
// vertex
uniform float uTime, uAmp, uFreq;
varying vec3 vN; varying vec3 vV; varying float vD;
float field(vec3 p){ return snoise(p*uFreq + uTime*.15) * uAmp; }
vec3 displace(vec3 p){ vec3 n = normalize(p); return n * (1. + field(n)); }
void main(){
  vec3 p = displace(position);
  // recompute normal from two displaced neighbours (tangent t, bitangent b)
  vec3 t = normalize(cross(normalize(position), vec3(0.,1.,0.)+.001)); vec3 b = cross(normalize(position), t);
  vec3 n = normalize(cross(displace(position+t*.01)-p, displace(position+b*.01)-p));
  vD = field(normalize(position)); vN = normalize(normalMatrix*n);
  vec4 mv = modelViewMatrix*vec4(p,1.); vV = normalize(-mv.xyz); gl_Position = projectionMatrix*mv;
}
// fragment
vec3 pal(float t){ return vec3(.42,.42,.55)+vec3(.42,.38,.45)*cos(6.2831*(vec3(1.,.8,.6)*t+vec3(.55,.62,.72))); }
void main(){ float f = pow(1.-max(dot(normalize(vN),vV),0.),2.4);
  vec3 c = mix(vec3(.015,.018,.026), pal(f*.7+vD*.9), .08+.92*pow(f,1.25)); gl_FragColor = vec4(c,1.); }
```
⚡ Subdivision is the main cost: around 50–60 icosahedron detail on desktop and 24–30 on mobile. Never recompute geometry on the CPU each frame.
♿ Keep `uTime` speed slow (<0.2). In reduced-motion mode, render one frame and stop.
**Avoid:** untuned rainbow palettes (they read as a "thermal camera"). Keep the core dark and put the colour on the rim.

---

## 3. Scroll-scrubbed scene / camera choreography

**What:** scroll progress drives camera position, object transforms and shader uniforms, so each section is a keyframe.
**When:** storytelling sites, product explode-views, studio sites with one persistent object.
**Library:** GSAP ScrollTrigger (`scrub`) or Theatre.js sheets (`sequence.position = progress * length`).

```js
const state = { x: 1.1, s: 1, amp: .22, hue: 0 };      // read every frame by the render loop
let last = { ...state };
function key(trigger, to){
  gsap.fromTo(state, { ...last }, { ...to, ease: 'none', immediateRender: false,
    scrollTrigger: { trigger, start: 'top bottom', end: 'top top', scrub: 1.2 } });
  last = { ...last, ...to };
}
key('.manifesto', { x: -1.6, s: 1.75, amp: .32, hue: .2 });
key('.work',      { x:  1.9, s: .8,  amp: .18, hue: .4 });
```
⚡ Only uniforms change, never geometry. `fromTo` plus `immediateRender:false` keeps segments consistent when the page reloads mid-scroll.
♿ Scrubbed motion is tied 1:1 to the user's input, which makes it safer than autonomous camera flights. Still, avoid large zooms and fast rotation (vestibular triggers).

---

## 4. Smooth scroll that keeps native scroll

**What:** inertia-smoothed scrolling. Modern libraries (Lenis) animate the *native* scroll position, so anchors, find-in-page, `position: sticky` and the scrollbar keep working.
**When:** almost every immersive site, because it removes wheel jitter that makes scrubbed WebGL stutter.
**Library:** Lenis (darkroom.engineering). Locomotive Scroll v5 is also built on Lenis.

```js
const lenis = new Lenis({ lerp: 0.1, smoothWheel: true });
lenis.on('scroll', ScrollTrigger.update);
gsap.ticker.add(t => lenis.raf(t * 1000));
gsap.ticker.lagSmoothing(0);
```
```css
html.lenis, html.lenis body { height: auto; }
.lenis.lenis-smooth { scroll-behavior: auto !important; }
```
⚡ Cheap. Avoid older "transform the whole page" smooth-scroll containers, which break `position: fixed` and accessibility.
♿ Disable it under reduced motion, and keep keyboard scrolling (Space, PgDn) responsive. Never change the scroll *direction*. Nielsen Norman Group found scroll-jacking disorienting for most users (Paul, 2023).

---

## 5. Split-text kinetic reveals

**What:** headlines split into lines, words or characters, each masked by an `overflow:hidden` parent and animated up from `yPercent: 110`, with a slight rotation and stagger.
**When:** hero headline, section titles, footer statement. **Not** body copy.
**Library:** GSAP SplitText (free since GSAP 3.13), SplitType, or a 10-line manual split.

```js
el.innerHTML = el.textContent.split(' ').map(w =>
  `<span class="word">${[...w].map(c => `<span class="ch">${c}</span>`).join('')}</span>`).join(' ');
gsap.from(el.querySelectorAll('.ch'), { yPercent: 110, rotate: 6, duration: 1.2, ease: 'expo.out', stagger: .028 });
```
```css
.line { display:block; overflow:hidden; } .ch { display:inline-block; } .word { white-space:nowrap; }
```
⚡ Character spans multiply DOM nodes, so limit them to about 40–80 characters per animated block.
♿ Screen readers read split spans letter by letter. Put `aria-label="Full sentence"` on the heading and `aria-hidden="true"` on the split lines.

---

## 6. Scroll-scrubbed word highlight ("reading light")

**What:** a large paragraph whose words go from 15% to 100% opacity as you scroll through it.
**When:** manifesto or about statements. It forces pacing.
**Library:** GSAP ScrollTrigger.

```js
gsap.to('.manifesto .w', { opacity: 1, stagger: .1, ease: 'none',
  scrollTrigger: { trigger: '.manifesto', start: 'top 80%', end: 'bottom 45%', scrub: true } });
```
⚡ Opacity only, so it stays on the compositor.
♿ At 0.15 opacity, unread words fail contrast. Show the full text under reduced motion and when JS fails (default CSS `opacity:1`, with JS lowering it).

---

## 7. Custom cursor with semantic states

**What:** a small dot (instant) plus a ring (lerped), which grows on links and becomes a filled label ("View", "Drag", "Play") on projects.
**When:** desktop studio and portfolio sites. It must *say something*, not just lag.
**Library:** vanilla JS plus `gsap.quickSetter` / `quickTo`.

```js
const p = {x:0,y:0}, r = {x:0,y:0}, setX = gsap.quickSetter(ring,'x','px'), setY = gsap.quickSetter(ring,'y','px');
addEventListener('pointermove', e => { p.x = e.clientX; p.y = e.clientY; gsap.set(dot, { x:p.x, y:p.y }); });
gsap.ticker.add(() => { const k = 1 - Math.pow(1 - .18, gsap.ticker.deltaRatio()); r.x += (p.x-r.x)*k; r.y += (p.y-r.y)*k; setX(r.x); setY(r.y); });
document.addEventListener('pointerover', e => cursor.classList.toggle('is-label', !!e.target.closest('[data-cursor=label]')));
```
⚡ Frame-rate-independent lerp (`deltaRatio`). Update transforms only, never `left/top`.
♿ Only enable it on `(hover:hover) and (pointer:fine)`. Never hide focus outlines. Keep the OS cursor for text inputs. `pointer-events:none` on the cursor element.

---

## 8. Shader-distorted image hover (WebGL image planes)

**What:** project images rendered as WebGL planes synced to DOM `<img>` positions. On hover or scroll velocity a fragment shader applies a liquid ripple, RGB split or noise displacement.
**When:** work grids and lists on studio sites. It is the classic Codrops effect.
**Library:** Three.js / OGL / PixiJS, or `r3f-scroll-rig` (`<UseCanvas>` plus `<ScrollScene>`) for React.

```glsl
uniform sampler2D uTex; uniform float uHover; uniform vec2 uMouse; varying vec2 vUv;
void main(){
  float d = distance(vUv, uMouse);
  vec2 off = normalize(vUv - uMouse) * .04 * uHover * smoothstep(.45, 0., d);
  float r = texture2D(uTex, vUv + off*1.2).r, g = texture2D(uTex, vUv + off).g, b = texture2D(uTex, vUv + off*.8).b;
  gl_FragColor = vec4(r,g,b,1.);
}
```
```js
// sync plane to DOM image each frame (read rects once, update on resize/scroll offset)
mesh.position.set(rect.left + rect.width/2 - innerWidth/2, -(rect.top + rect.height/2) + innerHeight/2, 0); // ortho camera in px
```
⚡ Use an orthographic camera in pixel units. Read `getBoundingClientRect` on resize, not every frame. Load textures lazily.
♿ The real `<img alt>` stays in the DOM (it can be `opacity:0` once WebGL is ready). Hover effects must also trigger on `:focus-visible`.

---

## 9. Cursor-trailing preview card (DOM version of 8)

**What:** hovering a text list of projects reveals a floating image card that trails the cursor and tilts with velocity.
**When:** text-first work lists. It is cheaper than technique 8 and works without WebGL.
**Library:** GSAP `quickSetter`.

```js
gsap.set(prev, { xPercent:-50, yPercent:-50 });
gsap.ticker.add(() => { const nx = pv.x + (p.x-pv.x)*.12; const vx = nx - pv.x; pv.x = nx; pv.y += (p.y-pv.y)*.12;
  gsap.set(prev, { x: pv.x, y: pv.y, rotation: gsap.utils.clamp(-12, 12, vx*.6) }); });
```
⚡ Preload the preview images. Use `will-change: transform` on the card only.
♿ Decorative (`aria-hidden`). The list rows are real links with descriptive text.

---

## 10. Magnetic buttons

**What:** a CTA that pulls toward the cursor within its bounds and springs back elastically.
**When:** one or two primary CTAs (contact, "play"). Not every link.
**Library:** `gsap.quickTo`.

```js
const xTo = gsap.quickTo(btn,'x',{duration:.6,ease:'power3'}), yTo = gsap.quickTo(btn,'y',{duration:.6,ease:'power3'});
btn.addEventListener('pointermove', e => { const b = btn.getBoundingClientRect();
  xTo((e.clientX - b.left - b.width/2)*.4); yTo((e.clientY - b.top - b.height/2)*.4); });
btn.addEventListener('pointerleave', () => gsap.to(btn, { x:0, y:0, duration:1.1, ease:'elastic.out(1,.35)' }));
```
⚡ Trivial cost.
♿ Fine pointers only. The moving hit area must not move away from the pointer by more than about 30% of its size.

---

## 11. Preloader to hero transition

**What:** a 000→100 counter or progress bar tied to *real* asset loading (fonts, GLB, textures), then a mask/clip-path wipe straight into the hero animation.
**When:** sites that genuinely need to load 3D assets. If nothing heavy loads, skip it.
**Library:** `THREE.LoadingManager` / `useProgress` (drei) plus a GSAP timeline.

```js
const mgr = new THREE.LoadingManager();
mgr.onProgress = (_, loaded, total) => gsap.to(counter, { v: loaded/total*100, onUpdate: draw });
mgr.onLoad = () => gsap.timeline()
  .to('.loader', { clipPath: 'inset(0 0 100% 0)', duration: 1.1, ease: 'expo.inOut' })
  .from(heroState, { s: .25, amp: .9, duration: 2.2, ease: 'expo.out' }, '<.1')
  .from('.hero .ch', { yPercent: 110, stagger: .028, ease: 'expo.out' }, '<.35');
```
⚡ The loader must not delay the LCP for content that is already available. Keep the total under about 2–3s on 4G. A fake 5-second counter is a pitfall.
♿ Skip it entirely under reduced motion. The loader is `aria-hidden`. Announce "loading" with `aria-busy` on `<main>` if it blocks content.

---

## 12. Pinned horizontal scroll sequence

**What:** a section pins while vertical scroll translates a horizontal track of panels.
**When:** process steps, timelines, galleries. **One per site** at most.
**Library:** GSAP ScrollTrigger (`pin`) inside `gsap.matchMedia` (desktop only).

```js
gsap.matchMedia().add('(min-width: 768px)', () => {
  const dist = () => track.scrollWidth - innerWidth;
  gsap.to(track, { x: () => -dist(), ease: 'none',
    scrollTrigger: { trigger: '.process', pin: true, scrub: 1, end: () => '+=' + dist(), invalidateOnRefresh: true } });
});
```
⚡ Pinning inserts spacers. Call `ScrollTrigger.refresh()` after fonts and images load.
♿ On mobile and under reduced motion, stack the panels vertically. Keyboard users must be able to reach every panel's content (tab order follows the DOM).

---

## 13. Page transitions with a persistent canvas

**What:** route changes animate instead of hard-reloading. The DOM content swaps while the WebGL scene stays alive and morphs into the next page's state (the shared-element effect).
**When:** multi-page studio sites and case studies.
**Library:** Barba.js or Swup (multi-page), Next/Nuxt route transitions (SPA), or the native **View Transitions API** (`document.startViewTransition`, and cross-document `@view-transition { navigation: auto; }`).

```js
barba.init({ transitions: [{
  async leave({ current }) { await gsap.to(current.container, { opacity: 0, y: -40, duration: .6, ease: 'power4.in' }); },
  enter({ next }) { setSceneFor(next.namespace); gsap.from(next.container, { opacity: 0, y: 40, duration: .9, ease: 'expo.out' }); }
}]});
```
⚡ Prefetch on hover. Dispose geometries and textures you no longer need (`.dispose()`) or memory will grow per route.
♿ Move focus to the new page's `<h1>`, update `document.title`, and announce the change (live region). Respect reduced motion with an instant swap.

---

## 14. Infinite marquee, grain overlay and other "texture" moves

**What:** (a) a CSS-only infinite marquee that duplicates the group and translates by -50%; (b) an SVG `feTurbulence` grain overlay stepping at about 6fps; (c) `mix-blend-mode: difference` nav that reads over any frame.
**When:** at most one marquee per page, as a beat between sections. Grain on dark sites to unify CG and photos.
**Library:** CSS only.

```css
.track { display:flex; width:max-content; animation: marquee 28s linear infinite; }
.group { display:flex; gap:3rem; padding-right:3rem; }
@keyframes marquee { to { transform: translateX(-50%); } }
.marquee:hover .track { animation-play-state: paused; }
.grain { position:fixed; inset:-50%; opacity:.07; mix-blend-mode:overlay; pointer-events:none;
  background-image:url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='160' height='160'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3'/></filter><rect width='100%' height='100%' filter='url(%23n)'/></svg>");
  animation: grain 1s steps(6) infinite; }
```
⚡ A full-screen blended overlay costs fill-rate on low-end GPUs, so drop the grain on mobile if FPS suffers.
♿ The marquee duplicate is `aria-hidden`, with the message in a visually-hidden element. Stop marquees and grain under reduced motion (WCAG 2.2.2 requires a pause for anything moving longer than 5s).

---

## Bonus patterns (no sketch)

- **MSDF / troika text in WebGL:** a headline inside the 3D scene that refracts or bends. Keep a DOM copy for accessibility.
- **GPGPU particles (FBO ping-pong):** thousands of particles morphing between shapes (a logo into a product). Needs WebGL2 float textures, so provide a fallback.
- **Post-processing:** bloom, chromatic aberration, film grain via `pmndrs/postprocessing`. Each pass is a full-screen draw, so budget one or two passes.
- **Spline embeds:** fast prototyping and no-code 3D. The runtime is heavy, so prefer a GLB export into Three.js for production.
- **Audio-reactive uniforms:** the Web Audio `AnalyserNode` feeds `uAmp`. Make it opt-in only, after a user gesture.
