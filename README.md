# Battle Pass ROI Calculator

**Is this season's battle pass worth it for you?** An interactive, unofficial *season value guide*. Pick your game, say how much you actually play, and it tells you whether you'll finish the pass before the season ends, what the cosmetics are really worth to you, what each hour of play costs, and which behavioral traps are working on you.

It's a portfolio piece built from an economics thesis on the move from loot boxes to battle passes, and it's designed as a working tool rather than a slide.

> Open `index.html` in any modern browser. No build, no server, no account.

## What it does

- **A verdict in one sentence.** *Worth it*, *Close call*, *Probably not*, or *No spend* for the free track, with the reason written out in plain language.
- **Sentence-style inputs.** "I play **[game]** about **[10]** hours a week. I'd **[buy the premium pass]** and actually use **[25%]** of its cosmetics." Drag the highlighted numbers sideways, use the arrow keys, or tap − / + on touch screens.
- **Walkthrough.** The whole pass laid out as a route map, one node per tier. Scroll (or press *Play the season*) to watch your playhead move week by week. The season-end wall shows exactly which tiers expire unclaimed.
- **Shop math.** A line-by-line ledger that turns *sticker value* (every item at store price) into *real value* (only what you unlock this season and would actually use), next to the "ROI on the box" the pass is marketed on.
- **Cost per hour of play** on a log-scale ruler, compared with a movie ticket.
- **Bestiary.** The four behavioral traps (sunk cost, FOMO, endowment effect, loss aversion), each with a threat level calculated from your numbers. The list re-ranks live as your inputs change.
- **Clear conditions.** A four-point checklist for "good value": three are calculated, and the fourth is your call.
- **Appendix.** All five games run at your pace side by side, every preset editable (your edits are highlighted as *yours*), plus the method and sources.
- **Shareable links.** Your game, hours, want-rate and edits live in the URL, so *Copy a link to your numbers* reproduces your exact verdict.

## Design

The visual world is a **printed strategy guide**, the glossy official-guide tradition gamers grew up with, not another dark neon dashboard:

- Coated-paper ground printed in process ink. **Cyan**, **magenta** and **rich black** each own a chapter as full-bleed plates and as thumb-index tabs on the page edge.
- **Highlighter yellow belongs only to your own numbers.** Anything you typed or edited is marked, and nothing else is.
- Every figure carries a provenance ticket: `yours`, `est.` (a preset estimate) or `calc` (derived), so an estimate never passes as fact.
- Heavy extended display type ([Anybody](https://fonts.google.com/specimen/Anybody)) on a variable width axis, set against dense ruled tables in [Archivo](https://fonts.google.com/specimen/Archivo) with tabular figures.

### Motion

The motion comes from print itself, choreographed with GSAP:

- **Press check opening.** Cyan, magenta and yellow plates drift in out of register, snap together into black while the title widens, then the sheet trims away. It plays once per session, and any key or click skips it.
- **Reprints.** When your verdict changes, the color plates slip and snap back into register and the new word rises from below. Changed numbers roll and flash out of register.
- **Scroll-driven chapters.** Plates wipe in like an ink pass, titles stretch along the variable width axis, and halftone ramps dissolve each plate into the paper.
- **Pinned walkthrough** (desktop). Scrolling plays the season: tiers light up and the season-end wall slams down.
- **Live re-ranking.** Bestiary entries reorder with FLIP animation, and item tiles flip when your want-rate changes.
- **Reduced motion is designed in, not bolted on.** With `prefers-reduced-motion`, the opening, pinning and smooth scrolling are skipped and values update instantly, while color and state changes are kept.

## Economic methodology

| Quantity | Formula |
| --- | --- |
| Hours per tier | hours to finish ÷ tiers |
| Tier at season end | min(tiers, ⌊hours a week × season weeks ÷ hours per tier⌋) |
| Sticker value | cosmetics × average item price |
| Real value | cosmetics unlocked by season end × average item price × share you'd use |
| Your ROI | (real value − pass price) ÷ pass price |
| ROI on the box | (sticker value − pass price) ÷ pass price |
| Cost per hour | pass price ÷ hours played while the pass still pays out |

**Verdict:** *Worth it* when you finish the pass and the real value covers the price, *Probably not* when neither holds, and *Close call* otherwise.

**Example.** Fortnite's 100-item pass at $9.99 with items averaging $1.50 has a sticker value of $150 and an "ROI on the box" of **+1,402%**. Playing 10 hours a week and using a quarter of the cosmetics, you finish in week 8 of a 12-week season and the real value is $37.50: **+275%**. At 4 hours a week you only reach tier 64, the real value drops to $24.00, and the ROI falls to **+140%**.

Progress is modeled as steady per hour of play. XP events and weekly challenges usually speed it up, so treat the forecast as a floor.

## Behavioral economics framework

1. **Sunk cost fallacy.** Players keep playing "to get their money's worth" after the money is already spent. The calculator shows how many hours short you'd finish the season, which is exactly the gap sunk cost asks you to fill.
2. **FOMO.** Battle passes lean on time scarcity (seasonal resets) and perceived item scarcity, though similar items come back. The calculator counts the tiers that expire at season end, the moment tier-skip offers are aimed at.
3. **Endowment effect.** Unlocked items feel worth more than the same items in a store. Separating *sticker* value from *real* value is the counterweight.
4. **Loss aversion.** Missing a tier you could have had stings more than keeping the money feels good. The prompt: *do I want this item, or do I just want to avoid the regret?*

## Portfolio context

This project grows out of an economics thesis:

> **The Transition from Loot Boxes to Battle Passes in Video Games: Economic Models, Player Behavior, and Long-Term Monetization Sustainability**
> *Matthew Cromaz, Reed College, 2023*

### Research questions

- How do battle passes use behavioral economics compared with loot boxes?
- What metrics do players use to judge "value" in cosmetic items?
- How does time-to-completion affect purchasing behavior?
- Can education (this tool) reduce vulnerability to FOMO and sunk-cost mechanics?

### Key findings

1. **Perceived vs. real value gap:** players typically overvalue cosmetics by 200–300% after unlocking them (endowment effect).
2. **Time-lock premium:** players pay 40–60% more for time-gated items than for permanently available cosmetics that look the same.
3. **Completion heuristic:** players who complete 70%+ of a pass report 26% higher satisfaction, regardless of ROI.
4. **Behavioral shift:** battle passes cut impulsive loot box spending by ~35% while making seasonal spending steadier, which suggests players treat them as budgeted entertainment rather than gambling.

## Data sources and assumptions

All presets are **estimates** and every one is editable in the appendix.

| Game | Price | Tiers | Hours to finish | Season (weeks)* | Items | Avg. item price |
| --- | --- | --- | --- | --- | --- | --- |
| Fortnite | $9.99 | 100 | 75 | 12 | 100 | $1.50 |
| Apex Legends | $9.99 | 110 | 100 | 13 | 110 | $1.45 |
| Valorant | $10.00 | 50 | 50 | 8 | 50 | $2.40 |
| Rocket League | $9.99 | 70 | 60 | 13 | 70 | $1.43 |
| COD Warzone | $19.99 | 100 | 120 | 9 | 100 | $2.00 |

\*Season length is a typical-season estimate added in this version. The other columns come from the 2023 thesis dataset: tier counts and prices from public storefronts, hours to finish from community tier-unlock tracking, and item prices from seasonal cosmetic databases cross-referenced with Newzoo (2022) spending surveys.

Behavioral references: sunk cost from Arkes & Blumer (1985), FOMO mechanics adapted from Zuboff (2019), and the endowment effect for digital goods from Duhachek et al. (2012).

## Technical stack

- **Vanilla JavaScript** in a single `index.html`: no framework, no build step, no in-browser transpiling.
- **[GSAP 3.13](https://gsap.com/)** with **ScrollTrigger** for timelines and scroll-driven scenes, and **[Lenis](https://github.com/darkroomengineering/lenis)** for smooth scrolling. All three load from jsDelivr.
- Hand-built **SVG** for the route map, **canvas** for halftone ramps, and **CSS Grid** for everything else.
- **Google Fonts:** Anybody (display, variable width) and Archivo (text and tables).

This replaces the first version's React + ReactDOM + Babel Standalone + Recharts stack, which shipped several megabytes and transpiled JSX in the browser on every visit. The page now needs about 130 KB of script.

### Accessibility

- Every control works from the keyboard. The custom number scrubbers are ARIA `slider`s with arrow, Page Up/Down, Home and End keys.
- The verdict is announced through a polite live region, and the route map has a descriptive label.
- Text contrast meets WCAG AA, focus rings and text selection are themed, and there is a skip link.
- `prefers-reduced-motion` is fully supported (see *Motion*).

## Run it locally

```bash
npx http-server .
```

Or open `index.html` directly, or host it on GitHub Pages, Netlify or Vercel.

### Embed it

```html
<iframe src="https://your-domain.com/battle-pass-roi/index.html" width="100%" height="1200"></iframe>
```

## File structure

```
battle-pass-roi-calculator/
├── index.html      # the whole app: markup, styles, logic, motion
├── README.md       # this file
├── PRODUCT.md      # product record (users, purpose, principles)
├── DESIGN.md       # the visual system: tokens, type, components, motion
└── .impeccable/    # design-process records (direction contract, detector config)
```

## Future enhancements

- Live game APIs for current-season pass structure and cosmetic pricing
- Currency refunds per pass (many passes pay back premium currency)
- Monte Carlo playtime simulation in place of the steady-pace model
- More games: Genshin Impact, Honkai: Star Rail, FFXIV, WoW seasons, CoD Mobile
- Budget framing: cosmetic spend against a monthly entertainment budget

## Credits

**Author:** Matthew Cromaz. **Original thesis:** Reed College Economics Department, 2023.

### References

- Arkes, H. R., & Blumer, C. (1985). The psychology of sunk cost. *Organizational Behavior and Human Decision Processes.*
- Zuboff, S. (2019). *The Age of Surveillance Capitalism.*
- Duhachek, A., et al. (2012). Emotional responses to unattained goals and implications for consumer choice.
- Newzoo (2022). *Global Games Market Report.*
- GDC talk: "Monetization Psychology in Free-to-Play Games"
- David Perry's analysis of battle pass design patterns (2020–2023)

Unofficial and unaffiliated: game names belong to their publishers. Nothing here is financial advice.

## License

Provided as a portfolio and educational piece. Use freely for non-commercial purposes, personal analysis and education.
