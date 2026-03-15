# Claude Code — Global Configuration

Personal Claude Code configuration versioned for portability and consistent behavior across all projects and machines.

## What is this repository

`~/.claude` is the Claude Code data directory. By versioning it in git, preferences, commands, and plugins can be synchronized between machines with a single `git clone`.

The `CLAUDE.md` file at the root defines the global assistant behavior — language, stack conventions, commit rules, and more — applied automatically to every project opened with Claude Code.

## Directory structure

```
~/.claude/
├── CLAUDE.md                          # Global preferences (language, stack, commit rules, behavior)
├── settings.json                      # Application JSON settings
├── commands/
│   └── commit.md                      # Enhanced /commit command with CLAUDE.md context
├── plugins/
│   ├── known_marketplaces.json        # Registered plugin marketplaces
│   ├── blocklist.json                 # Blocked plugins
│   └── marketplaces/                  # Downloaded marketplace plugins
└── projects/
    └── -Users-odenirgomes--claude/
        └── memory/                    # Persistent memory for this repository
```

> Files excluded by `.gitignore`: cache, sessions, conversation history, telemetry, and other ephemeral/sensitive data.

## Installed plugins

Plugins installed from the official Claude Code marketplace:

| Plugin | Description |
|---|---|
| `agent-sdk-dev` | Development with the Anthropic Agent SDK |
| `claude-code-setup` | Claude Code configuration and automation |
| `claude-md-management` | Creation and improvement of CLAUDE.md files |
| `code-review` | Code review |
| `code-simplifier` | Code simplification and refactoring |
| `commit-commands` | Commands for commit, push, and PR |
| `feature-dev` | Feature development with specialized agents |
| `frontend-design` | UI design and implementation |
| `hookify` | Claude Code hooks configuration |
| `playground` | Code exploration and experimentation |
| `plugin-dev` | Custom plugin and skill creation |
| `pr-review-toolkit` | Pull request review |
| `security-guidance` | Security guidance |
| `skill-creator` | Custom skill creation |

## Usage on another machine

Clone the repository directly into the Claude Code data directory:

```bash
git clone <repo-url> ~/.claude
```

Then reinstall plugins via the Claude Code marketplace — plugin binaries are not versioned.

## Customization

- **Preferences**: edit `CLAUDE.md` to adjust language, stack conventions, behavior rules, etc.
- **Custom commands**: add `commands/<name>.md` files to create new slash commands
- **Plugins**: install or remove plugins via Claude Code's plugin marketplace

## Author

Odenir Gomes — https://github.com/odenirdev
