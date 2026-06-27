# YLF Agent Skills

Reusable agent skills for disciplined coding work and project instruction maintenance.

[![skills.sh](https://skills.sh/b/yaolifeng0629/ylf-agent-skills)](https://skills.sh/yaolifeng0629/ylf-agent-skills)

## Skills

### ylf-coding-standards

Personal engineering discipline for one task. Use it when you want an agent to slow down enough to read the project, define done, make small changes, verify real outcomes, and report plainly.

### ylf-project-instructions

Create or update a project's `AGENTS.md` or `CLAUDE.md` with compact YLF coding standards. Use it when you want these rules to persist in a project instead of manually invoking a skill every time.

## Install

Install both skills globally:

```bash
npx skills add yaolifeng0629/ylf-agent-skills -g --all
```

Install one skill:

```bash
npx skills add yaolifeng0629/ylf-agent-skills -g --skill ylf-coding-standards
npx skills add yaolifeng0629/ylf-agent-skills -g --skill ylf-project-instructions
```

Preview available skills:

```bash
npx skills add yaolifeng0629/ylf-agent-skills --list
```

## Usage

Apply the standards to the current task:

```text
$ylf-coding-standards Fix this bug and verify the result.
```

Update persistent project instructions:

```text
$ylf-project-instructions Update this project's AGENTS.md with my YLF coding standards.
```

```text
$ylf-project-instructions Update both AGENTS.md and CLAUDE.md for this project.
```

## Principles

- Read the current project before changing it.
- Define what done means before non-trivial work.
- Make the smallest change that solves the request.
- Prefer existing project patterns and mature dependencies.
- Verify with the closest real check available.
- Avoid git actions and destructive file operations unless explicitly requested.
- Report results in plain language.

## Repository Layout

```text
skills/
  ylf-coding-standards/
    SKILL.md
  ylf-project-instructions/
    SKILL.md
    agents/openai.yaml
```

## License

MIT
