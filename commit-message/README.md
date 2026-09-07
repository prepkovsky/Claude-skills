# commit-message

**Stop writing "fix stuff". Get a commit message you'll still understand in six months.**

A subject line that reads on its own in `git log --oneline`, a sentence on why the change was needed, and bullets only when the change actually calls for them. Your log becomes something you can read back instead of something you have to `git show` your way through.

It works from the diff, not from the conversation. That's the part that matters: asked for a commit message off the back of a working session, a model summarizes the session — so the thing you fixed in passing goes unmentioned, and the thing you talked about but didn't do can end up in the message. This runs `git status` first, then reads `git diff --cached`, and describes the commit that's actually staged. Unstaged and untracked files stay out of it.

## What you get

```
Short imperative summary, under 72 characters

Why this change is needed — the relevant context, a sentence or two.

- Thematic bullet, only if the change needs them
- Another
```

No markdown headers, and the subject is imperative — "Add retry to upload handler", not "Added retry" or "This adds retry", so it reads the same way as every other line in the log.

Note this isn't [Conventional Commits](https://www.conventionalcommits.org) — no `feat:` or `fix:` prefixes, nothing for a semver tool to parse. It optimizes for a human reading the log.

## Length doesn't follow diff size

The instinct is that a bigger diff deserves a longer message, and following it produces a per-file changelog — the one thing the diff already stores perfectly well. So a 40-file change gets the same length message as a 4-file one; the bullets just get more general.

Small changes get a subject line, or a subject plus one sentence, and no bullets at all. Large ones get at most five bullets, grouped by theme rather than by file. A bullet that names a single file is a bullet that hasn't been generalized yet.

## Using it

Ask for a commit message and it applies itself. Or call it:

```
/commit-message
```

## Installing

```bash
cp -r commit-message ~/.claude/skills/
```

Only `SKILL.md` is read by Claude Code; this README rides along and is ignored.
