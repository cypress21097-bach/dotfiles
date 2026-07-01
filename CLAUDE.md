# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Environment

- Shell: zsh, macOS arm64 (Apple Silicon)
- Claude Code binary: `~/.local/bin/claude`
- PATH: `~/.local/bin` is prepended to PATH (set in `~/.zshrc`)

## Key Locations

- **OneDrive**: `~/OneDrive` (symlink to `~/Library/CloudStorage/OneDrive-Personal`) — contains aviation documents, regulatory materials (Vietnamese Aviation Regulations)
- **Obsidian Vault**: `~/Documents/Obsidian Vault/`
- **Claude projects memory**: `~/.claude/projects/-Users-bachdo/memory/`
- **Cursor agents/skills**: `~/.cursor/agents/`, `~/.cursor/skills-cursor/`

## Context

This is a home directory, not a code project. The user works in aviation (likely a pilot or flight instructor) — documents cover A320/C909 aircraft, Vietnamese aviation regulations (VAR), crew resource management (CRM), and flight training. When assisting with document work or writing, aviation terminology and regulatory context are relevant.

## Git Workflow

After completing any meaningful unit of work, commit changes with a clear, descriptive message and push to GitHub. Don't batch unrelated changes into a single commit — keep commits focused. This ensures work is never lost and progress is always recoverable from remote.

## Claude Code Setup

- Theme: dark
- Cursor IDE is configured alongside Claude Code with agents for tasks like `review`, `babysit`, `loop`, `split-to-prs`, `create-skill`, `create-rule`, etc.
- Available Cursor skills: `automate`, `canvas`, `onboard`, `review`, `sdk`, `shell`, `statusline`, `update-cli-config`, `update-cursor-settings`
