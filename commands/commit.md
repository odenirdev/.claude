---
allowed-tools: Bash(git add:*), Bash(git status:*), Bash(git commit:*), Bash(git log:*), Bash(cat:*)
description: Create a git commit
---
## Context
- Current git status: !`git status`
- Current diff: !`git diff --staged 2>/dev/null || git diff`
- Current branch: !`git branch --show-current`
- Recent commits: !`git log --oneline -10 2>/dev/null || echo "No commits yet"`
- Project context: !`cat CLAUDE.md 2>/dev/null || echo "No CLAUDE.md found"`

## Your task
Based on the above changes, create a single git commit following these rules:

1. If there are no changes at all, inform the user and stop.
2. If there are NO staged changes but there are unstaged changes, ask the user which files they want to stage before committing. Do not run `git add` without explicit user confirmation.
3. If there are staged changes, use the project context from `CLAUDE.md` (if available) to better understand the codebase and write a more meaningful commit message.
   - If `CLAUDE.md` defines a commit convention, follow it strictly.
   - If no convention is defined, default to **Conventional Commits** (`feat`, `fix`, `chore`, `docs`, `refactor`, `test`, `perf`), in English, imperative mood, no trailing period. Example: `feat(auth): add OAuth2 integration with Google`.

## SECURITY RULE — MANDATORY in auto-accept mode

When running in **auto-accept mode** (tools are approved automatically without user interaction), **NEVER execute `git commit` automatically.** Follow this exact sequence:

1. Draft the commit message based on the staged changes and CLAUDE.md conventions.
2. **Show the proposed commit message to the user** in a clearly formatted block.
3. **Stop and wait** for explicit user confirmation before proceeding. Accepted confirmations: "yes", "ok", "sim", "vai", "confirma", "go ahead", "proceed", or equivalent.
4. Only after receiving explicit confirmation, run `git commit`.

In **normal mode** (where the user manually approves each tool call), skip all the steps above and run `git commit` directly — no need to show the proposed message or ask for confirmation. The tool approval prompt is sufficient.

Do not use any other tools or do anything else.