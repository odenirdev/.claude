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

Do not use any other tools or do anything else.