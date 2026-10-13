# HOWTO — from dormant account to a steady cadence

Read once. Then the weekly section is the only part you need.

## Week 0 — setup (one afternoon)

### 1. Install and open
```bash
git clone <repo> linkedin-os && cd linkedin-os
rm -rf .git && git init
claude
```
First message to Claude: "Read CLAUDE.md and tell me what you need from me." It will ask for `cv/`.

### 2. Fill `cv/`
- Export your LinkedIn profile as PDF (Me → View profile → More → Save to PDF), paste the text into `cv/cv.md`. Claude can convert it for you: "turn cv/cv.pdf into cv/cv.md".
- Write `cv/projects.md`: one block per project you would talk about in an interview. What, for whom (or "a European airline" if you cannot name them), stack, your role, outcome, numbers.
- Write `cv/public-claims.md`: the five claims you will defend in public, each with where the number comes from.

This step is the one people skip. Skip it and every post is generic.

### 3. Run `/profile-revamp`, session 1
Claude interviews you in four blocks: goal, proof, themes, voice. Answer in messy sentences. It writes `identity/positioning.md` and `identity/voice.md`.

Then open `identity/voice.md` and add the three reference posts and the never/always lists yourself. Ten minutes. This file decides whether the drafts sound like you.

### 4. Run `/profile-revamp`, session 2 (next day)
Claude drafts two headlines, two Abouts, experience bullets and a banner brief. Pick, edit, confirm every number. Apply on LinkedIn:
- headline, About, experience
- profile photo: recent, face fills 60% of the frame, plain background
- banner: make it in Canva from the brief, 1584×396 px
- "Open to" matching your goal
- custom URL
- 5 skills that match your three themes; remove the rest
- Creator mode if you want followers rather than connections (optional)

Commit: `git add -A && git commit -m "profile revamp"`.

## Week 1 onward — the rhythm

### Monday, 20 minutes
1. **Dump (15 min).** Put raw material in `00-inbox/`. Fastest sources for a developer:
   ```bash
   git log --since="1 week ago" --format="%s%n%b" > 00-inbox/$(date +%F)-git-log.md
   ```
   plus a 3-minute voice memo answering "what broke, what did I explain, what did I decide". Transcribe with your phone's dictation or Whisper, paste as a file. Nothing to say? Run `/inbox-dump` and answer its six questions.
2. **Draft (5 min).** Run `/weekly-content`. It shows 3 angles in a table. Say which to draft ("1 and 3", or "all"). It writes them to `posts/drafts/` and prints the hooks.

### Friday, 10 minutes
1. Open each draft. Read "Notes for the owner" first, check every `(inferred)` line.
2. Edit the text in place. If it does not sound like you, fix it and tell Claude what was off: "too formal, I would never say 'leverage'". It updates `voice.md` so it does not happen again.
3. Set `status: approved` or `rejected`.
4. Post on LinkedIn, by hand or via the native scheduler. Spread over the week: Tuesday, Thursday, and one more if you have three.
5. Move the file to `posts/published/`, fill `published:` and `url:`. Or ask Claude: "mark the react post as published at <url>".

### Target cadence
- Weeks 1–4: 2 posts a week. Consistency beats volume while the algorithm re-learns the account exists.
- Month 2 onward: 2–3 a week. Never more than 1 a day.
- Comment on 3 posts by people in your target audience each week, by hand, with something that adds a fact. This matters more than your own posting in the first month.

### Any time
`/post-from-note 00-inbox/<file>.md` turns one note into one post with two hook options. Use it when something happens mid-week that is worth saying while it is fresh.

## First Monday of the month, 20 minutes

Run `/monthly-audit`. Paste the numbers from each post's "View analytics" (impressions, reactions, comments). Claude writes `docs/audit-YYYY-MM.md` with performance by theme and by format and three decisions for next month. Apply its proposed edits to `voice.md` and `positioning.md` if the data supports them.

## Post anatomy (what Claude is aiming for)

```
Hook, 1–2 lines, survives the "see more" fold. A concrete detail or a plain claim.

One idea. 120–220 words. Paragraphs of 1–2 sentences.

Story: what happened → what I did → what I would do differently.
Lesson: the rule → the moment that taught it.
Opinion: the claim → the best counter-argument → why I still hold it.
How-to: 5 numbered steps max.
Question: one I genuinely do not know the answer to.

Close: one plain sentence or one real question. Never "Thoughts?".
```

## What to do when

| Situation | Do |
|---|---|
| Drafts sound generic | `voice.md` is thin. Add the three reference posts and five "never" phrases. Re-run. |
| Drafts contain a wrong fact | Fix `cv/`, not the draft. Then regenerate. |
| Inbox empty three weeks running | The problem is capture, not writing. Put a Monday 09:00 calendar block for the voice memo. |
| A post mentions a client | Check `cv/public-claims.md`. If not listed, anonymise ("a national airline"). |
| Tempted by an automation tool | Don't. Native scheduler or Buffer/Taplio only. |
| Want to change what you are known for | Re-run `/profile-revamp`. Themes change, the system stays. |

## Git

Commit every Friday: `git add -A && git commit -m "week $(date +%V)"`. Push to a **private** repo; `cv/` and the inbox are not for the public.

## Obsidian (optional)

Open the folder as a vault. Turn off "Automatically update internal links" in Files & Links if you rename things through Claude. The `.obsidian/workspace*.json` files are git-ignored.
