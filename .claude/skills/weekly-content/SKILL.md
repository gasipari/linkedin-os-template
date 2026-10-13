---
name: weekly-content
description: Monday run — read everything in 00-inbox/, propose 3 post angles tied to the positioning themes, draft the approved ones in the owner's voice, move used inputs to archive/inbox/.
---
# Weekly content

Load `identity/voice.md` and `identity/positioning.md`. Then read every file in `00-inbox/` with `status: new` (or no frontmatter).

## Step 1 — propose, do not draft
Grep `posts/published/` and `posts/drafts/` for each candidate topic so you do not repeat a post from the last 60 days.

Present a table of 3 angles (5 if the inbox is rich):

| # | Source file | Angle (one line) | Theme from positioning | Format | Why it works |

Formats: story (what happened, what I did, what I learned), lesson (one rule, the moment that taught it), opinion (claim, the strongest counter-argument, why I still hold it), how-to (numbered, 5 steps max), question (a real one you do not know the answer to).

Stop and ask the owner which ones to draft. Default if they say "all": draft 3.

## Step 2 — draft
For each approved angle write `posts/drafts/YYYY-MM-DD-<slug>.md` from `templates/post.md`.

Rules of the draft:
- Hook: first 2 lines carry the whole post. No "I'm excited", no "Unpopular opinion:", no question stacks. A concrete detail or a plain claim.
- Length: 120–220 words. Over 250 only for a how-to.
- One idea per post. If the inbox item has two, that is two posts.
- Paragraphs of 1–2 sentences, blank line between. LinkedIn collapses after ~3 lines, the hook must survive that.
- No hashtags unless `voice.md` says so. Max 3 if yes, at the end.
- Close: one plain sentence or one real question. Never "Thoughts?" or "Agree?".
- Every number must trace to `cv/` or the inbox item. Fill "Notes for the owner" honestly: facts used, inferred, anonymised.
- Anonymise clients and internal names unless `cv/public-claims.md` allows them.

## Step 3 — write back
- Set the used inbox items to `status: used` and move them to `archive/inbox/`.
- Print the three hooks so the owner can judge in 10 seconds.
- Remind: edit in place, set `status: approved`, post it yourself, move to `posts/published/` with date and URL.
- List the files changed.
