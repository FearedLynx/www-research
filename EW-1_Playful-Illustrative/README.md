# EW-1 · Playful-Illustrative

## 1. One-line definition
A brand-as-character style: custom illustration and a mascot carry the identity, set in saturated colour, chunky rounded type, sticker and collage layering and springy motion, so that every interaction feels like poking a friendly toy.

---

## 2. Position on the map

| Axis | Score | Why |
|---|---|---|
| Classical ↔ Expressive | **4 / 5** (expressive) | Originality and surprise beat order, but the best examples keep a clean, readable UI layer under the art (Ponpon Mania's quiet nav, Duolingo's strict button system). |
| Cool ↔ Warm | **5 / 5** (warm) | Faces, hand-drawn lines, food and animals, warm yellows and corals. This is the warmest folder in the library. |
| Density | **3 / 5** | Hero scenes are busy collages, but content sections breathe. Confetti layers are sparse by design. |
| Motion | **4 / 5** | Spring and overshoot easing, idle character loops (blink, bob), squash-and-stretch on press. It is rarely scroll-jacked. |
| Ornament | **5 / 5** | Stickers, doodles, outlines, offset shadows, badges, marquees. Decoration is the content. |
| Contrast | **3 / 5** | High chroma, but values sit close together (yellow next to coral). Legibility comes from a dark "ink" outline colour rather than black-and-white contrast. |

---

## 3. Best-fit purposes

| Purpose | Fit | Reason |
|---|---|---|
| Portfolio | ➖ | Great for illustrators and character designers. For anyone else the art can upstage the work. |
| Agency | ➖ | Works for studios whose product *is* playful work (ToyFight, Upperquad); otherwise it reads as unserious. |
| Corporate | ❌ | Trust signals (restraint, data, institutional tone) clash with mascots, except for internal culture pages. |
| SaaS | ✅ | Friendly B2C or SMB SaaS and fintech (Mailchimp, Fruitful, Duolingo). A mascot lowers perceived complexity. |
| E-commerce | ✅ | D2C snacks, drinks, toys, pet goods. Packaging illustration extends naturally onto the web. |
| Editorial | ➖ | Good for kids' media or a playful magazine. Long reading needs calmer pages. |
| Nonprofit | ✅ | Charity games and campaigns (Captain Goosebumps) make heavy topics approachable. Mind the tone on serious causes. |
| Event | ✅ | Festivals, family events, game launches. |
| Personal | ➖ | Fun for side projects. Hard to sustain without real illustration skill. |
| Kids / education / games | ✅ | The home turf. Baby-schema characters and gamified feedback are proven here. |

---

## 4. Visual DNA

### Typography
- **Display:** chunky, soft-cornered, high-x-height faces set tight and big (clamp 3.5rem → 11vw), often with an outline or an offset "ghost" duplicate.
  - Commercial: Cooper Black / Cooper Std (Mailchimp's wordmark basis), Recoleta, GT Walsheim Ultra, Feather Bold (custom for Duolingo), Ruder Plakat (Ink Games).
  - Free on Google Fonts: **Bagel Fat One**, **Chango**, **Rubik Mono One**, **Bricolage Grotesque 800 (condensed)**, **Fredoka 700** (overused, avoid unless twisted), **Grandstander 900**, **Cherry Bomb One**, **Modak**.
- **Body/UI:** a friendly geometric or humanist sans at 17–19 px with generous line-height (1.5–1.6): **Figtree**, **Bricolage Grotesque 400–600**, **Nunito Sans**, **DM Sans**, **Libre Franklin** (Ponpon Mania).
- **Annotation/"hand" voice:** **Shantell Sans** (it has an informal axis), **Gochi Hand**, **Caveat Brush**. Use it for arrows, margin notes and price tags, never for paragraphs.
- **Moves:** mixed-case wordmarks with one letter dropped below the baseline (Ponpon Mania's "n"), a rotated price tag at -6°, text set on a circular path for badges.

### Colour
- 4–6 saturated hues + **one dark "ink" colour that is not pure black** (aubergine, navy or deep brown) for outlines and text + a warm off-white paper colour.
- Example palette (used in the demo):

| Role | Hex | Note |
|---|---|---|
| Paper | `#FFF4E0` | warm cream, not white |
| Ink | `#2A1740` | aubergine, used for every outline and all body text |
| Butter | `#FFC93C` | sunshine primary (compare Mailchimp's Cavendish Yellow) |
| Tomato | `#FF5B3A` | energy, CTA fill (with ink text, never white) |
| Bubblegum | `#FF8CC6` | secondary, cheeks, highlights |
| Grape | `#7B4DFF` | depth colour for blob rings and night scenes |
| Mint | `#28C2A0` | freshness, success states |

- **Logic:** analogous warm runs (butter → tomato → bubblegum) for rings and gradients, and one complementary cool (grape or mint) for depth. Saturation stays high; the ink colour holds contrast.

### Layout and grid
- **A free collage over a simple grid:** a 12-column grid underneath, but illustrations break it (overlap section edges, peek from behind cards, sit on the fold line).
- **Shaped sections:** wavy SVG dividers, arched windows, blob-masked images, and cards with 24–40 px radii.
- **Marquee frames and tickers** for repeating slogans (Crumbskees).
- **The sticker layer:** absolutely positioned badges at small rotations (-8° to +8°), drop-shadowed with a hard offset (`4px 6px 0 var(--ink)`).

### Imagery and art direction
- **A mascot built on baby-schema proportions:** a large head-to-body ratio, big low-set eyes, small nose and mouth, round silhouette (Lorenz 1943; Glocker et al. 2009). Give it 3–5 expressions (idle, happy, surprised, sleepy, oops) and reuse it in empty states, 404 pages, loaders and success screens.
- **A consistent line language:** pick ONE of (a) thick uniform ink outline with flat fills (Ponpon, Crumbskees, Meow Mart), (b) no outline, with grain-gradient shapes (Captain Goosebumps, Headspace), or (c) 3D toy render (ToyFight). Mixing them looks like stock assets.
- **Props and confetti:** a small set (5–8) of brand-specific doodles (food, tools, stars) scattered sparsely.

### Motion and interaction
- **Spring easing everywhere:** overshoot curves (`cubic-bezier(.34,1.56,.64,1)`) or CSS `linear()` springs; 350–600 ms for UI, longer for characters.
- **Idle life:** the mascot blinks every 3–6 s (randomised), breathes (scaleY 1 → 1.02) and its eyes follow the pointer.
- **Squash and stretch** on press: buttons collapse their 3D lip and characters squash to `scale(1.15, .85)` and then rebound.
- **Reward moments:** confetti or sticker bursts on add-to-cart or sign-up, and a mascot reaction on form success.
- **Drag-and-play toys:** draggable stickers, a "pet the mascot" interaction, tilt-on-hover cards.

### Micro-details
- A custom cursor that becomes a hand or a sticker on interactive items (keep the native cursor for text).
- Hard offset shadows instead of blurred ones, and 2.5–4 px ink borders.
- Wobbly SVG strokes (`feTurbulence` + `feDisplacementMap` at a low scale) for hand-drawn edges.
- Easter eggs: Konami code, a mascot that falls asleep after 30 s idle, a console.log greeting.

---

## 5. Why it works

### The visceral hook
Norman (2004, *Emotional Design*) splits design response into visceral, behavioural and reflective levels. Saturated colour, round shapes and faces act at the **visceral** level: they are judged pre-consciously within the 50 ms first-impression window that Lindgaard et al. (2006) measured (see `00_Research/`).

### Roundness is liked
Bar & Neta (2006, "Humans prefer curved visual objects", *Psychological Science*) found that sharp-angled objects are liked less than curved ones, which supports chunky rounded type and blobs.

### Cuteness changes behaviour
- Lorenz's *Kindchenschema* (1943) describes baby-schema features: a large head, big eyes and a round face.
- Glocker et al. (2009, "Baby schema in infant faces induces cuteness perception and motivation for caretaking in adults", *Ethology*) showed that these features raise both perceived cuteness and the motivation to care for the face.
- Nittono, Fukushima, Yano & Moriya (2012, "The power of Kawaii: Viewing cute images promotes a careful behavior and narrows attentional focus", *PLoS ONE* 7(9): e46362) found that people did fine-motor and visual-search tasks *more carefully* after viewing baby-animal images.
- Implication: a cute mascot near a tricky form or onboarding step is not just decoration.

### Mascots and anthropomorphism
- Epley, Waytz & Cacioppo (2007, "On seeing human: A three-factor theory of anthropomorphism", *Psychological Review*) explain why people readily attribute minds to non-human agents.
- Aggarwal & McGill (2007, "Is that car smiling at me? Schema congruity as a basis for evaluating anthropomorphized products", *Journal of Consumer Research*) showed that anthropomorphised products are evaluated more positively when the human schema fits.
- A mascot gives the brand a social face. Users forgive an error message when a character says it.

### Colour and arousal
- Valdez & Mehrabian (1994, "Effects of color on emotions", *Journal of Experimental Psychology: General*) found that **saturation and brightness drive arousal and pleasure** more than hue. Saturated colour is energising; brighter colour is more pleasant.
- Labrecque & Milne (2012, "Exciting red and competent blue", *JAMS*) link saturated warm hues to an "exciting" brand personality.

### Gamification and delight
- Deterding, Dixon, Khaled & Nacke (2011, "From game design elements to gamefulness: defining gamification", *MindTrek*) define gamification.
- Hamari, Koivisto & Sarsa (2014, "Does gamification work? A literature review of empirical studies on gamification", *HICSS*) found mostly positive but context-dependent effects.
- Award juries consistently reward branded games here (Meow Mart, Captain Goosebumps, Chocapic).

### The expert view
Aarron Walter (2011, *Designing for Emotion*) argues that a "personality layer" on top of a usable base is what makes products memorable. That is exactly the Mailchimp/Freddie model.

### What juries reward
On Awwwards, Creativity is 20 % of the score and Design 40 %. Playful SOTDs win when the illustration is **original and narratively used** (a story, game or toy) rather than spot illustrations in a template. Every winner above has a mechanic (play, read, slide, dodge), not just pictures.

---

## 6. Uniqueness levers
1. **Derive the type from the mascot:** one glyph quirk borrowed from the character's anatomy (a leaf terminal, a fang serif, an ear on the "i").
2. **Make the brand promise a toy:** a draggable, squishable or feedable mechanic that *demonstrates* the product (the Captain Goosebumps colour-restore idea).
3. **A non-black ink colour** for every outline and all text (aubergine, navy, chocolate). It instantly reads as custom.
4. **A shaped viewport:** arched, blob or ticket-shaped hero windows instead of full-bleed rectangles.
5. **Marquee frames:** a looping slogan border around the whole page or the hero.
6. **One rule-breaking scale moment:** a mascot 2× the viewport height peeking from the bottom, or a wordmark bleeding off both edges.
7. **Mascot as system UI:** it appears in the loader, empty cart, 404 page, form errors and cookie banner, each with a different expression.
8. **Seasonal or contextual moods:** the mascot reacts to the time of day, scroll speed or idle time (it falls asleep).
9. **Sticker economy:** collectable badges awarded for scrolling sections or finding easter eggs.
10. **Physical sound design (opt-in):** squeaks and pops, muted by default with a visible toggle.

---

## 7. Clichés and pitfalls
- **"Corporate Memphis" / Alegria people:** flat purple humans with tiny heads and giant limbs. This is the single biggest "template" tell.
- Stock 3D emoji blobs and generic Spline "clay" shapes with no character.
- Fredoka or Baloo plus a rainbow gradient plus confetti on every click.
- Bouncy animation on *everything*. Constant motion becomes noise; reserve springs for meaningful state changes.
- A mascot that only appears in the hero. If it does not recur, it is clip art.
- White text on saturated yellow, coral or mint (it fails WCAG). Use the ink colour on light saturated fills.
- Mixed illustration styles (outlined icons next to grain-gradient scenes next to 3D renders).
- Copying a famous character's silhouette or proportions too closely, such as owls, chimps and blob monks. Originality is also an IP issue.

---

## 8. Accessibility and performance notes
- **Contrast:** use `#2A1740` (or similar) ink on cream, butter, bubblegum or mint fills; these pass AA. Tomato `#FF5B3A` needs ink text (≈5.3 : 1), not white (≈3 : 1).
- **Motion:** wrap springs, wobbles, marquees and confetti in `@media (prefers-reduced-motion: no-preference)`. Keep the eye-follow (it is subtle) but stop idle bobbing. Provide a pause control for any marquee longer than 5 s (WCAG 2.2.2).
- **Mascot SVGs** need `role="img"` and a short `aria-label`, or `aria-hidden="true"` when decorative. Do not let the mascot be the only carrier of meaning (for example, a sad face for an error must come with error text).
- **Drag toys** need a keyboard equivalent (arrow keys or buttons) and must not trap focus.
- **Performance:** inline SVG over PNG for characters (they are small and recolourable). Lottie and Rive files can be heavy, so lazy-load them below the fold. Avoid giant transparent PNG sticker sheets.
- **Sound** is off by default, with a visible toggle.

---

## 9. Neighbouring styles and hybrids
- **+ EW-2 Retro-Nostalgic:** a pixel or 8-bit mascot (Chocapic Nutri-Game), or 70s cartoon rubber-hose characters. It is the most natural blend.
- **+ CW-2 Warm-Organic:** grain-gradient, paper-cut, pastel playful (Headspace, Fruitful, Captain Goosebumps). The calm, wellness-friendly end.
- **+ EC-1 Immersive-Experimental:** WebGL toy worlds, physics playgrounds and 3D mascots (Bruno-Simon-style driving portfolios).
- **+ EC-2 Brutalist-Raw:** raw HTML layouts with crude, MS-Paint-style doodles. A Gen-Z streetwear and indie-game vibe.
- **+ CC-3 Tech-Product:** a friendly SaaS with a strict product UI plus a mascot in empty states and onboarding (the Mailchimp model).
- **Avoid with CW-1 Luxury-Refined:** mascots and saturated colour fight luxury's restraint, except for ironic limited drops.
