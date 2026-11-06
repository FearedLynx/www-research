# Academic findings: the evidence base for the style library

Every source below was checked against Crossref (api.crossref.org) or the publisher / author page for authors, year, title, venue and DOI. **✔ verified** means the bibliographic record was confirmed. Where I read the full text (Lavie & Tractinsky 2004), the summary goes into more detail. Method and finding summaries come from abstracts, publisher pages or the full text. Each entry ends with **Design implication for prompts**: something an LLM can actually act on.

Full APA references: `bibliography.md`. How these feed the style map: `taxonomy.md`.

---

## Contents
1. [First impressions: the 50 ms window](#1-first-impressions-the-50-ms-window)
2. [Aesthetic dimensions: classical vs expressive, VisAWI](#2-aesthetic-dimensions-the-backbone)
3. [Aesthetics and usability](#3-aesthetics-and-usability)
4. [Complexity, prototypicality, novelty, fluency](#4-complexity-prototypicality-novelty-and-fluency)
5. [Colour](#5-colour)
6. [Warmth, competence and brand personality](#6-warmth-competence-and-brand-personality)
7. [Typography](#7-typography)
8. [Layout, attention and reading](#8-layout-attention-and-reading)
9. [Kansei engineering](#9-kansei-engineering)
10. [Standards used as hard constraints](#10-standards-used-as-hard-constraints)
11. [Unverified or dropped leads](#11-unverified-or-dropped-leads)

---

## 1. First impressions: the 50 ms window

### Lindgaard, Fernandes, Dudek & Brown (2006) ✔ verified
**Citation:** Lindgaard, G., Fernandes, G., Dudek, C., & Brown, J. (2006). Attention web designers: You have 50 milliseconds to make a good first impression! *Behaviour & Information Technology, 25*(2), 115–126. https://doi.org/10.1080/01449290500330448
**Method:** Three studies. Participants rated homepages for visual appeal after brief exposures, the last at **50 ms**, and those ratings were compared with ratings made after longer viewing.
**Key finding:** Visual-appeal judgments formed in 50 ms correlated strongly with judgments made with more time. Appeal is decided almost pre-attentively, before any content is read.
**Design implication for prompts:** The first viewport has to work as a *static image*. Tell the model: "The hero must communicate the brand's personality as a still frame, before any animation runs, text is read or a scroll happens." Never let the hero depend on a loader or an intro animation to look good.

### Tractinsky, Cokhavi, Kirschenbaum & Sharfi (2006) ✔ verified
**Citation:** Tractinsky, N., Cokhavi, A., Kirschenbaum, M., & Sharfi, T. (2006). Evaluating the consistency of immediate aesthetic perceptions of web pages. *International Journal of Human-Computer Studies, 64*(11), 1071–1083. https://doi.org/10.1016/j.ijhcs.2006.06.009
**Method:** A replication and extension of Lindgaard et al. Web-page screenshots were rated after ~500 ms exposure and after unlimited exposure, and response latencies were recorded.
**Key finding:** Immediate aesthetic impressions were highly consistent with considered ones and stable across repeated exposures. Extreme (very attractive or very unattractive) pages were judged faster.
**Design implication for prompts:** Aim for an *unambiguous* aesthetic signal. A clearly committed style is judged faster and more consistently than a hedged mix. In prompts: "Commit to one style. Do not average two."

### Reinecke, Yeh, Miratrix, Mardiko, Zhao, Liu & Gajos (2013) ✔ verified
**Citation:** Reinecke, K., Yeh, T., Miratrix, L., Mardiko, R., Zhao, Y., Liu, J., & Gajos, K. Z. (2013). Predicting users' first impressions of website aesthetics with a quantification of perceived visual complexity and colorfulness. In *Proceedings of CHI '13* (pp. 2049–2058). ACM. https://doi.org/10.1145/2470654.2481281
**Method:** 548 volunteers rated 450 websites for colourfulness, visual complexity and appeal after **500 ms**. The authors built computational models of perceived complexity (e.g. number of text/image areas, quadtree decomposition) and colourfulness (colour metrics in HSV/LAB).
**Key finding:** Perceived complexity and colourfulness together explained about half the variance in first-impression appeal. Appeal peaked at **low-to-moderate complexity** and **moderate colourfulness**, and the optimum shifted with demographics.
**Design implication for prompts:** Put a number on complexity. For a first viewport: "at most 1 headline, 1 supporting line, 1–2 CTAs, 1 visual. Keep it to roughly 5–7 distinct visual groups." Use a restrained palette (1 dominant hue + neutrals + 1 accent) unless the style is deliberately Expressive-Warm.

### Reinecke & Gajos (2014) ✔ verified
**Citation:** Reinecke, K., & Gajos, K. Z. (2014). Quantifying visual preferences around the world. In *Proceedings of CHI '14* (pp. 11–20). ACM. https://doi.org/10.1145/2556288.2557052
**Method:** An online LabintheWild study: ~2.4 million ratings of visual appeal from almost 40,000 participants of diverse backgrounds, on 430 websites.
**Key finding:** Preferences for colourfulness and complexity vary systematically with country, age, gender and education. Higher education tended to lower the preference for colourfulness. Russians, for example, preferred lower complexity, and Macedonians liked highly colourful sites more than any other group in the dataset.
**Design implication for prompts:** `{{AUDIENCE}}` is not decoration. It should move the complexity and colour sliders. Add to prompts: "Adjust colourfulness and density to the audience. Highly educated, professional or older audiences get lower colourfulness; youth and consumer audiences can go higher."

### Lindgaard, Dudek, Sen, Sumegi & Noonan (2011) ✔ verified
**Citation:** Lindgaard, G., Dudek, C., Sen, D., Sumegi, L., & Noonan, P. (2011). An exploration of relations between visual appeal, trustworthiness and perceived usability of homepages. *ACM Transactions on Computer-Human Interaction, 18*(1), Article 1, 1–30. https://doi.org/10.1145/1959022.1959023
**Method:** Several experiments comparing very brief (50 ms) and longer exposures with judgments of visual appeal, trustworthiness and perceived usability.
**Key finding:** Visual appeal is judged fastest and drives early perceptions of trust and usability. Trust and usability judgments need more exposure to stabilise.
**Design implication for prompts:** For trust-critical purposes (finance, health, NGO), the first screen has to *look* trustworthy (clean, aligned, classical cues), and trust evidence (logos, numbers, certifications) must appear within the first two screens.

### Fogg, Soohoo, Danielson, Marable, Stanford & Tauber (2003) ✔ verified
**Citation:** Fogg, B. J., Soohoo, C., Danielson, D. R., Marable, L., Stanford, J., & Tauber, E. R. (2003). How do users evaluate the credibility of Web sites? A study with over 2,500 participants. In *Proceedings of DUX '03* (pp. 1–15). ACM. https://doi.org/10.1145/997078.997097
**Method:** A large online study. Participants compared site pairs on credibility and wrote comments, which were then coded.
**Key finding:** "Design look" was the most frequently mentioned credibility cue, ahead of information structure and focus.
**Design implication for prompts:** Visual polish *is* credibility. Require craftsmanship details (consistent spacing scale, aligned baselines, real-looking content, no lorem ipsum) in every generated page.

### Thielsch, Blotenberg & Jaron (2014) ✔ verified
**Citation:** Thielsch, M. T., Blotenberg, I., & Jaron, R. (2014). User evaluation of websites: From first impression to recommendation. *Interacting with Computers, 26*(1), 89–102. https://doi.org/10.1093/iwc/iwt033 (Crossref lists the online-first year as 2013.)
**Method:** A field study linking first-impression ratings, later evaluations of content, usability and aesthetics, and intention to revisit or recommend.
**Key finding:** First impressions carried over into later evaluations. Aesthetics, content and usability all contributed to revisit and recommendation intentions.
**Design implication for prompts:** A beautiful hero does not save poor content. The prompt must ask for real, specific copy and a clear information structure, not only visuals.

### Papachristos & Avouris (2011) ✔ verified
**Citation:** Papachristos, E., & Avouris, N. (2011). Are first impressions about websites only related to visual appeal? In *INTERACT 2011, LNCS 6946* (pp. 489–496). Springer. https://doi.org/10.1007/978-3-642-23774-4_40
**Method:** Brief-exposure ratings of websites on several emotional and affective attributes, not only appeal.
**Key finding:** Within short exposures users also form impressions of attributes beyond overall appeal (for example how pleasant, professional or modern a site is).
**Design implication for prompts:** Specify the *target impression words* (e.g. "precise, calm, premium") in the prompt and have the model check the hero against them. This is effectively a mini-Kansei brief (see §9).

---

## 2. Aesthetic dimensions: the backbone

### Lavie & Tractinsky (2004) ✔ verified (full text read)
**Citation:** Lavie, T., & Tractinsky, N. (2004). Assessing dimensions of perceived visual aesthetics of web sites. *International Journal of Human-Computer Studies, 60*(3), 269–298. https://doi.org/10.1016/j.ijhcs.2003.09.002 (author PDF: https://www.ise.bgu.ac.il/faculty/noam/papers/04_tl_nt_ijhcs.pdf)

**Why it matters here:** This paper is the source of the library's primary axis **Classical ↔ Expressive**.

**Method in detail (four studies):**
| Stage | Sample | Stimulus | Analysis | Outcome |
|---|---|---|---|---|
| Item generation | Literature review + 11 experts (4 web designers, 4 HCI researchers, 2 interior designers, 1 architect) listing adjectives of aesthetics | – | Duplicates and opposites removed | **41 adjectives** |
| Study 1 | 125 engineering students | times.com or universalusability.org | Exploratory factor analysis (maximum likelihood, oblique rotation), 7-point agree scale; scree test and parallel analysis | 8 eigenvalues > 1, but scree and parallel analysis pointed to **2 factors**; items pruned and new ones added → 35 items |
| Study 2 | 212 undergraduates | Gap.com or Macys.com after a shopping task | EFA | A simple 2-factor structure: "well organized, clear, clean, symmetrical" vs "original, fascinating, using special effects" |
| Study 3 | 145 students | An Israeli restaurant-guide site | EFA together with usability, pleasure, playfulness and service-quality items | The 2 aesthetic factors again (55.7% of variance) |
| Study 4 | 384 ordinary web users recruited on 5 Israeli portals; split-sample cross-validation | The site where they saw the recruitment ad | Confirmatory factor analysis (AMOS) | Final **5 + 5 item** scales, good fit, factors correlated ≈ .6 but distinct |

**The final items (7-point scale):**
| Classical aesthetics | Expressive aesthetics |
|---|---|
| Aesthetic design | Creative design |
| Pleasant design | Fascinating design |
| Clear design | Use of special effects |
| Clean design | Original design |
| Symmetric design | Sophisticated design |

Both scales had α ≈ .85–.87.

**Key findings:**
- Users' aesthetic perception splits into **classical aesthetics** (order, clarity, the pre-Romantic ideals of proportion; it matches Nasar's "visual clarity") and **expressive aesthetics** (the designer's creativity, originality, ability to *break conventions*; it matches Nasar's "visual richness").
- **Perceived usability correlated much more strongly with classical than with expressive aesthetics.** Some items, such as "clear design", load on both classical aesthetics and usability.
- **Pleasure correlated with both dimensions** at similar levels (slightly higher for classical).
- There were no meaningful age or gender effects on either dimension.

**Design implication for prompts:**
1. Every style must declare its position on this axis. A Classical style optimises for *clear, clean, symmetric, pleasant*; an Expressive style optimises for *original, fascinating, sophisticated, special effects*.
2. Because usability tracks *classical* aesthetics, **an Expressive design must keep a Classical skeleton for navigation, forms and checkout**: be expressive in the hero, art direction and transitions, and classical in the controls.
3. Use the ten items as a **self-critique rubric** in every PROMPT.md: "Rate your output 1–7 on clear, clean, symmetric, pleasant (classical) and creative, original, fascinating, sophisticated, special effects (expressive). The target style needs ≥ 6 on its own pole and ≥ 4 on the other."

### Moshagen & Thielsch (2010): VisAWI ✔ verified
**Citation:** Moshagen, M., & Thielsch, M. T. (2010). Facets of visual aesthetics. *International Journal of Human-Computer Studies, 68*(10), 689–709. https://doi.org/10.1016/j.ijhcs.2010.05.006
**Method:** Seven studies developing and validating the *Visual Aesthetics of Websites Inventory* (VisAWI): 18 items, 4 facets.
**Key finding:** Perceived website aesthetics has four related but distinct facets:
- **Simplicity**: clarity, orderliness, structure (≈ classical)
- **Diversity**: variety, novelty, creativity, dynamism (≈ expressive)
- **Colourfulness**: the appeal and harmony of colour combinations
- **Craftsmanship**: skilful, coherent, up-to-date execution with care for detail
**Design implication for prompts:** VisAWI adds two dimensions that Lavie & Tractinsky do not isolate. **Colour** is the material for our Cool↔Warm axis, and **craftsmanship** is the quality bar for *every* style, Brutalist included. Add to every prompt: "Craftsmanship is non-negotiable: one spacing scale, consistent radii, aligned baselines, intentional states (hover, focus, active, disabled), no orphaned elements."

### Moshagen & Thielsch (2013): VisAWI-S ✔ verified
**Citation:** Moshagen, M., & Thielsch, M. T. (2013). A short version of the visual aesthetics of websites inventory. *Behaviour & Information Technology, 32*(12), 1305–1311. https://doi.org/10.1080/0144929X.2012.694910
**Method:** A 4-item short form, one item per facet, validated against the full VisAWI.
**Key finding:** Four items reproduce the full scale well enough for quick evaluation.
**Design implication for prompts:** A cheap critique loop: "Score your design 1–7 on (1) clear structure, (2) varied and interesting, (3) attractive colour composition, (4) professionally made. Fix the lowest score before finishing."

### Seckler, Opwis & Tuch (2015) ✔ verified
**Citation:** Seckler, M., Opwis, K., & Tuch, A. N. (2015). Linking objective design factors with subjective aesthetics: An experimental study on how structure and color of websites affect the facets of users' visual aesthetic perception. *Computers in Human Behavior, 49*, 375–389. https://doi.org/10.1016/j.chb.2015.02.056
**Method:** An experiment that systematically varied structural properties (e.g. symmetry, balance, alignment) and colour properties of websites and measured the VisAWI facets.
**Key finding:** Structural manipulations mainly affected the *simplicity* facet, colour manipulations mainly affected *colourfulness*, and both influenced overall aesthetics.
**Design implication for prompts:** Classical↔Expressive (structure) and Cool↔Warm (colour) can be tuned *independently*, which justifies treating them as orthogonal axes. In prompts, specify grid and alignment rules separately from colour rules.

### Bauerly & Liu (2006) ✔ verified
**Citation:** Bauerly, M., & Liu, Y. (2006). Computational modeling and experimental investigation of effects of compositional elements on interface and design aesthetics. *International Journal of Human-Computer Studies, 64*(8), 670–682. https://doi.org/10.1016/j.ijhcs.2006.01.002
**Method:** Abstract compositions and web-like layouts varied in symmetry and number of elements were rated for aesthetics, and a computational model was fitted.
**Key finding:** Symmetry, especially vertical-axis symmetry, raised aesthetic ratings. More elements tended to lower them, and the effects interacted.
**Design implication for prompts:** Classical styles: use a centred or mirrored hero and balanced columns. Expressive styles can break symmetry, but only on purpose: "Break symmetry in exactly one place per screen."

### Ngo, Teo & Byrne (2003) ✔ verified
**Citation:** Ngo, D. C. L., Teo, L. S., & Byrne, J. G. (2003). Modelling interface aesthetics. *Information Sciences, 152*, 25–46. https://doi.org/10.1016/S0020-0255(02)00404-8
**Method:** Proposed 14 computable layout measures (balance, equilibrium, symmetry, sequence, cohesion, unity, proportion, simplicity, density, regularity, economy, homogeneity, rhythm, order and complexity) and compared them with human ratings.
**Key finding:** The formal measures related to perceived screen aesthetics.
**Design implication for prompts:** Name the formal properties you want: "strong *alignment* and *regularity* (classical)" versus "deliberate *rhythm* changes and asymmetric *balance* (expressive)." These words direct an LLM better than vague words like "modern".

---

## 3. Aesthetics and usability

### Kurosu & Kashimura (1995) ✔ verified
**Citation:** Kurosu, M., & Kashimura, K. (1995). Apparent usability vs. inherent usability: Experimental analysis on the determinants of the apparent usability. In *CHI '95 Conference Companion* (pp. 292–293). ACM. https://doi.org/10.1145/223355.223680
**Method:** Participants rated 26 ATM interface layouts for beauty and for how usable they appeared.
**Key finding:** *Apparent* usability correlated more strongly with aesthetic appeal than with *inherent* usability. This is the origin of the "aesthetic-usability effect".
**Design implication for prompts:** Looks shape perceived ease of use. This lets you raise beauty, but it is not a licence to hide controls. Pair every visual flourish with an explicit usable affordance.

### Tractinsky, Katz & Ikar (2000) ✔ verified
**Citation:** Tractinsky, N., Katz, A. S., & Ikar, D. (2000). What is beautiful is usable. *Interacting with Computers, 13*(2), 127–145. https://doi.org/10.1016/S0953-5438(00)00031-X
**Method:** A field-style experiment with ATM layouts varying in aesthetics and in actual usability. Perceptions were measured before and after use.
**Key finding:** Perceived aesthetics before use predicted perceived usability *after* use. Actual usability manipulations had little effect on post-use perceptions.
**Design implication for prompts:** The aesthetic halo is real and survives use. It justifies investing prompt budget in visual quality even for "boring" products (B2B, government).

### Hassenzahl (2004) ✔ verified
**Citation:** Hassenzahl, M. (2004). The interplay of beauty, goodness, and usability in interactive products. *Human-Computer Interaction, 19*(4), 319–349. https://doi.org/10.1207/s15327051hci1904_2
**Method:** Studies with MP3-player skins and other products measuring beauty, overall goodness, pragmatic quality and hedonic quality (identification, stimulation), before and after use.
**Key finding:** **Beauty** was linked mainly to *hedonic identification* (what the product says about me). **Goodness** was linked to *pragmatic quality* (usability). Beauty judgments were stable after use, while goodness judgments shifted with experience.
**Design implication for prompts:** Brand identity (who the user becomes by using this) drives beauty, so the prompt must state the *identity promise* ("users should feel like insiders at a design-literate studio"). Usability drives *goodness*, so specify the core task flow too.

### Hassenzahl, Burmester & Koller (2003): AttrakDiff ✔ verified
**Citation:** Hassenzahl, M., Burmester, M., & Koller, F. (2003). AttrakDiff: Ein Fragebogen zur Messung wahrgenommener hedonischer und pragmatischer Qualität. In *Mensch & Computer 2003* (pp. 187–196). Vieweg+Teubner. https://doi.org/10.1007/978-3-322-80058-9_19
**Method:** A semantic-differential questionnaire (word pairs) measuring pragmatic quality (PQ), hedonic quality–identity (HQ-I), hedonic quality–stimulation (HQ-S) and attractiveness (ATT).
**Key finding:** Pragmatic and hedonic quality are separable and both feed attractiveness.
**Design implication for prompts:** Map the styles: Classical styles lead with **PQ** (simple, practical, predictable). Expressive styles lead with **HQ-S** (novel, creative, captivating). Luxury and brand-led styles lead with **HQ-I** (professional, stylish, premium, presentable). Use AttrakDiff word pairs as target adjectives.

### Hassenzahl & Tractinsky (2006) ✔ verified
**Citation:** Hassenzahl, M., & Tractinsky, N. (2006). User experience: A research agenda. *Behaviour & Information Technology, 25*(2), 91–97. https://doi.org/10.1080/01449290500330331
**Method:** A position paper defining UX as beyond the instrumental: emotion, affect, aesthetics, the experiential.
**Key finding:** UX is the user's internal state × system characteristics × context.
**Design implication for prompts:** Always fill `{{PURPOSE}}` and `{{AUDIENCE}}`. The same style lands differently in a different context.

### Hassenzahl & Monk (2010) ✔ verified
**Citation:** Hassenzahl, M., & Monk, A. (2010). The inference of perceived usability from beauty. *Human-Computer Interaction, 25*(3), 235–260. https://doi.org/10.1080/07370024.2010.500139
**Method:** Analysis of several datasets with beauty, pragmatic quality and goodness ratings.
**Key finding:** The beauty→usability link is *indirect*: people infer usability from beauty mostly when they have little usability experience.
**Design implication for prompts:** On landing and marketing pages, beauty strongly shapes inferred usability. Inside an app, real usability takes over. Expressive treatment belongs on marketing surfaces, not in dense app UI.

### Moshagen, Musch & Göritz (2009) ✔ verified
**Citation:** Moshagen, M., Musch, J., & Göritz, A. S. (2009). A blessing, not a curse: Experimental evidence for beneficial effects of visual aesthetics on performance. *Ergonomics, 52*(10), 1311–1320. https://doi.org/10.1080/00140130903061717
**Method:** An online experiment crossing high and low aesthetics with good and poor usability on a website task.
**Key finding:** Under poor usability, the aesthetic version led to *better* task performance.
**Design implication for prompts:** Aesthetics is not decoration competing with function. It can improve performance, which is another reason to always ask for a high-polish visual layer.

### Sonderegger & Sauer (2010) ✔ verified
**Citation:** Sonderegger, A., & Sauer, J. (2010). The influence of design aesthetics in usability testing: Effects on user performance and perceived usability. *Applied Ergonomics, 41*(3), 403–410. https://doi.org/10.1016/j.apergo.2009.09.002
**Method:** Teenagers did tasks on an aesthetically appealing or unappealing mobile-phone prototype with identical function.
**Key finding:** The appealing version got higher perceived usability *and* better performance.
**Design implication for prompts:** As above. Prototypes and demos should be visually finished, because ugly demos underrate a product.

---

## 4. Complexity, prototypicality, novelty and fluency

### Berlyne (1970) ✔ verified; Berlyne (1971) ✔ verified (book)
**Citations:** Berlyne, D. E. (1970). Novelty, complexity, and hedonic value. *Perception & Psychophysics, 8*(5), 279–286. https://doi.org/10.3758/BF03212593. Berlyne, D. E. (1971). *Aesthetics and psychobiology*. Appleton-Century-Crofts (confirmed through library catalogues and reviews in *Leonardo*, https://doi.org/10.2307/1573258, and *JAAC*, https://doi.org/10.2307/429334).
**Method:** Experiments and theory on "collative variables" (novelty, complexity, uncertainty, conflict) and arousal.
**Key finding:** Collative variables raise arousal potential, and hedonic value follows an **inverted U** (Wundt curve). Moderate arousal is most pleasing. Repetition reduces novelty, so preference for complex stimuli can grow with exposure.
**Design implication for prompts:** Each style has its own point on the inverted U. Classical styles sit left of the peak and Expressive styles approach it, but *nothing should go past it*. Prompt rule: "One loud thing per screen." For audiences who return often (dev tools, magazines), you can afford more complexity.

### Tuch, Bargas-Avila, Opwis & Wilhelm (2009) ✔ verified
**Citation:** Tuch, A. N., Bargas-Avila, J. A., Opwis, K., & Wilhelm, F. H. (2009). Visual complexity of websites: Effects on users' experience, physiology, performance, and memory. *International Journal of Human-Computer Studies, 67*(9), 703–715. https://doi.org/10.1016/j.ijhcs.2009.04.002
**Method:** Participants viewed websites varying in complexity while subjective, physiological and memory measures were taken.
**Key finding:** Higher complexity was linked to lower pleasure and higher arousal, with physiological effects and slower task performance. The relationship was largely linear and negative for websites.
**Design implication for prompts:** For *websites*, more complex is usually worse. Expressive styles should get their expressiveness from *novelty and craft*, not from piling up elements.

### Tuch, Presslaber, Stöcklin, Opwis & Bargas-Avila (2012) ✔ verified
**Citation:** Tuch, A. N., Presslaber, E. E., Stöcklin, M., Opwis, K., & Bargas-Avila, J. A. (2012). The role of visual complexity and prototypicality regarding first impression of websites: Working towards understanding aesthetic judgments. *International Journal of Human-Computer Studies, 70*(11), 794–811. https://doi.org/10.1016/j.ijhcs.2012.06.003
**Method:** Study 1 used 119 website screenshots varying in visual complexity and prototypicality, at 50, 500 and 1000 ms. Study 2 used 17, 33 and 50 ms.
**Key finding:** **Low complexity + high prototypicality** gave the most appealing first impressions. Both effects appeared within **17 ms**. Complexity dominated at the briefest exposures, and prototypicality became as important at longer ones.
**Design implication for prompts:** Respect the **genre prototype** for the purpose: shops look like shops, SaaS looks like SaaS (logo left, nav right, hero with value proposition and CTA). Spend novelty on the art direction, not the information architecture. Prompt line: "Keep the page structure prototypical for a {{PURPOSE}} site. Put novelty into type, colour, imagery and motion."

### Michailidou, Harper & Bechhofer (2008) ✔ verified
**Citation:** Michailidou, E., Harper, S., & Bechhofer, S. (2008). Visual complexity and aesthetic perception of web pages. In *Proceedings of SIGDOC '08* (pp. 215–224). ACM. https://doi.org/10.1145/1456536.1456581
**Method:** Users ranked web pages on visual complexity and aesthetic attributes, and the rankings were related to page structure (the counts of images, links, words, sections).
**Key finding:** Perceived complexity tracked structural element counts and was negatively related to aesthetic judgments such as "clean" or "interesting".
**Design implication for prompts:** Control complexity through *counts*: "Hero: ≤ 12 words in the headline, ≤ 25 in the subline, ≤ 2 buttons, ≤ 6 nav links."

### Hekkert, Snelders & van Wieringen (2003): MAYA ✔ verified
**Citation:** Hekkert, P., Snelders, D., & van Wieringen, P. C. W. (2003). "Most advanced, yet acceptable": Typicality and novelty as joint predictors of aesthetic preference in industrial design. *British Journal of Psychology, 94*(1), 111–124. https://doi.org/10.1348/000712603762842147
**Method:** Participants rated product designs (e.g. telephones, teakettles, cars) for typicality, novelty and preference. Regression with suppression analysis.
**Key finding:** **Typicality and novelty both positively predict preference**, but they are negatively correlated with each other and suppress each other's effect. The optimum is the most novel design that stays typical: Raymond Loewy's **MAYA** principle.
**Design implication for prompts:** The central creative rule of this library: **"Prototypical structure + 1–3 committed novel moves."** Every PROMPT.md has a "pick 2–3 uniqueness levers" section for this reason. Too many levers make a design unacceptable, and none makes it a template.

### Reber, Schwarz & Winkielman (2004) ✔ verified
**Citation:** Reber, R., Schwarz, N., & Winkielman, P. (2004). Processing fluency and aesthetic pleasure: Is beauty in the perceiver's processing experience? *Personality and Social Psychology Review, 8*(4), 364–382. https://doi.org/10.1207/s15327957pspr0804_3
**Method:** A theoretical review integrating findings on symmetry, contrast, clarity, prototypicality and repetition.
**Key finding:** The more fluently a perceiver can process an object, the more positive the aesthetic response. Fluency is raised by figure-ground contrast, symmetry, clarity, prototypicality and prior exposure. Fluency that is unexpected or that the person cannot attribute feels especially pleasing.
**Design implication for prompts:** High contrast, clear figure-ground and consistent rhythm are not just accessibility rules. They *produce* beauty. Expressive styles add a moment of *disfluency* (a surprise), then resolve it quickly.

### Reber, Winkielman & Schwarz (1998) ✔ verified
**Citation:** Reber, R., Winkielman, P., & Schwarz, N. (1998). Effects of perceptual fluency on affective judgments. *Psychological Science, 9*(1), 45–48. https://doi.org/10.1111/1467-9280.00008
**Method:** Fluency was manipulated through priming, presentation duration and figure-ground contrast, and liking was measured.
**Key finding:** Higher perceptual fluency, including higher figure-ground contrast, raised liking.
**Design implication for prompts:** Experimental evidence for the cheatsheet rule "text contrast ≥ 4.5:1". Low-contrast grey-on-grey "minimalism" is less liked, not more elegant.

### Leder, Belke, Oeberst & Augustin (2004) ✔ verified
**Citation:** Leder, H., Belke, B., Oeberst, A., & Augustin, D. (2004). A model of aesthetic appreciation and aesthetic judgments. *British Journal of Psychology, 95*(4), 489–508. https://doi.org/10.1348/0007126042369811
**Method:** A theoretical stage model: perceptual analysis → implicit memory integration → explicit classification (style, content) → cognitive mastering → evaluation, producing aesthetic judgment and aesthetic emotion.
**Key finding:** Expert viewers rely more on *style classification*. Recognising the style ("this is Swiss", "this is Y2K") is itself rewarding.
**Design implication for prompts:** Award juries are experts, so a style that is *recognisable and mastered* scores well. Name the style and its lineage explicitly in prompts so the model applies it coherently rather than eclectically.

### Silvia (2005) ✔ verified
**Citation:** Silvia, P. J. (2005). Emotional responses to art: From collation and arousal to cognition and emotion. *Review of General Psychology, 9*(4), 342–357. https://doi.org/10.1037/1089-2680.9.4.342
**Method:** A review contrasting Berlyne's arousal model with appraisal theories of emotion.
**Key finding:** *Interest* arises when something is appraised as **novel-complex** *and* **comprehensible**. Coping potential matters: confusion kills interest.
**Design implication for prompts:** Experimental sites (EC-1, EC-2) must give the visitor a way to understand them quickly: a clear "scroll" cue, readable nav, an explicit way out of the WebGL scene.

### Bateman, Mandryk, Gutwin, Genest, McDine & Brooks (2010) ✔ verified
**Citation:** Bateman, S., Mandryk, R. L., Gutwin, C., Genest, A., McDine, D., & Brooks, C. (2010). Useful junk? The effects of visual embellishment on comprehension and memorability of charts. In *Proceedings of CHI '10* (pp. 2573–2582). ACM. https://doi.org/10.1145/1753326.1753716
**Method:** Embellished ("chart-junk") vs plain charts were compared for interpretation accuracy and recall, immediately and after 2–3 weeks.
**Key finding:** Accuracy did not differ, but embellished charts were remembered significantly better over the long term.
**Design implication for prompts:** **Ornament** (secondary axis) can buy memorability without costing comprehension if the data or content stays legible. Illustrative and retro styles can embellish key numbers and data.

---

## 5. Colour

### Valdez & Mehrabian (1994) ✔ verified
**Citation:** Valdez, P., & Mehrabian, A. (1994). Effects of color on emotions. *Journal of Experimental Psychology: General, 123*(4), 394–409. https://doi.org/10.1037/0096-3445.123.4.394
**Method:** Participants rated Munsell colour chips on Pleasure–Arousal–Dominance (PAD) scales. Regression on hue, saturation and brightness.
**Key finding:** **Brightness and saturation** predicted emotion more strongly than hue. Brighter colours were more pleasant and less dominant, and more saturated colours were more arousing. Among hues, blue, blue-green and green were among the most pleasant, and yellow and green-yellow were among the most arousing.
**Design implication for prompts:** Use saturation as the arousal dial: low-chroma palettes for calm (Classical, Luxury, Organic), high-chroma for energy (Playful, Retro, Brutalist accents). Specify colours in **OKLCH** and state chroma bands per style (e.g. "accent chroma ≤ 0.10" for Luxury and "≥ 0.20" for Playful).

### Gorn, Chattopadhyay, Yi & Dahl (1997) ✔ verified
**Citation:** Gorn, G. J., Chattopadhyay, A., Yi, T., & Dahl, D. W. (1997). Effects of color as an executional cue in advertising: They're in the shade. *Management Science, 43*(10), 1387–1400. https://doi.org/10.1287/mnsc.43.10.1387
**Method:** Ad experiments manipulating hue, chroma and value and measuring feelings and attitude toward the ad.
**Key finding:** Higher **value** (lightness) raised feelings of relaxation, and higher **chroma** raised excitement. Both influenced liking of the ad, with value and chroma mattering more than hue.
**Design implication for prompts:** Warm/inviting does not have to mean red or orange. Light, low-chroma warm neutrals (cream, sand) give *calm warmth*, and saturated warm hues give *excited warmth*. This is the difference between CW (Luxury, Organic) and EW (Playful, Retro).

### Labrecque & Milne (2012) ✔ verified
**Citation:** Labrecque, L. I., & Milne, G. R. (2012). Exciting red and competent blue: The importance of color in marketing. *Journal of the Academy of Marketing Science, 40*(5), 711–727. https://doi.org/10.1007/s11747-010-0245-y
**Method:** Four studies. Study 1 mapped hues onto Aaker's brand-personality dimensions. Studies 2–4 manipulated saturation and value and measured brand personality, purchase intent, likability and familiarity.
**Key finding:** Blue was linked to **competence**, trust, security and sincerity. Red was linked to **excitement**. Yellow was linked to sincerity and excitement. Saturation and value **amplify** personality traits (higher saturation means more excitement; lower value, i.e. darker, means more sophistication and ruggedness). Hue choice also shifted purchase intent.
**Design implication for prompts:** This links colour to Aaker and so to our styles: **Cool styles → blue/neutral (competence)**; **Warm-Expressive → red/orange/yellow (excitement)**; **Luxury → dark, desaturated, black/gold or deep jewel tones (sophistication)**; **Organic → greens and browns (sincerity, ruggedness)**. Write the target personality into the prompt and derive the palette from it.

### Elliot & Maier (2014) ✔ verified
**Citation:** Elliot, A. J., & Maier, M. A. (2014). Color psychology: Effects of perceiving color on psychological functioning in humans. *Annual Review of Psychology, 65*, 95–120. https://doi.org/10.1146/annurev-psych-010213-115035
**Method:** A narrative review of empirical colour-psychology research and the color-in-context theory.
**Key finding:** Colour meanings are **context-dependent** (red means danger in achievement contexts and attraction in romantic ones). Many popular colour claims are weakly supported, and methodological rigour (controlling lightness and chroma) is often missing.
**Design implication for prompts:** Do not write "use blue because blue means trust" as dogma. Write "colour meaning follows the context of {{PURPOSE}}", and test **lightness and chroma**, not hue alone. Avoid red for neutral UI states in high-stakes forms (it signals error and failure).

### Ou, Luo, Woodcock & Wright (2004) ✔ verified
**Citation:** Ou, L.-C., Luo, M. R., Woodcock, A., & Wright, A. (2004). A study of colour emotion and colour preference. Part I: Colour emotions for single colours. *Color Research & Application, 29*(3), 232–240. https://doi.org/10.1002/col.20010 (Part III, preference modelling: https://doi.org/10.1002/col.20047)
**Method:** Observers rated single colour patches on colour-emotion scales. Factor analysis was used, along with colorimetric models.
**Key finding:** Colour emotions collapse into three factors: **colour activity** (active–passive), **colour weight** (heavy–light) and **colour heat** (**warm–cool**). Each is predictable from CIELAB hue angle, lightness and chroma.
**Design implication for prompts:** **This is the colorimetric basis for the Cool↔Warm axis.** Warmth rises with hue angles near red/orange/yellow and with chroma. Coolness rises with blue/cyan hues and low chroma. For prompts: "Cool styles: neutrals tinted toward blue (OKLCH hue ~230–260). Warm styles: neutrals tinted toward yellow-orange (hue ~60–90)." A temperature shift often only needs a *tint of the neutrals*.

### Palmer & Schloss (2010) ✔ verified
**Citation:** Palmer, S. E., & Schloss, K. B. (2010). An ecological valence theory of human color preference. *Proceedings of the National Academy of Sciences, 107*(19), 8877–8882. https://doi.org/10.1073/pnas.0906172107
**Method:** 32 chromatic colours were rated for preference, and separately, objects associated with each colour were rated for valence.
**Key finding:** Colour preference is well explained by how people feel about the *objects* associated with the colour (sky and water blues are liked, while biological-waste browns and olives are disliked).
**Design implication for prompts:** Organic and earthy styles must anchor browns and olives to *appealing referents* (wood, bread, soil in a garden, clay) through imagery and texture. Otherwise these colours read as "mud".

### Cyr, Head & Larios (2010) ✔ verified
**Citation:** Cyr, D., Head, M., & Larios, H. (2010). Colour appeal in website design within and across cultures: A multi-method evaluation. *International Journal of Human-Computer Studies, 68*(1–2), 1–21. https://doi.org/10.1016/j.ijhcs.2009.08.005
**Method:** Websites in different colour schemes were tested with users in Canada, Germany and Japan using questionnaires, interviews and eye-tracking.
**Key finding:** Colour appeal predicted **trust and satisfaction**, which in turn predicted e-loyalty. Preferred colour schemes differed by culture.
**Design implication for prompts:** For international audiences, test the palette against the target culture. Colour is a trust lever in e-commerce, not just decoration.

### Hall & Hanna (2004) ✔ verified
**Citation:** Hall, R. H., & Hanna, P. (2004). The impact of web page text-background colour combinations on readability, retention, aesthetics and behavioural intention. *Behaviour & Information Technology, 23*(3), 183–195. https://doi.org/10.1080/01449290410001669932
**Method:** Participants read pages with different text and background colour combinations and rated readability, aesthetics and intentions. Retention was tested.
**Key finding:** Higher-contrast combinations (black on white, white on black) were more readable. Preferred colours were rated more aesthetically pleasing and correlated with intention to purchase.
**Design implication for prompts:** Body text stays high-contrast in every style. Colour personality lives in backgrounds, accents, display type and imagery, not in low-contrast body copy.

---

## 6. Warmth, competence and brand personality

### Aaker (1997) ✔ verified
**Citation:** Aaker, J. L. (1997). Dimensions of brand personality. *Journal of Marketing Research, 34*(3), 347–356. https://doi.org/10.1177/002224379703400304
**Method:** US respondents rated 37 brands on 114 personality traits. Factor analysis produced a 42-item scale, validated on a separate sample.
**Key finding:** Five dimensions: **Sincerity** (down-to-earth, honest, wholesome, cheerful), **Excitement** (daring, spirited, imaginative, up-to-date), **Competence** (reliable, intelligent, successful), **Sophistication** (upper-class, charming) and **Ruggedness** (outdoorsy, tough).
**Design implication for prompts:** This gives the brand-personality → style mapping in `taxonomy.md`. Prompts should name the *primary and secondary Aaker dimension* of the brand.

### Fiske, Cuddy & Glick (2007) ✔ verified
**Citation:** Fiske, S. T., Cuddy, A. J. C., & Glick, P. (2007). Universal dimensions of social cognition: Warmth and competence. *Trends in Cognitive Sciences, 11*(2), 77–83. https://doi.org/10.1016/j.tics.2006.11.005
**Method:** A review of the stereotype content model and related findings.
**Key finding:** People judge others on two universal dimensions: **warmth** (intent: friendly, sincere) and **competence** (ability: capable, skilled). Warmth is judged first.
**Design implication for prompts:** The psychological basis of our Cool↔Warm axis. **Warm** = signalling good intent (human, friendly, approachable). **Cool** = signalling ability (precise, technical, capable). The best brands show both, so a Cool style still needs one warmth cue (a human photo, a friendly microcopy line), and a Warm style needs one competence cue (precise data, credentials).

### Aaker, Vohs & Mogilner (2010) ✔ verified
**Citation:** Aaker, J., Vohs, K. D., & Mogilner, C. (2010). Nonprofits are seen as warm and for-profits as competent: Firm stereotypes matter. *Journal of Consumer Research, 37*(2), 224–237. https://doi.org/10.1086/651566
**Method:** Experiments manipulating whether an organisation was framed as nonprofit (.org) or for-profit (.com), measuring warmth, competence and willingness to buy.
**Key finding:** Nonprofits were seen as warmer but less competent, and this competence gap reduced willingness to buy. Credible competence signals closed the gap.
**Design implication for prompts:** NGO and nonprofit sites (CW-2 Warm-Organic) must add **competence cues**: hard impact numbers, audited reports, crisp data visualisation. Corporate and finance sites (CC-2) must add **warmth cues**: real people, plain-language copy.

### Kervyn, Fiske & Malone (2012) ✔ verified
**Citation:** Kervyn, N., Fiske, S. T., & Malone, C. (2012). Brands as intentional agents framework: How perceived intentions and ability can map brand perception. *Journal of Consumer Psychology, 22*(2), 166–176. https://doi.org/10.1016/j.jcps.2011.09.006
**Method:** Applied the warmth × competence model to brands, with consumer ratings of many brands.
**Key finding:** Brands sort into warmth × competence quadrants that predict distinct emotions (admiration, contempt, envy, pity) and purchase intent. High-high brands are admired.
**Design implication for prompts:** Our Cool↔Warm axis and an implicit competence floor map onto this space. Award-level sites aim for the **admired quadrant**: warm style + visible competence, or cool style + visible warmth.

### Williams & Bargh (2008) ✔ verified; failed replication: Chabris et al. (2019) ✔ verified
**Citations:** Williams, L. E., & Bargh, J. A. (2008). Experiencing physical warmth promotes interpersonal warmth. *Science, 322*(5901), 606–607. https://doi.org/10.1126/science.1162548. Chabris, C. F., Heck, P. R., Mandart, J., Benjamin, D. J., & Simons, D. J. (2019). No evidence that experiencing physical warmth promotes interpersonal warmth: Two failures to replicate Williams and Bargh (2008). *Social Psychology, 50*(2), 127–132. https://doi.org/10.1027/1864-9335/a000361
**Key finding:** The famous "warm cup makes people seem warmer" effect **did not replicate**.
**Design implication for prompts:** *Caution.* Do not justify warm palettes with embodied-warmth priming. Justify the Cool↔Warm axis with colour-emotion research (Ou et al., 2004) and social-perception warmth (Fiske et al., 2007), as this library does.

---

## 7. Typography

### Brumberger (2003a, 2003b) ✔ verified
**Citations:** Brumberger, E. R. (2003a). The rhetoric of typography: The persona of typeface and text. *Technical Communication, 50*(2), 206–223. Brumberger, E. R. (2003b). The rhetoric of typography: The awareness and impact of typeface appropriateness. *Technical Communication, 50*(2), 224–231. (Society for Technical Communication; no DOI. Indexed by IngentaConnect: https://www.ingentaconnect.com/contentone/stc/tc/2003/00000050/00000002/art00008)
**Method:** (a) Participants rated typefaces and text passages on persona attributes, and factor analysis gave three dimensions: *elegance*, *friendliness* and *directness*. (b) Participants read passages set in congruent or incongruent typefaces.
**Key finding:** Typefaces have consistent, recognisable **personas**. Readers notice typeface–text *appropriateness*, and it affects how the text is perceived (p < .01 in the published abstract).
**Design implication for prompts:** The three persona dimensions map onto the styles: **elegance** → Luxury/Swiss (high-contrast serifs, refined grotesks); **friendliness** → Playful/Organic (rounded sans, soft serifs); **directness** → Corporate/Tech/Brutalist (neutral grotesks, monospace). The prompt must state the *typeface persona* along with the family name.

### Brumberger (2004) ✔ verified
**Citation:** Brumberger, E. R. (2004). The rhetoric of typography: Effects on reading time, reading comprehension, and perceptions of ethos. *Technical Communication, 51*(1), 13–24.
**Method:** A follow-up experiment manipulating typeface appropriateness and measuring reading time, comprehension and perceived ethos.
**Key finding:** Appropriateness had little effect on reading time or comprehension but did influence perceptions of the document's ethos.
**Design implication for prompts:** Typeface choice is mainly a *credibility and persona* decision. Body text should stay a highly legible face; spend persona on display type.

### Henderson, Giese & Cote (2004) ✔ verified
**Citation:** Henderson, P. W., Giese, J. L., & Cote, J. A. (2004). Impression management using typeface design. *Journal of Marketing, 68*(4), 60–72. https://doi.org/10.1509/jmkg.68.4.60.42736
**Method:** Rated a large set of typefaces (≈ 200) on design characteristics and on impressions. Factor analysis and regression.
**Key finding:** Six design dimensions: **elaborate, harmony, natural, flourish, weight, compressed**. These predicted the impressions *pleasing, engaging, reassuring* and *prominent*. For example, natural and harmonious designs were more pleasing and reassuring, and heavier weights read as more prominent.
**Design implication for prompts:** Use these as typeface-selection knobs:
- **Reassuring** (Corporate, Finance, Health) → harmonious, natural, moderate weight, not compressed.
- **Engaging** (Playful, Retro, Agency) → elaborate, some flourish.
- **Prominent** (Brutalist, Event) → heavy weight, compressed display faces.

### Childers & Jass (2002) ✔ verified
**Citation:** Childers, T. L., & Jass, J. (2002). All dressed up with something to say: Effects of typeface semantic associations on brand perceptions and consumer memory. *Journal of Consumer Psychology, 12*(2), 93–106. https://doi.org/10.1207/S15327663JCP1202_03
**Method:** Experiments pairing ads with typefaces whose semantic associations were congruent or incongruent with the brand positioning.
**Key finding:** Typeface semantics shaped brand perceptions, and congruent typefaces improved memory for the brand claims.
**Design implication for prompts:** "Congruence beats novelty." An unexpected typeface is a valid uniqueness lever only if its connotation still fits the brand.

### Doyle & Bottomley (2004) ✔ verified
**Citation:** Doyle, J. R., & Bottomley, P. A. (2004). Font appropriateness and brand choice. *Journal of Business Research, 57*(8), 873–880. https://doi.org/10.1016/S0148-2963(02)00487-3
**Method:** Choice experiments with fictitious brand names set in fonts that were appropriate or inappropriate to the product.
**Key finding:** Brands in appropriate fonts were chosen more often.
**Design implication for prompts:** Font fit has measurable commercial effects. Every PROMPT.md should justify its font pairing against the product category.

### Bernard, Liao & Mills (2001) ✔ verified
**Citation:** Bernard, M., Liao, C. H., & Mills, M. (2001). The effects of font type and size on the legibility and reading time of online text by older adults. In *CHI '01 Extended Abstracts* (pp. 175–176). ACM. https://doi.org/10.1145/634067.634173
**Method:** Older adults read on-screen passages in serif and sans-serif fonts at 12 and 14 pt.
**Key finding:** 14-pt text was more legible and preferred. Font type mattered less than size.
**Design implication for prompts:** Body text at **≥ 16 px** (≈ 12 pt) and **18–20 px** for older audiences or long-form editorial. Serif vs sans for body is a persona decision, not a legibility one, at modern screen resolutions.

### Dyson & Haselgrove (2001) ✔ verified
**Citation:** Dyson, M. C., & Haselgrove, M. (2001). The influence of reading speed and line length on the effectiveness of reading from screen. *International Journal of Human-Computer Studies, 54*(4), 585–612. https://doi.org/10.1006/ijhc.2001.0458
**Method:** Participants read on-screen text at different line lengths (25, 55, 100 characters per line) and reading speeds, then answered comprehension questions.
**Key finding:** A **medium line length (~55 cpl)** supported comprehension well across normal and fast reading. Very long lines can be read faster but at a cost to comprehension.
**Design implication for prompts:** Set `max-width: 60–75ch` for body text (aligned with Bringhurst's 45–75 character guidance). Expressive styles may break this for *display* text but never for paragraphs.

### Bringhurst (2004) ✔ verified (book)
**Citation:** Bringhurst, R. (2004). *The elements of typographic style* (3rd ed.). Hartley & Marks. (Verified via Open Library; first edition 1992.)
**Key guidance:** A comfortable measure is roughly **45–75 characters** (66 is often cited as ideal). Type sizes should come from a coherent **scale** (the classic typographic scale or musical ratios). Leading should suit the measure.
**Design implication for prompts:** "Use a modular type scale (ratio 1.2–1.25 for Classical and app UIs, 1.333–1.618 for Expressive and editorial display). Body line-height 1.4–1.6; display line-height 0.9–1.1."

---

## 8. Layout, attention and reading

### Pan, Hembrooke, Gay, Granka, Feusner & Newman (2004) ✔ verified
**Citation:** Pan, B., Hembrooke, H. A., Gay, G. K., Granka, L. A., Feusner, M. K., & Newman, J. K. (2004). The determinants of web page viewing behavior: An eye-tracking study. In *Proceedings of ETRA 2004* (pp. 147–154). ACM. https://doi.org/10.1145/968363.968391
**Method:** Eye-tracking of participants viewing web pages of different genres and tasks.
**Key finding:** Viewing patterns depended on individual differences (e.g. gender), page type and the order of viewing. Scanpaths were not universal.
**Design implication for prompts:** Do not assume one reading pattern. Use **visual hierarchy** (size, contrast, position) to force the intended order: headline → proof → CTA.

### Djamasbi, Siegel & Tullis (2010) ✔ verified
**Citation:** Djamasbi, S., Siegel, M., & Tullis, T. (2010). Generation Y, web design, and eye tracking. *International Journal of Human-Computer Studies, 68*(5), 307–323. https://doi.org/10.1016/j.ijhcs.2009.12.006
**Method:** Eye-tracking and surveys of Gen Y users on web pages with different design features.
**Key finding:** Gen Y users preferred pages with a large main image, images of celebrities or people, little text and a search feature. They tended to skip dense text.
**Design implication for prompts:** For younger consumer audiences: a large hero image, short text and people in imagery. For expert B2B audiences, denser information is acceptable.

### Nielsen (2006) and Pernice (2017), NN/g: the F-pattern ✔ verified (industry research)
**Citations:** Nielsen, J. (2006, April 16). *F-shaped pattern for reading web content*. Nielsen Norman Group. Pernice, K. (2017, November 12). *F-shaped pattern of reading on the web: Misunderstood, but still relevant (even on mobile)*. Nielsen Norman Group. https://www.nngroup.com/articles/f-shaped-pattern-reading-web-content/
**Method:** Eye-tracking of 232 users on thousands of pages (2006), and a later replication (2017).
**Key finding:** When text is poorly formatted, users scan in an **F** (two horizontal sweeps, then a vertical one down the left). Other patterns: **layer-cake** (headings only), **spotted**, **marking**, **bypassing**, **commitment**. The F-pattern is a symptom of poor formatting.
**Design implication for prompts:** Design for the *layer-cake* pattern instead: information-rich headings and subheads, key words at the start of headings, bullets, bolded key terms, and the most important content in the first two paragraphs.

### Fessenden (2018), NN/g: scrolling and attention ✔ verified (industry research)
**Citation:** Fessenden, T. (2018). *Scrolling and attention*. Nielsen Norman Group. https://www.nngroup.com/articles/scrolling-and-attention/
**Method:** Eye-tracking analysis of where viewing time falls on long pages.
**Key finding:** About **57%** of viewing time was above the fold and **74%** within the first two screenfuls (up to 2160 px). Attention drops sharply after the fold.
**Design implication for prompts:** The value proposition, the style's signature and one proof point must sit in the first ~2 viewports. Long scroll-told stories (EC-1) need a strong hook in the first screen and visible progress cues.

---

## 9. Kansei engineering

### Nagamachi (1995) ✔ verified
**Citation:** Nagamachi, M. (1995). Kansei engineering: A new ergonomic consumer-oriented technology for product development. *International Journal of Industrial Ergonomics, 15*(1), 3–11. https://doi.org/10.1016/0169-8141(94)00052-5
**Method:** Introduced Kansei Engineering (KE). Collect the "Kansei words" consumers use for a product domain → rate product samples on semantic differentials of those words → statistically relate (e.g. regression, quantification theory) the ratings to concrete *design elements* → derive design rules.
**Key finding:** Emotional responses can be translated systematically into design parameters.
**Design implication for prompts:** This is the method behind the library. A style is a set of **Kansei words** (e.g. "calm, precise, premium") linked to **design parameters** (font class, chroma band, grid, motion curve). Each PROMPT.md should list both, so the LLM knows *why* each parameter is there.

### Nagamachi (2002) ✔ verified
**Citation:** Nagamachi, M. (2002). Kansei engineering as a powerful consumer-oriented technology for product development. *Applied Ergonomics, 33*(3), 289–294. https://doi.org/10.1016/S0003-6870(02)00019-4
**Method:** An overview of KE types (category classification, computer-assisted KE, hybrid KE) with industrial cases.
**Key finding:** *Category classification*, breaking a top-level concept into sub-concepts and then design specifications, is practical and effective.
**Design implication for prompts:** Our taxonomy is category classification: quadrant → style → Kansei words → tokens. Prompts should go top-down in the same order.

### Schütte, Eklund, Axelsson & Nagamachi (2004) ✔ verified
**Citation:** Schütte, S. T. W., Eklund, J., Axelsson, J. R. C., & Nagamachi, M. (2004). Concepts, methods and tools in Kansei engineering. *Theoretical Issues in Ergonomics Science, 5*(3), 214–231. https://doi.org/10.1080/1463922021000049980
**Method:** A conceptual model of KE: choose the domain → span the semantic space (Kansei words) → span the space of properties (design elements) → synthesise → validate.
**Key finding:** The two "spaces" (semantic and properties) and their mapping are the core of KE.
**Design implication for prompts:** In our library the **semantic space** is Classical↔Expressive × Cool↔Warm plus the Aaker traits, and the **property space** is the secondary axes (Density, Motion, Ornament, Contrast) plus `tokens.css`. A prompt states both and how they map.

### Hussin & Lokman (2011) ✔ verified
**Citation:** Hussin, S. R., & Lokman, A. M. (2011). Kansei website interface design: Practicality and accuracy of Kansei Web Design Guideline. In *2011 International Conference on User Science and Engineering (i-USEr)* (pp. 30–35). IEEE. https://doi.org/10.1109/iUSEr.2011.6150531
**Method:** Websites were built from a KE-derived web design guideline and evaluated on whether they evoked the intended Kansei.
**Key finding:** Guideline-based designs largely evoked the targeted emotions, which supports KE for web design.
**Design implication for prompts:** Evidence that "emotion word → design rule" guidelines (which is what each PROMPT.md is) can reproduce intended feelings on websites.

---

## 10. Standards used as hard constraints

These are not papers, but they are authoritative and verified. Juries (Awwwards Developer Award, Webby) explicitly score accessibility and performance.

| Standard | Requirement | Source ✔ |
|---|---|---|
| WCAG 2.2 SC 1.4.3 Contrast (Minimum), AA | Text ≥ **4.5:1**; large text (≥ 24 px, or ≥ 18.66 px bold) ≥ **3:1** | W3C (2023). *Web Content Accessibility Guidelines 2.2*. https://www.w3.org/TR/WCAG22/ |
| WCAG 2.2 SC 1.4.11 Non-text Contrast, AA | UI components and meaningful graphics ≥ **3:1** | same |
| WCAG 2.2 SC 2.3.3 Animation from Interactions, AAA | Motion triggered by interaction can be disabled. In practice, honour `prefers-reduced-motion` | same |
| WCAG 2.2 SC 2.4.11 Focus Not Obscured (Minimum), AA, and 2.5.8 Target Size (Minimum), AA | Focus must not be hidden by sticky UI; targets ≥ **24×24 CSS px** | same |
| Core Web Vitals | LCP ≤ **2.5 s**, INP ≤ **200 ms**, CLS ≤ **0.1** ("good" thresholds, 75th percentile) | Google web.dev, https://web.dev/articles/vitals |

**Design implication for prompts:** Put these in every PROMPT.md as non-negotiable constraints. Expressive styles (WebGL, heavy motion) need a stated fallback: a static poster frame, `prefers-reduced-motion` handling and lazy-loaded 3D.

---

## 11. Unverified or dropped leads

| Lead | Status |
|---|---|
| "Users form an opinion in 0.05 s, so 94% of first impressions are design-related" (a statistic often attributed to Sillence et al.) | **Dropped as stated.** The underlying paper exists and is verified (Sillence, E., Briggs, P., Harris, P., & Fishwick, L. (2007). Health websites that people can trust: The case of hypertension. *Interacting with Computers, 19*(1), 32–42. https://doi.org/10.1016/j.intcom.2006.07.009), but I could not confirm the "94%" figure from the source. Do not quote the statistic. |
| Bernard, Lida, Riley, Hackler & Janzen (2002), "A comparison of popular online fonts" (*Usability News*) | Not found in Crossref (an SURL newsletter, not peer-reviewed). Not used. |
| Pengnate & Sarathy (2013), durability of initial impressions (HICSS) | The record exists in Crossref (https://doi.org/10.1109/HICSS.2013.600), but I did not read the findings. Left out of the analysis. |
| Awwwards Developer Award sub-criteria (Semantics/SEO, Animations/Transitions, Accessibility, WPO, Responsive design, Markup/Meta-data) | The official page links a Google Doc that I could not read. The categories are confirmed only by secondary sources. See `award-criteria.md`. |
| Colour-temperature claims such as "warm colours increase conversion by X%" | No peer-reviewed source found. Not used. |
