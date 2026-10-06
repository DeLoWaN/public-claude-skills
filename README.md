# Public Claude Skills

A collection of [Claude Code](https://claude.com/claude-code) skills, shared in public.

A skill is a packaged set of instructions for Claude Code. It tells Claude how to carry
out one specific kind of task, step by step. Each skill lives in its own folder with a
`SKILL.md` file that an agent reads and follows.

## Skills

| Skill | Description |
|---|---|
| [linkedin-refresh](linkedin-refresh/SKILL.md) | Rebuild a LinkedIn profile from evidence found in the user's own work tools (git hosting, tickets, mailbox, chat), then update the profile in the browser with the user's approval. |

## Installation

Copy a skill's folder into your Claude Code skills directory, either for one project
(`.claude/skills/`) or for every project (`~/.claude/skills/`):

\`\`\`bash
cp -r linkedin-refresh ~/.claude/skills/
\`\`\`

Claude Code picks up the skill on its next run.

## License

See [LICENSE](LICENSE) if present in this repository, otherwise no license is granted
and all rights are reserved by the author.
