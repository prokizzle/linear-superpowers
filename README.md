# Linear Superpowers

Linear Superpowers extends [Superpowers](https://github.com/obra/superpowers) with Linear integration skills for Claude Code. It connects Linear's issue tracking with the Superpowers agentic development workflow — so your coding agent can triage issues, work through prioritized backlogs, and convert implementation plans into tracked Linear projects.

## What's Different from Superpowers?

This plugin includes all the core Superpowers skills (brainstorming, TDD, subagent-driven development, etc.) plus three Linear-specific skills:

- **linear-triage** — Process the Linear triage queue. Brainstorms each item into a fully spec'd issue with title, background, acceptance criteria, label, and priority. Rejects or merges duplicates.

- **linear-cycle** — Continuous development loop. Pulls the highest-priority fully spec'd Todo issue, executes it, then pulls the next one. Flags incomplete issues for triage instead of blocking.

- **linear-cowork** — Convert implementation plans into Linear projects and issues. Owns the issue-creation workflow and shared conventions that all Linear skills follow.

## How It Works

The Linear skills layer on top of the standard Superpowers workflow:

1. **Triage** → `linear-triage` processes your queue, brainstorming each item into a spec'd issue
2. **Brainstorm** → Design refinement through questions, saved as a design document
3. **Plan** → Break work into bite-sized tasks with exact file paths and verification steps
4. **Create issues** → `linear-cowork` converts the plan into a Linear project with tracked issues
5. **Execute** → `linear-cycle` pulls issues by priority, executes each one with subagent-driven development
6. **Review** → Two-stage review per task (spec compliance, then code quality)
7. **Finish** → Verify tests, merge/PR, clean up

Linear remains the source of truth throughout. Every piece of work flows through a tracked issue.

## Prerequisites

The Linear skills require the [Linear MCP server](https://github.com/linear/linear-mcp) to be installed and authenticated. See `skills/linear-cowork/setup-guide.md` for setup instructions.

## Installation

Install as a Claude Code plugin:

```bash
/plugin marketplace add prokizzle/linear-superpowers
/plugin install linear-superpowers@linear-superpowers
```

### Verify Installation

Start a new session and ask to "process the triage queue" or "work through my Linear issues." The agent should invoke the relevant Linear skill.

## All Skills

### Linear Integration
- **linear-triage** — Process triage queue into spec'd issues
- **linear-cycle** — Continuous issue execution loop
- **linear-cowork** — Plan-to-issues conversion and shared conventions

### Development Workflow
- **brainstorming** — Socratic design refinement
- **writing-plans** — Detailed implementation plans
- **executing-plans** — Batch execution with checkpoints
- **subagent-driven-development** — Fast iteration with two-stage review
- **dispatching-parallel-agents** — Concurrent subagent workflows

### Testing & Debugging
- **test-driven-development** — RED-GREEN-REFACTOR cycle
- **systematic-debugging** — 4-phase root cause process
- **verification-before-completion** — Verify before declaring success

### Collaboration
- **requesting-code-review** — Pre-review checklist
- **receiving-code-review** — Responding to feedback
- **using-git-worktrees** — Parallel development branches
- **finishing-a-development-branch** — Merge/PR decision workflow

### Meta
- **writing-skills** — Create new skills following best practices
- **using-superpowers** — Introduction to the skills system

## Philosophy

- **Linear is the source of truth** — All work flows through tracked issues
- **Test-Driven Development** — Write tests first, always
- **Systematic over ad-hoc** — Process over guessing
- **Complexity reduction** — Simplicity as primary goal
- **Evidence over claims** — Verify before declaring success

## Contributing

1. Fork the repository
2. Create a branch for your skill
3. Follow the `writing-skills` skill for creating and testing new skills
4. Submit a PR

See `skills/writing-skills/SKILL.md` for the complete guide.

## Upstream

This project is built on top of [Superpowers](https://github.com/obra/superpowers) by [Jesse Vincent](https://github.com/obra). If Superpowers has helped you, consider [sponsoring his opensource work](https://github.com/sponsors/obra).

## License

MIT License — see LICENSE file for details

## Support

- **Issues**: https://github.com/prokizzle/linear-superpowers/issues
- **Upstream Superpowers**: https://github.com/obra/superpowers
