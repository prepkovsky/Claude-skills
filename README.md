# claude-skills

My own twist on Claude skills — a small collection of `SKILL.md` files I use with Claude Code to get more consistent results out of the tasks I repeat most: writing commits, analyzing websites, designing web interfaces, and researching topics.

Each skill is a self-contained folder: a `SKILL.md` Claude Code reads, and a `README.md` explaining it for you. No dependencies, no build step.

## Skills

- **[commit-message](commit-message/README.md)** — a `git log` you can read back. Every commit gets a title, the reason, and what actually moved, written from the diff rather than the conversation.
- **[web-analysis](web-analysis/README.md)** — paste a link, get the whole site in one summary: what it does, how it's designed, and the details you'd otherwise click through four pages to find.
- **[web-design](web-design/README.md)** — web interfaces that don't look like every other AI-built page, with the keyboard access and interaction states that usually go missing.
- **[web-research](web-research/README.md)** — research you can check: every claim linked where it's made, disagreements left visible, and the gaps named instead of papered over.

## Installing

Skills are picked up from `~/.claude/skills/` (available everywhere) or `.claude/skills/` inside a project (that project only).

```bash
git clone https://github.com/prepkovsky/claude-skills.git
cd claude-skills

# all of them, for every project
cp -r commit-message web-analysis web-design web-research ~/.claude/skills/

# or just one, scoped to the project you're in
cp -r web-design /path/to/your/project/.claude/skills/
```

## Using them

Claude Code reads each skill's `description` and invokes it when the task matches — ask for a commit message and `commit-message` applies itself. You can also call one by name:

```
/web-design a landing page for a freight invoicing tool
```

## Contributing

Contributions and forks are welcome. Open a PR with a new skill or an improvement to an existing one — keep the frontmatter (`name`, `description`) intact, since the description is what decides when the skill fires.

## Issues

Found something broken, or a skill that misfires? Report it in [Issues](https://github.com/prepkovsky/claude-skills/issues).

## License

[MIT](LICENSE).
