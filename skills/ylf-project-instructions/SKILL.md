---
name: ylf-project-instructions
description: Create or update a project's AGENTS.md or CLAUDE.md with compact YLF coding standards. Use when the user asks to make their coding discipline persistent in the current project, update project instructions, sync AGENTS/CLAUDE guidance, or generate a short rule set for Codex or Claude Code.
---

# YLF Project Instructions

Use this to make YLF coding standards persistent in a project. This skill edits instruction files; it does not execute the coding task itself.

## Workflow

1. Confirm the target.
   - If the user names `AGENTS.md`, update `AGENTS.md`.
   - If the user names `CLAUDE.md`, update `CLAUDE.md`.
   - If the user asks for both, update both.
   - If no target is named, ask which file to update before editing.
   - Completion criterion: the exact target file or files are known.

2. Read the project.
   - Read existing `AGENTS.md`, `CLAUDE.md`, README files, package scripts, test config, and nearby project docs if they exist.
   - Project-specific facts and commands must come from the current project, not from memory.
   - Completion criterion: you know the project's existing instructions, common commands, and whether a YLF section already exists.

3. Merge, do not overwrite.
   - Preserve existing project rules.
   - Add or update one compact YLF section rather than scattering rules through the file.
   - Avoid duplicating rules already present.
   - Keep the wording tool-appropriate: `AGENTS.md` for Codex, `CLAUDE.md` for Claude Code.
   - Completion criterion: project-specific instructions remain intact and the YLF section is short, clear, and non-duplicative.

4. Include the YLF core.
   - Define done before non-trivial work.
   - Read current project rules and nearby code before editing.
   - Ask only for high-impact ambiguity; proceed on clear low-risk tasks.
   - Make surgical changes and avoid unrelated refactors.
   - Prefer existing dependencies or mature open-source packages over custom implementations.
   - Verify with the closest real check: tests, representative script input, browser flow, live service, or targeted fallback.
   - Do not perform git actions unless explicitly asked.
   - Do not batch-delete files or directories; delete only one explicit file path at a time.
   - Report plainly: what changed, result, verification, and any real blocker.
   - Completion criterion: all core rules are represented once, without long examples or copied essays.

5. Verify the edit.
   - Read the final file back.
   - Check that no TODO/template text remains.
   - Check that existing project-specific instructions were not removed.
   - Do not run git commands for verification unless the user explicitly requested git.
   - Completion criterion: the target file contains the intended section and can be used as persistent project guidance.

## Style

Keep the inserted section compact. Prefer a checklist over long prose. Do not paste the full Andrej-style essay or tool tutorials into project files.
