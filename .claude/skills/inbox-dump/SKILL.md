---
name: inbox-dump
description: Guided 15-minute capture — asks the owner six questions about the week and writes the answers as raw items into 00-inbox/. Use when the inbox is empty on Monday.
---
# Inbox dump

For weeks when the owner has nothing in `00-inbox/`. Do not draft posts here; only capture.

Ask these, one at a time. Accept short, messy answers. Say "next" if nothing comes to mind.

1. What broke this week, or nearly broke, and what did you do?
2. What did you explain to someone this week that they did not know?
3. What did you decide in a meeting that someone pushed back on?
4. What did you try (tool, library, approach) and what is the verdict in one line?
5. What did you ship, and what was the hardest part?
6. What did you read or watch about your field that you disagreed with?

If the owner has a git repo handy, suggest:
```
git log --since="1 week ago" --format="%s%n%b" > 00-inbox/$(date +%F)-git-log.md
```

Write each non-empty answer as its own file `00-inbox/YYYY-MM-DD-<slug>.md` using `templates/inbox-item.md`, `kind: conversation`, verbatim, no polishing. Report the file list. Suggest running `/weekly-content` next.
