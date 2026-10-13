# LinkedIn OS

A markdown vault plus Claude Code that revives a dormant LinkedIn profile and keeps it alive on 30 minutes a week. Built for developers: your raw material is already in your git log, your PRs and the things you explained to a colleague this week.

No virtual assistant, no scheduling bot, no automation on LinkedIn itself. Claude drafts, you publish.

## What it does

| Job | How | When |
|---|---|---|
| Rewrite the profile (headline, About, experience, banner) | `/profile-revamp` interviews you, drafts two options | Once, week 1 |
| Capture raw material | drop notes in `00-inbox/`, or `/inbox-dump` asks you six questions | Monday, 15 min |
| Draft posts in your voice | `/weekly-content` proposes 3 angles, drafts the ones you pick | Monday, 5 min |
| Turn one note into one post | `/post-from-note <file>` | Any time |
| Learn from the numbers | `/monthly-audit` scores posts by theme and format, writes 3 decisions | First Monday of the month |

## Why it works when the account went dormant before

The account died because writing a post from a blank page costs an hour and the hour never came. Here the blank page is gone: the input is a 3-minute voice memo or a `git log` paste, the draft is written for you, and your job is to approve and click publish. The system fails if you skip the Monday 20 minutes; nothing else can replace that input.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and logged in
- Git
- Any markdown editor. [Obsidian](https://obsidian.md) is nice for the `[[links]]`, not required
- A LinkedIn account you can log into

## Setup in one afternoon

```bash
git clone <this repo> linkedin-os
cd linkedin-os
rm -rf .git && git init           # make it yours
claude                            # start Claude Code in the folder
```

Then, inside Claude Code:

```
/profile-revamp
```

Answer the questions. Come back the next day, run `/profile-revamp` again for the drafting session, apply the copy on LinkedIn by hand. Done with job 1.

Full walkthrough, week by week: [docs/HOWTO.md](docs/HOWTO.md).
Rules Claude follows: [CLAUDE.md](CLAUDE.md).
A finished post, so you know what good looks like: [docs/EXAMPLE-post.md](docs/EXAMPLE-post.md).

## Layout

```
CLAUDE.md               instructions Claude reads every session
identity/voice.md       how you write (fill this, it matters more than anything else)
identity/positioning.md goal, audience, 3 themes, proof points, approved profile copy
cv/                     facts Claude may state publicly
00-inbox/               raw material, consumed weekly
posts/drafts/           waiting for your approval
posts/published/        what went out, with date, URL and numbers
archive/                used inputs and rejected drafts, never deleted
templates/              post and inbox-item templates
docs/                   HOWTO, example post, monthly audits
.claude/skills/         the five skills
```

## The three rules

1. **You click publish.** Claude never touches LinkedIn. Auto-posting, auto-commenting and auto-connecting tools get accounts restricted, and they sound like bots anyway.
2. **Facts come from `cv/`.** Anything Claude infers is marked `(inferred)` in the draft. Check those lines every time.
3. **No client-confidential material in the vault.** Describe the system, not the client's internals.

## Scheduling

Post by hand, or use LinkedIn's native scheduler (clock icon in the post composer, up to 3 months ahead). If you want a third-party tool, use one on LinkedIn's official API (Buffer, Taplio). Never a browser-automation tool.

## License

MIT. Fork it, strip it, rename it.
