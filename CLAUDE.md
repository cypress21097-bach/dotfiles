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

The user is in charge of monitoring cadet pilot training. Work may involve tracking cadet training progress, syllabus and VAR compliance, evaluation records, and related training documentation.

## Report Formatting Standard

**Every remedial training plan and every performance analysis report must use the formatting below.** It is taken from the Safety Remedial Training Plan template (Flight Training & Standard Department, Issue 01/Rev 00, July 2026), which is the house standard. Do not invent a new look per report.

This section governs *appearance*. The prose rules — state the finding, then the evidence, then the consequence; keep instructor and examiner remarks verbatim — live in `~/OneDrive/MAC/CLAUDE.md` and still apply.

### Page

- **A4 portrait**, 8.27 × 11.69 in (595 × 842 pt). Not US Letter.
- Margins **2 cm (0.79 in)** left and right, ~0.6 in top, ~0.5 in bottom.

### Typeface — Calibri throughout

| Element | Size | Weight | Colour |
|---|---|---|---|
| Body text | 11 pt | Regular | `#1F1F1F` |
| Body emphasis | 11 pt | Bold | `#1F1F1F` |
| Section heading (ALL CAPS) | 14 pt | Bold | `#1F1F1F` |
| Sub-heading, `▸` prefixed | 12 pt | Bold | `#1F3864` |
| Inline accent / lead-in | 11 pt | Bold or Italic | `#1F3864` |
| Table header row | 11–13 pt | Bold | `#FFFFFF` on `#1F3864` |
| Header and footer | 8 pt | Regular | `#808080` |

### Palette

| Role | Hex |
|---|---|
| Accent — headings, table headers, sub-heading markers | `#1F3864` |
| Body text | `#1F1F1F` |
| Table borders and rules | `#B7B7B7` |
| Shaded row / panel fill | `#F2F2F2` |
| Text on accent fill | `#FFFFFF` |
| Muted — header, footer, captions | `#808080` |

### Structure

- **Document header block** on every page: department name, document title, `Issue NN / Rev. NN`, document reference, date in `[DD MMM YYYY]`.
- **Footer** on every page: `<document reference> — Internal training record` left, `Page N of M` right.
- **Section headings** in ALL CAPS, 14 pt bold.
- **Sub-headings** prefixed with `▸` in accent navy.
- **Tables** carry a navy header row with white bold text, `#B7B7B7` borders, `#F2F2F2` for shaded rows. Use a table wherever the content is a comparison or a mapping — it is shorter than prose and easier to check.
- **Document reference** format: `REM-TRG-<CompanyID>-<SURNAME FIRSTNAME>-<FlightNo>` for remedial plans. Performance analyses keep `<CompanyID>_<NameNoSpaces>_PerformanceAnalysis_<Topic>`.

### Standard sections

Remedial training plans: Summary table → Background (triggering occurrence, findings by phase, root cause) → Reference → Observable Behaviours with an OB-to-finding traceability table → the training phases, each with its own **Exit Standard** → **If Exit Standard Not Met**, with a defined action per phase.

Every phase states its exit standard in writing, and every exit standard has a defined consequence when it is not met. Both are mandatory — a plan without them is incomplete.

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
