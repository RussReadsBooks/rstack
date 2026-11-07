---
name: how-to-ask-good-questions
description: >-
  Read before asking the user anything: a clarifying question, a decision, a "should I…", a confirmation, or a choice between approaches. Also read when you're stuck, blocked, or unsure whether to proceed. Covers when to decide yourself instead, and how to package every open question into one message the user can answer as "1A 2B".
---

# How to Ask Good Questions

Never ask the user a naked question. Package every decision with the data and context the user needs to answer in one reply, with no back-and-forth.

Ask only for one-way doors, taste calls, or trade-offs that hinge on the user's goals. Otherwise, decide, act, and say what you decided. If one option is clearly right, do it instead of asking.

## Bad examples (do not do this)
- What calibration records should I use? Want to use moving average smoothing? (two asks, no context, no options)
- What should we do about ticket #32? (naked ticket number, no options)
- Do you want to apply these changes to all the other sub-modules? (no context, no recommendation)

## Question format
1. Number each question (`1.`, `2.`, …). Never send an unnumbered list; every answer must map to a number and a letter.
2. List options as bullets that start with their letter (`- A.`, `- B.`, `- C.`).
3. For each question: one clear ask, 2–3 short sentences of situation, then 2–3 credible options.
4. Recommend one option per question: what best serves the user's short- and long-term goals, not what's least work for you.
5. Put `(recommended)` right after that option's letter. No separate "I recommend X" line.
6. Flag one-way doors in the situation or on that option.
7. Put every open decision in one message, most important first. Do not drip questions.

## Reply shape the user will use

The user replies in one batch: number, letter, optional comment.

```
1B
2A Yes, but log every shutdown
3B
```

## Writing style
- Be succinct. Use plain English; cut jargon and long setup.
- Expand an acronym on first use, e.g. "Quasi-Biennial Oscillation (QBO)". After that, use the acronym.
- Prefer a short Markdown link over a long pasted URL.
- Don't assume the user remembers the context; bring them up to speed. Link tickets with a short title: never a naked #32, but [#32 Refactor UI on Sign-up Page](https://github.com/owner/repo/issues/32).

## Good examples

Examples use made-up data and sources; cite real files or URLs from the project.

**1. Which ADC (analog-to-digital converter) should the photometer use?**
Twilight sky brightness spans about 12 magnitudes (10 to 22 mag/arcsec²). At full dark, a 16-bit ADC sees only a few counts, so precision drops to about ±0.3 mag/arcsec². A 24-bit ADC holds about ±0.02 for about $9 more per unit. This is a one-way door once boards are ordered.

- A. Keep 16-bit and accept ±0.3 at full dark. Cheapest and fastest, but compromises the main science goal.
- B. (recommended) Go to 24-bit now. Full-dark accuracy is the main goal, $9 is small, and a later respin costs 3+ weeks.
- C. Keep 16-bit and add switchable gain. Recovers most dark-sky precision, but adds analog parts and per-gain calibration.

**2. Should the thermal design target worst-case sun load or typical?**
Worst case (summer sun, 45 °C ambient) puts the enclosure at 71 °C, above the battery's 60 °C limit. Typical days peak at 52 °C. The 58 °C firmware shutdown stays in every option, and 2024 weather data says it would trip about 6 afternoons a year.

- A. (recommended) Design for typical days and let the shutdown handle rare hot ones. Simplest hardware, and losing about 6 afternoons a year doesn't hurt the science.
- B. Design for the worst case by adding a sun shield and white finish. This cuts the peak to about 55 °C so the shutdown never trips, for a small increase in cost and complexity.
- C. Refine the 1D thermal model with test data first. Could drop the worst case below 60 °C, but needs a test setup and about a week.

**3. Which dataset should the calibration fit use?**
The record covers 2010–2025, including the January 2022 Hunga Tonga–Hunga Ha'apai (HTHH) eruption. HTHH added stratospheric water vapor that persisted for years, and its bias isn't fully removed yet ([Keith 2025](docs/references/keith-2025.pdf)).

- A. Use the full 2010–2025 record. Longest baseline; the regression absorbs some of the bias.
- B. (recommended) Use 2010–2025 but screen out January 2022 through December 2023. The perturbation is large and one-time, and losing 2 of 16 years costs little.
- C. Stop the fit at 2021. Cleanest, but drops the newest 4 years, including the current hardware era.
