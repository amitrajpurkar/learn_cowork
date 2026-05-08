# selflearn_cowork Usage Guide

**Purpose:** How to use, navigate, and maintain the selflearn_cowork project going forward.
**Audience:** Amit Rajpurkar
**Status:** Draft
**Last updated:** 2026-04-19
**Related documents:** `../README.md`, `claude-cowork-learning-plan.md`, `global-configuration-setup-guide.md`, `../tracking/learning-progress-tracker.md`

---

## Prerequisites

- Claude Cowork desktop app installed and connected to this workspace folder
- Workspace folder path: `/Users/amitrajpurkar/workspace/claude_workspace`
- Terminal access for the one-time installation step in Phase 2

---

## First thing to do after opening this project

1. Open `tracking/learning-progress-tracker.md` and check the current status
2. Identify the next module to tackle from the Module Status table
3. Open `docs/claude-cowork-learning-plan.md` and navigate to that module
4. Work through the module, including its exercise
5. Update the tracker before closing the session

---

## Installing the global configuration (one-time, high priority)

This is the single most impactful action in this project. Do it before proceeding with other modules.

```bash
# 1. Create the ~/.claude directory if it does not exist
mkdir -p ~/.claude

# 2. Copy the configuration file
cp /Users/amitrajpurkar/workspace/claude_workspace/selflearn_cowork/config/global-CLAUDE.md ~/.claude/CLAUDE.md

# 3. Verify installation
cat ~/.claude/CLAUDE.md
```

Then open a new Cowork session and ask: "What do you know about my working style?" — Claude should correctly describe it without prompting.

Full details: `docs/global-configuration-setup-guide.md`

---

## How to update the progress tracker

After every study session, add an entry to `tracking/learning-progress-tracker.md`:

1. Update the module status in the table (Not started → In progress → Complete)
2. Add a dated session entry with: what you covered, what worked, what was unclear
3. Note the next module at the bottom of the session entry
4. Use the format: `### Session N — YYYY-MM-DD`

---

## How to update the global CLAUDE.md over time

As you discover new preferences through usage:

1. Edit `config/global-CLAUDE.md` in this project (the source of truth)
2. Copy the updated file to `~/.claude/CLAUDE.md`:
   ```bash
   cp /Users/amitrajpurkar/workspace/claude_workspace/selflearn_cowork/config/global-CLAUDE.md ~/.claude/CLAUDE.md
   ```
3. Test in a new session

Keep the file under 200 lines. If it grows larger, move topic-specific sections to `~/.claude/rules/` files.

---

## How to add a new learning module

If you discover a new Cowork capability not covered in the plan:

1. Add a new module section to `docs/claude-cowork-learning-plan.md` following the existing format
2. Add a corresponding row to the Module Status table in `tracking/learning-progress-tracker.md`
3. Work through the module and log the session

---

## Known limitations

- The global `~/.claude/CLAUDE.md` applies to Claude Code CLI and Cowork desktop — but verify this holds for your exact Cowork version after installation
- Auto memory files at `~/.claude/projects/` are machine-local and are not committed to this project
- Cowork sessions start fresh — always check the progress tracker at the start of a session to re-establish context
