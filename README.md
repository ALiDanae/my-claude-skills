# my-claude-skills

Personal Claude Code marketplace. On any new computer:

```bash
gh auth login && gh auth setup-git
claude plugin marketplace add https://github.com/ALiDanae/my-claude-skills.git
claude plugin install local-skills@my-claude-skills example-skills@my-claude-skills design@my-claude-skills gsap-skills@my-claude-skills ui-ux-pro-max@my-claude-skills genjutsu@my-claude-skills linkedin-skills@my-claude-skills
```

Add a new skill: put its folder (with `SKILL.md`) in `plugins/local-skills/skills/`, bump the version in `plugins/local-skills/.claude-plugin/plugin.json`, push, then on each device run `claude plugin marketplace update my-claude-skills`.
