# Product

<!-- impeccable:product-schema 1 -->

> Interview substitution: the owner ran this redesign as an unattended `/goal` and asked not to be stopped for questions. Facts below come from the README, the shipped `index.html`, and the goal text. Anything marked *(inferred)* is a reading of that evidence, not a confirmed answer.

## Platform

web

## Stack

Zero-build, single `index.html` that opens straight from disk or any static host (GitHub Pages, Netlify, Vercel). The README promises "no build process". Libraries load from a CDN. *(inferred: dropping in-browser Babel transpilation is acceptable because it slows first paint and the README's zero-build promise is about deployment, not about JSX.)*

## Users

Players of seasonal live-service games (Fortnite, Apex Legends, Valorant, Rocket League, COD Warzone) deciding, usually right as a new season drops, whether to buy that season's premium battle pass. *(inferred)* A second audience is the people reading the author's portfolio: recruiters, game-economics readers, and design or engineering reviewers judging craft.

## Product Purpose

The calculator puts real numbers next to a purchase that game designers built to feel emotional. Given your game and how much you actually play, it shows whether you will finish the pass before the season ends, what the unlocked items are worth versus buying them, what each hour of play costs, and which behavioral traps (sunk cost, FOMO, endowment effect, loss aversion) are in play. Success means the player leaves with a clear yes or no and knows why.

## Positioning

It grows out of an economics thesis: *The Transition from Loot Boxes to Battle Passes in Video Games: Economic Models, Player Behavior, and Long-Term Monetization Sustainability* (Matthew Cromaz, Reed College, 2023). Unlike wiki tier calculators or store pages, it sets the quantitative ROI next to the behavioral economics behind the purchase and does not push either answer.

## Operating Context

The player opens it at the start of a season, often on a phone, often while the game's store screen is still open. They change playtime and game, then read the verdict. Portfolio viewers arrive from a GitHub link or the author's site on a desktop and explore all of it.

## Capabilities and Constraints

- Game presets: tiers, premium price, estimated hours to finish, item count, average item price. These are 2023 estimates from the thesis dataset and must be labeled as estimates.
- Inputs: game, hours per week, premium vs. free, a week to inspect progress at.
- Outputs: completion forecast, weeks to finish, tiers unlocked by a given week, cost per tier and item, ROI vs. buying items individually, savings, cost per hour.
- A behavioral-economics module with sunk cost, FOMO, endowment effect, "what good value means", and a cost-per-hour reality check, each reacting to the user's numbers.
- Runs fully client-side. No accounts, no API, no tracking.
- Season length, want-rate, and editable assumptions are *(inferred)* improvements in the spirit of the README's "Future Enhancements". Every number they introduce is a user-adjustable estimate, never a sourced fact.

## Brand Commitments

- "Transparency over persuasion" (README Design Philosophy): no green BUY NOW buttons, completion is not framed as achievement, an unfinished pass is not framed as failure. The calculator presents completion odds neutrally and explains the traps.
- Plain-language education, not academic jargon, ending in a reality check that reframes the metric as cost per hour of fun.
- Credible inside gaming culture without copying any publisher's UI, logos, or trade dress.
- Author credit: Matthew Cromaz, with the thesis citation.

## Evidence on Hand

- README research findings: players overvalue cosmetics 200–300% after unlocking them, pay a 40–60% time-lock premium, report 26% higher satisfaction once past 70% completion, and spend about 35% less on impulsive loot boxes. These come from the 2023 thesis and keep that attribution.
- Cited literature: Arkes & Blumer (1985), Zuboff (2019), Duhachek et al. (2012), Newzoo (2022).
- No game artwork, logos, or screenshots are licensed. Do not use publisher marks or imagery.
- No testimonials, user counts, or press exist. Do not fabricate any.

## Product Principles

1. The verdict comes first. Every number exists to answer one question: is this pass worth it for me?
2. Neutral, never persuasive. Show the trap; do not set it.
3. Your numbers, not ours. Every preset is an editable estimate, labeled as one.
4. Money and time are the same currency here: hours of play are what the pass actually sells.
5. Education stays tied to the user's own situation, never a generic lecture.

## Accessibility & Inclusion

Must be keyboard-operable, meet WCAG AA contrast, and honor `prefers-reduced-motion`. The brief asks for heavy motion, so reduced motion has to be a designed alternative, not a broken page. *(inferred: no stricter standard was stated.)*
