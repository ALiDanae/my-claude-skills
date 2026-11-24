# my-claude-skills

Personal Claude Code marketplace. On any new computer:

```bash
gh auth login && gh auth setup-git
claude plugin marketplace add https://github.com/ALiDanae/my-claude-skills.git
claude plugin install local-skills@my-claude-skills example-skills@my-claude-skills design@my-claude-skills gsap-skills@my-claude-skills ui-ux-pro-max@my-claude-skills genjutsu@my-claude-skills linkedin-skills@my-claude-skills sales-skills@my-claude-skills marketing-skills@my-claude-skills book-to-skill@my-claude-skills content-skills@my-claude-skills claude-seo@my-claude-skills claude-blog@my-claude-skills alireza-marketing@my-claude-skills alireza-business-growth@my-claude-skills gtm-skills@my-claude-skills nano-banana-prompts@my-claude-skills social-media-skills@my-claude-skills ai-builder-club@my-claude-skills brianwagner-marketing@my-claude-skills ai-marketing-claude@my-claude-skills cogny-marketing@my-claude-skills stickman-video@my-claude-skills x-mentor@my-claude-skills
```

Add a new skill: put its folder (with `SKILL.md`) in `plugins/local-skills/skills/`, bump the version in `plugins/local-skills/.claude-plugin/plugin.json`, push, then on each device run `claude plugin marketplace update my-claude-skills`.

Optional: `hyperframes@my-claude-skills` (official HeyGen bundle; local-skills already contains a copy of the HyperFrames skills, so install only one).

CLI tools (per device, macOS): `brew install ffmpeg yt-dlp uv && uv tool install openai-whisper`
