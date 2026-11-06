# Principles cheatsheet: 36 evidence-based rules

Every generated design should respect these, whatever the style. Sources are in `academic-findings.md` and `bibliography.md`.

## A. First impression (the 50 ms window)
1. **The hero must work as a still image.** It is judged in 17–50 ms, before animation or reading. *(Lindgaard et al., 2006; Tuch et al., 2012)*
2. **Commit to one clear style.** Unambiguous designs are judged faster and more consistently. *(Tractinsky et al., 2006)*
3. **Keep perceived complexity low-to-moderate in the first viewport:** ≤ 1 headline (≤ 12 words), 1 subline, ≤ 2 CTAs, 1 key visual, ≤ 6 nav items. *(Reinecke et al., 2013; Tuch et al., 2009; Michailidou et al., 2008)*
4. **Value proposition, style signature and one proof point within the first two screens.** About 57% of viewing time is above the fold and 74% within two screenfuls. *(Fessenden, 2018)*
5. **Let the audience set the dials.** Expert, older or highly educated audiences get less colour and complexity. Young consumer audiences get more imagery and less text. *(Reinecke & Gajos, 2014; Djamasbi et al., 2010)*

## B. Novelty vs familiarity
6. **Keep the page structure prototypical for the genre.** Shops look like shops, SaaS like SaaS. *(Tuch et al., 2012)*
7. **MAYA: prototypical structure + 2–3 committed novel moves.** Not zero, not ten. *(Hekkert et al., 2003)*
8. **One loud thing per screen.** Arousal has an inverted-U optimum, so do not stack effects. *(Berlyne, 1970, 1971)*
9. **Get novelty from craft and concept, not from element count.** Complexity alone lowers pleasure on websites. *(Tuch et al., 2009)*
10. **Make the surprise comprehensible.** Interest = novel + understandable, so give clear cues (scroll hint, readable nav, exit from 3D). *(Silvia, 2005)*
11. **Make the style recognisable and coherent.** Expert viewers (juries) reward a style they can classify and see mastered. *(Leder et al., 2004)*

## C. Classical skeleton, expressive skin
12. **Navigation, forms and checkout stay classical** (clear, clean, symmetric), whatever the style. Perceived usability tracks classical aesthetics. *(Lavie & Tractinsky, 2004)*
13. **Spend expressiveness on hero, art direction, transitions and typography**, not on controls. *(Lavie & Tractinsky, 2004; Hassenzahl & Monk, 2010)*
14. **Beauty buys perceived usability, but only as a starting credit.** Pair every flourish with a visible affordance. *(Kurosu & Kashimura, 1995; Tractinsky et al., 2000)*
15. **Invest in visual polish even for "boring" products.** Aesthetics can improve task performance. *(Moshagen et al., 2009; Sonderegger & Sauer, 2010)*
16. **State the identity promise.** Beauty follows hedonic identification ("what using this says about me"). *(Hassenzahl, 2004)*

## D. Craftsmanship (the universal floor)
17. **One spacing scale** (e.g. 4/8-pt multiples), **one radius family, one shadow system.** Craftsmanship is a separate facet of perceived aesthetics. *(Moshagen & Thielsch, 2010)*
18. **Design every state:** hover, focus-visible, active, disabled, loading, empty, error. *(Moshagen & Thielsch, 2010; WCAG 2.2)*
19. **Real-feeling content, never lorem ipsum.** "Design look" is the top credibility cue, and content is scored. *(Fogg et al., 2003; Thielsch et al., 2014; Awwwards Content 10%)*
20. **Use symmetry and alignment as defaults; break them in one deliberate place.** *(Bauerly & Liu, 2006; Ngo et al., 2003)*

## E. Colour
21. **Saturation is the arousal dial and lightness is the calm dial.** Hue matters less. Specify palettes in OKLCH with explicit chroma bands. *(Valdez & Mehrabian, 1994; Gorn et al., 1997)*
22. **Temperature lives in hue angle, chroma and tinted neutrals.** Cool: neutrals tinted toward blue (OKLCH hue ~230–260). Warm: toward yellow-orange (~60–90). *(Ou et al., 2004)*
23. **Derive the palette from the brand personality:** blue → competence; red/orange → excitement; dark and desaturated → sophistication; yellow/warm light → sincerity; brown/olive → ruggedness. *(Labrecque & Milne, 2012; Aaker, 1997)*
24. **Colour meaning depends on context.** Avoid red for non-error UI in high-stakes flows, and test lightness and chroma, not just hue. *(Elliot & Maier, 2014)*
25. **Anchor earthy colours to appealing referents** (wood, bread, clay, foliage) through imagery and texture. *(Palmer & Schloss, 2010)*
26. **Palette structure: 1 dominant + neutrals + 1 accent** (Expressive-Warm may add a second accent). Colour appeal drives trust. *(Reinecke et al., 2013; Cyr et al., 2010)*

## F. Contrast and readability
27. **Body text contrast ≥ 4.5:1; large text and UI components ≥ 3:1.** Higher contrast also raises liking through fluency. *(WCAG 2.2 SC 1.4.3, 1.4.11; Reber et al., 1998; Hall & Hanna, 2004)*
28. **Body text ≥ 16 px (18–20 px for editorial or older audiences); line-height 1.4–1.6.** *(Bernard et al., 2001; Bringhurst, 2004)*
29. **Measure: `max-width: 60–75ch` for paragraphs.** Only display type may break it. *(Dyson & Haselgrove, 2001; Bringhurst, 2004)*

## G. Typography
30. **Choose a typeface persona first, then the family:** *elegance* (Luxury, Swiss), *friendliness* (Playful, Organic), *directness* (Corporate, Tech, Brutalist). *(Brumberger, 2003a)*
31. **Typeface must fit the brand.** Congruence improves brand memory and choice. Novel fonts are a lever only if their connotation fits. *(Childers & Jass, 2002; Doyle & Bottomley, 2004; Brumberger, 2003b)*
32. **Tune impressions with type design:** harmonious and natural = *reassuring*; elaborate and flourished = *engaging*; heavy and compressed = *prominent*. *(Henderson et al., 2004)*
33. **Use a modular type scale:** ratio 1.2–1.25 (Classical and app UI) or 1.333–1.618 (Expressive and editorial display). Display line-height 0.9–1.1. Max 2 families (+ 1 mono). *(Bringhurst, 2004; Reber et al., 2004 on consistency and fluency)*

## H. Layout and reading
34. **Design for layer-cake scanning:** information-rich headings, key words first, bullets, bolded key terms, important content in the first two paragraphs. *(Nielsen, 2006; Pernice, 2017)*
35. **Force the reading order with hierarchy** (size → contrast → position), not with assumed F or Z patterns. Scanpaths vary by person and page type. *(Pan et al., 2004)*

## I. Warmth × competence
36. **Always show the missing half.** Cool styles add one warmth cue (people, friendly microcopy). Warm and NGO styles add one competence cue (hard numbers, credentials, crisp data). *(Fiske et al., 2007; Aaker et al., 2010; Kervyn et al., 2012)*

## J. Motion, performance, accessibility (jury floor)
- **Honour `prefers-reduced-motion`.** Animate only `transform`/`opacity`. UI transitions 150–250 ms; cinematic 600–1200 ms. *(WCAG 2.2 SC 2.3.3; Awwwards Developer Award ◐)*
- **LCP ≤ 2.5 s, INP ≤ 200 ms, CLS ≤ 0.1.** Give WebGL a static poster fallback. *(Google Core Web Vitals; Webby Functionality)*
- **Target size ≥ 24×24 px; focus never hidden by sticky headers.** *(WCAG 2.2 SC 2.5.8, 2.4.11)*

---

### The 60-second self-critique (paste at the end of any prompt)
1. **Lavie & Tractinsky 10 items (1–7):** clear, clean, symmetric, pleasant, aesthetic | creative, original, fascinating, sophisticated, special effects. Target pole ≥ 6, other pole ≥ 4.
2. **VisAWI-S (1–7):** structure · variety · colour composition · craftsmanship. Fix the lowest.
3. **MAYA:** is the structure prototypical? Can I name exactly 2–3 novel moves?
4. **Warmth × competence:** is the missing half present?
5. **Floor:** WCAG AA contrast, 375 px layout, reduced motion, CWV budget, no lorem ipsum.
6. **Juror score:** Design/Usability/Creativity/Content at 40/30/20/10. If < 7.5, fix the top 3 issues.
