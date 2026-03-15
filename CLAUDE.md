# CLAUDE.md — Global Preferences

## About Me
- Location: São Paulo, Brazil
- I primarily work with generative AI projects and full-stack applications
- Common stack: TypeScript, React, Node.js, Go, Python, Java
- Package manager: varies by project — always check the lockfile before assuming (`pnpm-lock.yaml`, `package-lock.json`, `yarn.lock`, `go.sum`, `requirements.txt`, `pom.xml`)

## Language
- Always respond in **English**
- Code comments in English (industry standard)
- Commit messages in English following Conventional Commits

## Response Style
- Direct and objective responses — get straight to the point
- Include code examples when they help understanding
- Explain the reasoning behind non-obvious decisions
- If there are multiple valid approaches, present the options with trade-offs

## Commits
- Follow **Conventional Commits**: `feat`, `fix`, `chore`, `docs`, `refactor`, `test`, `perf`
- Messages in English, imperative mood, no trailing period
- Example: `feat(auth): add OAuth2 integration with Google`

## Behavior Rules
- **Never remove commented-out code** without asking first
- **Never refactor beyond the requested scope** without warning
- **Ask before adding new dependencies** — prefer native solutions when viable
- If an out-of-scope issue is identified, **mention but do not fix** without authorization
- For destructive tasks (deleting files, rewriting modules), always confirm first

## Git Workflow
- Conventional Commits in English, imperative mood, no trailing period

## Installed Plugins (official marketplace)
- `agent-sdk-dev` — development with the Anthropic Agent SDK
- `claude-code-setup` — Claude Code configuration and automation
- `claude-md-management` — creation and improvement of CLAUDE.md files
- `code-review` — code review
- `code-simplifier` — code simplification and refactoring
- `commit-commands` — commands for commit, push, and PR
- `feature-dev` — feature development with specialized agents
- `frontend-design` — UI design and implementation
- `hookify` — Claude Code hooks configuration
- `playground` — code exploration and experimentation
- `plugin-dev` — custom plugin and skill creation
- `pr-review-toolkit` — pull request review
- `security-guidance` — security guidance
- `skill-creator` — custom skill creation
- Available LSPs: `clangd`, `csharp`, `gopls`, `jdtls`, `kotlin`, `lua`, `php`, `pyright`, `ruby`, `rust-analyzer`, `swift`, `typescript`

## Generative AI
- Frequent context: LLMs, Anthropic and OpenAI APIs, RAG pipelines, embeddings, agents
- When working with prompts, prefer clarity and structure over brevity
- For AI code, always consider token costs and latency

## TypeScript / Node.js
- Prefer `async/await` over callbacks
- Strict typing — avoid `any` without justification
- Project structure: follow what already exists in the repository

## Python
- Prefer type hints
- Use `uv` or `pip` depending on the project — check the environment first

## Go
- Follow idiomatic Go conventions (`gofmt`, explicit error handling)
- Do not ignore errors with `_` without an explanatory comment

## Java
- Check the Java version and build tool (`maven` or `gradle`) before suggesting code
- Prefer the idiomatic approach of the framework in use (Spring, Quarkus, etc.)