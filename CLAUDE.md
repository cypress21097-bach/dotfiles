# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Environment

- Shell: zsh, macOS arm64 (Apple Silicon)
- Claude Code binary: `~/.local/bin/claude`
- PATH: `~/.local/bin` is prepended to PATH (set in `~/.zshrc`)

## Repository Scope

This git repository is rooted at `~` (home directory), not at `~/OneDrive`. `~/.gitignore` uses an ignore-everything-then-allowlist pattern (`*` then `!.gitignore !CLAUDE.md !.zshrc`), so **only these three files are tracked** — everything else on disk (OneDrive documents, Documents, Desktop, Pictures, etc.) is present but intentionally untracked. Remote: `github.com/cypress21097-bach/dotfiles`.

- `git status` will show clean even though the home directory is full of untracked personal/work files — that's expected, not a problem to fix.
- To track a new file, add an explicit `!filename` line to `~/.gitignore` first, or the add will be silently ignored.
- Git commands (status/diff/add/commit) run from any subdirectory (e.g. `~/OneDrive`) still operate on this same home-directory repo, since that's where `.git` lives.

## Key Locations

- **OneDrive**: `~/OneDrive` (symlink to `~/Library/CloudStorage/OneDrive-Personal`) — contains aviation documents, regulatory materials (Vietnamese Aviation Regulations)
- **Obsidian Vault**: `~/Documents/Obsidian Vault/`
- **Claude projects memory**: `~/.claude/projects/-Users-bachdo/memory/`
- **Cursor agents/skills**: `~/.cursor/agents/`, `~/.cursor/skills-cursor/`

## Context

This is a home directory, not a code project. The user is a pilot — documents cover A320/C909 aircraft, Vietnamese aviation regulations (VAR), crew resource management (CRM), and flight training. When assisting with document work or writing, aviation terminology and regulatory context are relevant.

## Git Workflow

Commit and push to GitHub **regularly as you work** — not only at the end of a task. Treat version control as part of the workflow, not a final cleanup step.

- **Commit often**: After each meaningful, self-contained change (a fix, a feature slice, a doc update), create a commit with a clear, descriptive message that explains *why* the change was made.
- **Push regularly**: Push commits to GitHub frequently so remote always reflects current progress. Work should never exist only on the local machine.
- **Keep commits focused**: One logical change per commit. Don't batch unrelated edits into a single commit.
- **Write clean messages**: Use complete sentences in the imperative mood (e.g. "Add VAR cross-reference table", "Fix broken link in CRM notes"). Avoid vague messages like "updates" or "wip".

The goal is that status and work are never lost — every step of progress should be recoverable from GitHub.

## Claude Code Setup

- Theme: dark
- Cursor IDE is configured alongside Claude Code with agents for tasks like `review`, `babysit`, `loop`, `split-to-prs`, `create-skill`, `create-rule`, etc.
- Available Cursor skills: `automate`, `canvas`, `onboard`, `review`, `sdk`, `shell`, `statusline`, `update-cli-config`, `update-cursor-settings`
