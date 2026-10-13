---
name: monthly-audit
description: Monthly review — the owner pastes LinkedIn analytics (impressions, reactions, comments, profile views per post), the skill scores posts against themes and formats and writes docs/audit-YYYY-MM.md with 3 decisions for next month.
---
# Monthly audit

Needs input from the owner. Ask for it in this shape, one line per post, and accept it pasted messily:

```
YYYY-MM-DD | slug or first words | impressions | reactions | comments | profile views (if known)
```
LinkedIn shows this under each post's "View analytics". Also ask for: profile views this month vs last, search appearances, follower delta. All optional.

## Steps
1. Match each line to a file in `posts/published/` (by date, then by hook). Write the numbers into that file's frontmatter: `impressions:`, `reactions:`, `comments:`.
2. Build two tables: performance by **theme** (from positioning) and by **format**. Median, not mean; one viral post lies.
3. Identify: the best post and why (hook, theme, format, day/time), the worst and why, any theme with zero posts this month.
4. Check cadence: posts per week vs the target in `docs/HOWTO.md`. Say plainly if it was missed.
5. Write `docs/audit-YYYY-MM.md`:
   - the two tables
   - 3 decisions for next month, each one sentence, each actionable (e.g. "two lesson posts on theme 2, none on theme 3", "move the hook's number to the first line")
   - one thing to change in `identity/voice.md` if the data says the voice rules are wrong
6. Propose the edits to `voice.md` and `positioning.md`; apply only on a yes.
7. List files changed.

Never suggest engagement tactics that need automation (pods, auto-comments, bulk connects).
