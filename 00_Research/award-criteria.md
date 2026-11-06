# Award criteria: what juries actually score

Checked against the official sites in November 2026. **✔ official** = read on the award's own site. **◐ secondary** = only confirmed through third-party write-ups.

---

## 1. Awwwards

**Source:** https://www.awwwards.com/about-evaluation/ ✔ official; https://www.awwwards.com/developer-award ✔ official

| Criterion | Weight | What it means in practice |
|---|---|---|
| **Design** | **40%** ✔ | Visual quality: typography, colour, layout, imagery, consistency, craft |
| **Usability** | **30%** ✔ | Navigation, clarity, responsiveness, speed, accessibility |
| **Creativity** | **20%** ✔ | Originality of concept and execution, surprise, memorable interaction |
| **Content** | **10%** ✔ | Quality and relevance of copy, imagery and story |

Mechanics (✔ official):
- At least **18 jury members** score each submission. The **3 scores furthest from the average are discarded** automatically. Voting runs **5 days**.
- **Honorable Mention**: jury score **≥ 6.5**.
- **Site of the Day (SOTD)**: the highest jury scores of the day (a site can win early with high jury scores plus at least 10 PRO-user votes).
- **Developer Award**: every SOTD goes to a developer jury and is evaluated against the Developer Guidelines. A score **> 7** earns the award.
- **Site of the Month**: the 8 highest-scoring sites of the month are nominated for a second jury round. **Site of the Year**: all SOTM winners are nominated, plus curator picks.

Developer Award sub-criteria ◐ secondary (the official guideline is a linked Google Doc I could not read): **Semantics/SEO, Animations/Transitions, Accessibility, WPO (web performance optimisation), Responsive design, Markup/Meta-data**.

**Implication:** Design + Usability = **70%**. A spectacular site that is slow, unclear or broken on mobile cannot win. Creativity is only 20%, so novelty must sit *on top of* craft, not replace it. This matches Lavie & Tractinsky (2004): usability tracks *classical* aesthetics, and creativity is the *expressive* bonus.

---

## 2. CSS Design Awards (CSSDA)

**Source:** CSSDA site pages and FAQ text shown on submission pages, e.g. https://www.cssdesignawards.com/sites/glassland/38756/ ✔ official (FAQ text quoted on the site)

| Criterion | Weight | Definition (CSSDA's own words) |
|---|---|---|
| **UI Design** | equal, averaged | "User Interface design such as aesthetics and effects" |
| **UX Design** | equal, averaged | "User Experience and functionality" |
| **Innovation** | equal, averaged | "the use of new development and design ideas" |

Mechanics:
- Judges score UI, UX and Innovation, and the average is the **Final Judge's Score**.
- **Website of the Day (WOTD)**: average judge score **above 8.0** (the FAQ notes that this varies with the quality of submissions).
- **Special Kudos**: average **above 6.0** but below the WOTD bar.
- Separate **public awards** (UI, UX, Innovation) need ~20 votes in a category. WOTD is decided within **96 hours**.
- Higher tiers: Website of the Month, Website of the Year.

**Implication:** Innovation is **one third** of the score, a larger share than at Awwwards. A technically fresh idea (a new CSS feature, a shader, an original interaction model) is worth relatively more at CSSDA.

---

## 3. FWA (Favourite Website Awards)

**Source:** https://thefwa.com/about ✔ official

- FWA describes itself as "where you go to experience cutting-edge innovation in digital design and development. It's a space that encourages the digital industry to push the boundaries of technology, to show people what is possible."
- **Judging**: the FWA jury scores live. Each judge has **up to 100 points** per submission. A submission enters the Live Judging page with a **base score of 50** and has **14 days** to reach the top score of the day. The public page shows the average score out of 100 (from at least 20 judges).
- Tiers: **FWA of the Day (FOTD) → FWA of the Month → FWA of the Year**.
- Historical: the **Adobe Cutting Edge Award** (2013–2016, now retired) went to "the project that best highlights the newest capabilities of the modern web".
- **There are no published weightings.** Third-party summaries ◐ list innovation, design, creativity, content and user experience.

**Implication:** FWA leans most heavily toward the **Expressive** pole: innovation, technology and "pushing boundaries". EC-1 Immersive and EC-2 Brutalist are the natural FWA styles. A pure Classical-Cool site rarely gets a FOTD unless its execution is outstanding.

---

## 4. Webby Awards

**Source:** https://www.webbyawards.com/judging-criteria/ ✔ official

The Webbys judge websites on **seven criteria**, with **no public weighting**:

| Criterion | Summary of the official definition |
|---|---|
| **Content** | Engaging, relevant, clear, concise information with a distinctive perspective |
| **Structure & Navigation** | Organisation, prioritisation and movement through the site: consistent, intuitive, transparent |
| **Visual Design** | High quality, appropriate and relevant to audience and message, *while improving inclusion for people with disabilities*. It does not have to be trendy. |
| **Functionality** | Works well, loads quickly, live links, cross-platform, supports accessibility needs |
| **Interactivity** | Lets users act (search, commerce, real-time feedback, AI/ML), so they participate rather than consume passively |
| **Innovation** | Pushes beyond what has been done before. Is the idea fundamentally new or iterative? |
| **Overall Experience** | The intangible sum: repeat visits, bookmarking, sharing, time spent |

Judged by the International Academy of Digital Arts and Sciences, with a parallel **People's Voice** public vote.

**Implication:** The Webbys weight **content, structure and accessibility** much more than design-only awards do. Visual design is explicitly judged on *appropriateness to the audience*, not trendiness. This is a strong argument for the purpose → style matrix in `taxonomy.md`.

---

## 5. Side-by-side

| | Awwwards | CSSDA | FWA | Webby |
|---|---|---|---|---|
| Visual design | 40% | ⅓ (UI) | high (unweighted) | 1 of 7 |
| Usability / UX | 30% | ⅓ (UX) | considered | Structure + Functionality (2 of 7) |
| Creativity / innovation | 20% | ⅓ (Innovation) | **dominant ethos** | 1 of 7 |
| Content | 10% | – | considered | 1 of 7 (listed first) |
| Code / performance / a11y | Developer Award (> 7) | – | – | inside Functionality and Visual Design |
| Bias on our map | Classical skeleton + Expressive skin | Expressive-technical | **Expressive** | Classical, content-first |

---

## 6. What this means for prompt-writing

1. **Craft first, then surprise.** At Awwwards, 70% is design + usability. Prompt order should be: (1) grid, type scale, spacing, colour tokens, (2) responsive behaviour and accessibility, (3) *then* 2–3 creative levers. Never the other way round.
2. **Name the "one idea".** Creativity and Innovation are judged on a *concept*, not an effects count. `{{UNIQUE_HOOK}}` must be one sentence a juror could repeat ("the cursor is a magnifying loupe over a jeweller's workbench").
3. **Ship the Developer Award checklist** into every prompt: semantic HTML landmarks, a meaningful `<title>`/meta/OG tags, `prefers-reduced-motion`, keyboard focus styles, responsive at 375 px, lazy-loaded media, LCP ≤ 2.5 s, CLS ≤ 0.1, no layout jank from animations (animate `transform`/`opacity` only).
4. **Accessibility is now a design criterion** (Webby Visual Design explicitly, Awwwards Developer Award). WCAG AA contrast is the floor in every style.
5. **Content is scored.** Ban lorem ipsum. Ask for specific, brand-voiced microcopy and real-feeling case-study data (fictional but plausible).
6. **Choose the award for the style.** EC-1 and EC-2 → FWA and CSSDA Innovation. CC and CW styles → Awwwards Design/Usability and Webby. Playful or retro consumer brands → Awwwards and Webby People's Voice.
7. **Mobile is not an afterthought.** Usability (30%) and Responsive design (Developer Award) are judged on phones. Prompts must describe the 375 px layout explicitly, not just say "make it responsive".
8. **Juror self-critique.** End every generation prompt with: "Score this as an Awwwards juror: Design /10, Usability /10, Creativity /10, Content /10, weighted 40/30/20/10. If the weighted score is < 7.5, list the 3 biggest fixes and apply them."
