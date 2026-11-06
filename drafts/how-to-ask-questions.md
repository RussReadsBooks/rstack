## How to ask this user questions

Never ask a bare clarifying question. Package every decision with the data and context needed so the user can answer from one message.

### Bad examples (do not do this)
- > Should I merge the branch? Also what about the badges?
- > What should we do about ticket #32?
- > Should we go with A? (asked alone, after a long earlier message)

### Style
Be succinct. Prefer plain English. Say more with fewer words. Cut jargon and long setup. Prefer a short Markdown link over a long pasted URL that breaks reading flow.

### Correct Question Format
1. Number each question (`1.`, `2.`, …) so the user can reply `1A, 2B, 3A` plus optional commentary.
2. Letter the options (`A`, `B`, `C`). Each is a real, verified choice with enough detail to pick it.
3. For each question: one clear ask, then 1–2 sentences of situation (what is true now, what hangs on the choice). Prefer plain words. Ticket/PR/issue numbers are OK as short Markdown links when the situation still names the topic in one short phrase. Expand acronyms once in that question unless they are ubiquitous.
4. Put `(recommended)` inline right after the chosen letter, then a short why on that same option. No separate "I recommend X" line after the list.
5. Flag one-way doors in the situation or on that option.
6. Put every open decision in the same message. Do not drip questions, and do not ask the user to invent options.

### Reply shape the user will use
```
1A — "Yes, keep the short path."
2B — "No, let's revisit the badge later."
```

### Good examples

**1. What should we do with the half-finished `feature/cleanup` branch?**
Local branch is 8 commits ahead of `main`, tests pass, nothing is pushed. Merging as-is would ship 2 placeholder values. Deleting loses the scratch notes in the commits.

- **A. Merge to `main` now**, keep the placeholders and a short caveat in the UI.
- **B. (recommended) Strip the placeholders**, merge the rest, leave a TODO for real fills. Placeholders read like facts on screen; notes stay on the branch.
- **C. Leave the branch**, open a draft PR, decide after a local click-through.

**2. Where should the status badge live?**
Every hover card ends with a one-word status. That adds a word to many cards.

- **A. (recommended) Keep the suffix** only when status is not the default. One word, only when it matters.
- **B. Drop the text**; use a visual style plus a one-line legend.
- **C. Drop status from the hover card entirely.**
