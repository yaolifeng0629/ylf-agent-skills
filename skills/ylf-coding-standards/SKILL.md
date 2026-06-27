---
name: ylf-coding-standards
description: Apply compact YLF engineering discipline to the current task. Use when the user explicitly asks for YLF coding standards, wants a concise AGENTS/CLAUDE-style rule set applied to one task, or asks the agent to follow disciplined coding rules before making code changes.
---

# YLF Coding Standards

Use this for the current task only. To make these standards persistent in a project, use `ylf-project-instructions`.

This skill is short on purpose. Adapt by reading the current project, not by carrying every project rule inside this file.

## Process

1. Define done.
   - State the concrete outcome and how you will verify it.
   - For non-trivial work, keep a short checklist and update it as you go.
   - Completion means the requested result is working, verified where possible, and clearly reported.

2. Adapt to the project.
   - Read the active project instructions first: `AGENTS.md`, `CLAUDE.md`, README files, package scripts, test config, and nearby code.
   - Project rules override this skill. This skill fills gaps in how to work.
   - Follow existing patterns, dependencies, naming, file layout, and verification commands.
   - Prefer a mature project dependency or well-maintained open-source package over a custom implementation when that is the normal solution.

3. Clarify only when it matters.
   - If the task is clear and low risk, proceed.
   - Stop and ask before high-impact choices: architecture, data shape, external services, destructive actions, broad refactors, or ambiguous scope.
   - When asking, give your recommended answer and the tradeoff.

4. Change surgically.
   - Make the smallest change that satisfies the request.
   - Do not refactor, reformat, rename, or clean adjacent code unless the task requires it.
   - Remove only unused code that your own change created.
   - If a fix starts cascading into unrelated files, stop and explain the boundary before continuing.

5. Verify for real.
   - Bugs: reproduce first when feasible, then prove the fix.
   - Scripts: run with representative input and inspect output.
   - Web/UI: open the page, check rendering, and exercise the changed flow.
   - Deployments and integrations: check the live service or control plane when access exists.
   - If full verification is blocked by existing environment noise, run the narrowest check that still proves the requested outcome and say what remains unverified.

6. Keep safety boundaries.
   - Do not perform git actions unless the user explicitly asks.
   - Do not batch-delete files or directories. Delete only one explicit file path at a time. If bulk deletion is needed, stop and ask the user to handle it.
   - Do not expose secrets. It is fine to verify that a secret exists or that a name matches.
   - On Windows, separate environment noise such as file locks, pnpm no-TTY issues, or stale build artifacts from the correctness of the change.

7. Report plainly.
   - Tell the user what you changed, what the result is, and what was verified.
   - Mention only unresolved items that genuinely remain.
   - Keep implementation details out of the final report unless the user asks for them.

## Prune

When updating this skill, keep each rule if it changes behavior. Delete long examples, tool tutorials, and project-specific facts. Those belong in project instructions or separate skills.
