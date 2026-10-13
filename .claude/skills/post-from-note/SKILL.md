---
name: post-from-note
description: Turn one raw note into one post plus an alternative hook. Usage: /post-from-note 00-inbox/file.md [format]
---
# Post from note

Argument: a file path, optionally a format (story | lesson | opinion | how-to | question). Default format: whichever fits the note best, say which and why in one line.

1. Load `identity/voice.md` and `identity/positioning.md`.
2. Read the note. Pick the one idea. If there are two, say so and ask which.
3. Map it to a positioning theme. If it maps to none, say so and ask whether to proceed; off-theme posts dilute the profile.
4. Grep `posts/` for the topic to avoid a repeat.
5. Write `posts/drafts/YYYY-MM-DD-<slug>.md` from `templates/post.md`, same drafting rules as `/weekly-content`.
6. Add a section `## Alternative hook` with a second opening (2 lines) in a different register: if the first is a story opening, make the second a plain claim, and vice versa.
7. Fill "Notes for the owner". Move the note to `archive/inbox/` with `status: used`.
8. Print both hooks. List files changed.
