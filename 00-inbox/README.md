# 00-inbox/

Raw material goes here. The weekly skill reads everything in this folder, turns it into drafts, and moves the used files to `archive/inbox/`.

What to drop in, roughly in order of how good a post it makes:

1. **A thing that went wrong and what you did** (incident, bad deploy, wrong architecture call)
2. **Something you explained to a colleague or junior this week** (if you had to explain it, others need it)
3. **A PR description or commit log** for something non-trivial (paste `git log --since="1 week ago" --format="%s%n%b"`)
4. **An opinion you had in a meeting** that people pushed back on
5. **A tool or library you tried** and the verdict in one line
6. **A voice-memo transcript** (talk for 3 minutes on your phone, transcribe with Whisper or the phone's dictation, paste)

Do not tidy. One file per item, any filename. Use `templates/inbox-item.md` if you want structure; plain text is fine.

Never paste: client names you are not allowed to mention, internal URLs, credentials, screenshots of private dashboards.
