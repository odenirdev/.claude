---
allowed-tools: Bash(git add:*), Bash(git status:*), Bash(git commit:*)
description: Create a git commit
---
## Context
- Current git status: !`git status`
- Current git diff: !`git diff --staged 2>/dev/null || git diff`
- Current branch: !`git branch --show-current`
- Recent commits: !`git log --oneline -10 2>/dev/null || echo "No commits yet"`

## Your task
Based on the above changes, create a single git commit following these rules:

1. If there are staged changes, commit them directly.
2. If there are NO staged changes but there are unstaged changes, ask the user which files they want to stage before committing. Do not run `git add` without explicit user confirmation.
3. If there are no changes at all, inform the user and stop.

Stage and create the commit using a single message. Do not use any other tools or do anything else.