---
name: executing-plans
description: Use when implementing a Linear issue without subagent support — one issue per branch/PR, sequential execution
---

# Executing Plans

## Overview

Implement a single Linear issue in the current session. This is the non-subagent alternative to subagent-driven-development. **One issue = one branch = one PR.**

**Announce at start:** "I'm using the executing-plans skill to implement this Linear issue."

**Note:** Tell your human partner that Superpowers works much better with access to subagents. If subagents are available, use linear-superpowers:subagent-driven-development instead.

## The Process

### Step 1: Read the Linear Issue

Read the issue from Linear via MCP:
- Title, description, acceptance criteria
- Labels, priority, assignee
- Project context and related issues

The issue's **Acceptance Criteria** are the spec. Do NOT read from a plan file — the Linear issue is the source of truth.

If concerns: Raise them with your human partner before starting.

### Step 2: Update Status to In Progress

Update the issue status to **In Progress** via Linear MCP.

### Step 3: Create Branch

Create a branch named after the issue:
```
feat/ONE-42-short-description
fix/ONE-43-crash-on-empty-cart
chore/ONE-44-upgrade-react
```

### Step 4: Execute

Implement the issue:
1. Follow acceptance criteria as the spec
2. Use TDD (linear-superpowers:test-driven-development)
3. Run verifications as you go
4. Commit with issue ID: `[ONE-42] Add OAuth login flow`

### Step 5: Update Issue to Done

Update the issue status to **Done** via Linear MCP.

### Step 6: Complete Development

- **REQUIRED:** Use linear-superpowers:finishing-a-development-branch
- Follow that skill to verify tests, create PR
- PR title: `[ONE-42] Issue title`

### After Completion

Let the user know: *"Issue ONE-42 is done. Use linear-superpowers:linear-cycle to continue working through issues, or linear-superpowers:linear-cowork to pull a single issue."*

## Branch and PR Conventions

**One issue = one branch = one PR.** Never combine multiple issues into a single branch.

- Branch name: `{type}/ISSUE-ID-short-description`
- Commit messages: `[ISSUE-ID] description`
- PR title: `[ISSUE-ID] Issue title`

## When to Stop and Ask for Help

**STOP immediately when:**
- Hit a blocker (missing dependency, test fails, instruction unclear)
- Acceptance criteria have gaps preventing progress
- You don't understand a criterion
- Verification fails repeatedly

**Ask for clarification rather than guessing.**

## Remember
- Linear issue is the source of truth, not plan files
- Follow acceptance criteria exactly
- Don't skip verifications
- Stop when blocked, don't guess
- Never start on main/master without explicit user consent
- One issue per branch per PR

## Integration

**Required workflow skills:**
- **linear-superpowers:using-git-worktrees** - REQUIRED: Set up isolated workspace before starting
- **linear-superpowers:linear-cowork** - Creates the Linear issues this skill implements
- **linear-superpowers:linear-cycle** - Orchestrates working through multiple issues in sequence
- **linear-superpowers:finishing-a-development-branch** - Complete development after implementation
