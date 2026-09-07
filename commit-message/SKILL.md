---
name: commit-message
description: Writes commit messages. Use when creating a commit, writing a commit message, or when the user asks to summarize changes for a commit.
---

## Read the changes

1. Run `git status` to see what is staged, unstaged, and untracked.
2. Run `git diff --cached` — the staged changes are what's being committed. If nothing is staged, use `git diff HEAD` instead.

Describe only what is actually being committed. Unstaged and untracked files don't belong in the message.

## Format

A subject line, a blank line, then the body:

```
Short imperative summary, under 72 characters

Why this change is needed — the relevant context, a sentence or two.

- Thematic bullet, only if the change needs them
- Another
```

No markdown headers. The subject line is what shows up in `git log --oneline`, so it has to stand on its own.

Write the subject in the imperative: "Add retry to upload handler", not "Added retry" or "This adds retry".

## Length

Message length does not scale with diff size. A 40-file change gets the same length message as a 4-file one — the bullets just get more general.

- Small changes: subject line only, or subject plus one sentence. No bullets.
- Large changes: at most 5 bullets, grouped by theme, not by file. If you're writing one bullet per file, collapse them into a single bullet naming the theme.

Never enumerate files, functions, or line-level edits. The diff already records those; the message exists to say what they add up to.
