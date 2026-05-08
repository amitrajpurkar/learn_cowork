# Claude Cowork Learning Plan

**Purpose:** A phased, structured plan for building mastery of Claude Cowork — from foundational understanding through advanced workflow design.
**Audience:** Amit Rajpurkar (personal study plan)
**Status:** Draft
**Last updated:** 2026-04-19
**Related documents:** `../README.md`, `../tracking/learning-progress-tracker.md`, `global-configuration-setup-guide.md`

---

## How to use this plan

Work through the phases in sequence. Each phase builds on the previous. For each module:

1. Read the linked documentation or complete the referenced exercise
2. Apply the concept in a real Cowork session
3. Record what you learned in `tracking/learning-progress-tracker.md`
4. Note any open questions — revisit them in a later session

Do not skip the configuration phase (Phase 2) — it is the highest-leverage investment in this entire plan. Time spent setting up the global `CLAUDE.md` pays back on every future session.

---

## Phase 1 — Foundations: How Cowork Works

**Objective:** Understand the Cowork model, how sessions work, and what distinguishes Cowork from Claude on the web and Claude Code.

**Estimated time:** 2–3 study sessions

### Module 1.1 — What Claude Cowork is

**Key concepts to understand:**

- Cowork is a desktop tool designed for non-developers to automate file and task management
- It runs on top of Claude Code and the Claude Agent SDK — but it is not Claude Code
- Cowork has access to a workspace folder you select on your machine; files saved there persist
- Every session starts with a fresh context window — nothing from the previous session is remembered unless it is written to a file or configured via `CLAUDE.md`

**Key distinction from Claude web:** Claude web is a conversational interface. Cowork has file access, can run code in a sandboxed Linux shell, can use browser automation, and can execute skills and scheduled tasks.

**Key distinction from Claude Code:** Claude Code is a terminal-based agentic coding tool. Cowork is a desktop GUI designed for broader task and file work, not exclusively code.

**Exercise:** Open Cowork, ask Claude to create a simple test file in your workspace folder, then verify the file appears on your machine. This confirms the workspace connection is working.

---

### Module 1.2 — Sessions, context, and memory

**Key concepts to understand:**

- Each Cowork session is stateless by default — Claude starts with no memory of prior sessions
- The workspace folder persists across sessions — files saved there are available next time
- Two mechanisms carry knowledge across sessions:
  1. **CLAUDE.md files** — instructions you write that Claude reads at the start of every session
  2. **Auto memory** — notes Claude writes to itself based on patterns and corrections it observes

**Why this matters:** If you re-explain your preferences every session, you are not using Cowork effectively. The goal of Phase 2 is to eliminate all that re-explanation.

**Exercise:** In a new session, note what Claude does NOT know about you. Each item you find yourself re-explaining is a candidate for your global `~/.claude/CLAUDE.md`.

---

### Module 1.3 — File access and workspace model

**Key concepts to understand:**

- Cowork accesses your machine through a folder you select — this becomes your workspace
- Files inside the workspace can be read, created, and edited by Claude
- Files outside the workspace are not accessible without explicitly requesting access to another folder
- The workspace folder path on your machine: `/Users/amitrajpurkar/workspace/claude_workspace`

**Important operations:**
- Creating files: use Write or Edit tools (Claude does this automatically)
- Reading files: Claude can read any file in the workspace
- Deleting files: requires explicit permission — Claude will ask before deleting

**Exercise:** Ask Claude to list the contents of your workspace, then ask it to read one of your existing files and summarise it.

---

## Phase 2 — Configuration: Teaching Claude Who You Are

**Objective:** Set up the global `CLAUDE.md` file so that every future Cowork session starts with full knowledge of your personality, working style, problem-solving approach, and output preferences.

**Estimated time:** 1–2 sessions (this phase requires installation steps, not just reading)

**This is the highest-priority phase.** Do not defer it.

---

### Module 2.1 — Understanding CLAUDE.md file scopes

**Key concepts to understand:**

Claude reads `CLAUDE.md` files from multiple locations, each with a different scope. More specific locations override broader ones.

| Scope | Location on your Mac | Who it applies to |
|---|---|---|
| **Global (user)** | `~/.claude/CLAUDE.md` | You, across all projects |
| **Project** | `./CLAUDE.md` or `./.claude/CLAUDE.md` | Everyone on the project (via git) |
| **Project-local** | `./CLAUDE.local.md` | You only, for that project (gitignored) |
| **Rules directory** | `~/.claude/rules/*.md` | You, scoped to file types or paths |

For personal configuration — your personality, working style, output preferences — the correct location is `~/.claude/CLAUDE.md`. This file loads at the start of every session, for every project, on your machine.

**Exercise:** Run `ls ~/.claude/` in your terminal to see what currently exists in your Claude configuration directory.

---

### Module 2.2 — Installing your global CLAUDE.md

**Prerequisite:** Read `global-configuration-setup-guide.md` in full before executing this module.

**Steps:**

1. Locate the ready-to-install configuration file: `config/global-CLAUDE.md` in this project
2. Follow the installation instructions in `global-configuration-setup-guide.md`
3. In a new Cowork session after installation, verify Claude reads your configuration by asking: "What do you know about my working style and output preferences?"

**Verification criterion:** Claude should correctly describe your problem-solving stages, naming conventions, output format preference (markdown), and working style (iterative drafts, explicit plans before execution) without you having explained any of it.

---

### Module 2.3 — Auto memory: how Claude learns from corrections

**Key concepts to understand:**

- Auto memory is on by default in Claude Code / Cowork v2.1.59+
- When you correct Claude or express a preference, Claude saves a note to `~/.claude/projects/<project>/memory/MEMORY.md`
- These notes are loaded at the start of future sessions for that project
- You can view and edit auto memory files — they are plain markdown

**How it works with your global CLAUDE.md:**
- Your global `CLAUDE.md` provides the baseline instructions for every session
- Auto memory adds project-specific learnings on top of the baseline
- The two systems are complementary, not competing

**Exercise:** In a session, correct Claude on something (e.g., tell it you prefer numbered lists over bullets for sequential steps). Then start a new session and ask Claude what it remembers about your list preferences. Check if auto memory captured it.

---

### Module 2.4 — Project-level rules with .claude/rules/

**Key concepts to understand:**

- For any specific project, you can add a `.claude/rules/` directory with topic-specific markdown files
- Rules in this directory load every session for that project
- Rules can be path-scoped — only loading when Claude works on files matching a pattern
- This keeps your global `CLAUDE.md` clean and project-specific standards separate

**When to use rules vs global CLAUDE.md:**

| Instruction type | Where to put it |
|---|---|
| Applies to all your work everywhere | `~/.claude/CLAUDE.md` |
| Applies to one project, shared with team | `./CLAUDE.md` |
| Applies to one project, personal only | `./CLAUDE.local.md` |
| Applies only to TypeScript files in a project | `.claude/rules/typescript.md` with path frontmatter |

**Exercise:** For this `selflearn_cowork` project, create a `.claude/CLAUDE.md` that tells Claude to always update the progress tracker when a module is completed.

---

## Phase 3 — Skills: Extending What Cowork Can Do

**Objective:** Understand what Cowork skills are, when to use them, and how to invoke them effectively.

**Estimated time:** 2–3 study sessions

---

### Module 3.1 — What skills are

**Key concepts to understand:**

- Skills are installable bundles that give Claude specialized capabilities for specific tasks
- Built-in skills in your current setup: `pptx`, `docx`, `pdf`, `xlsx`, `schedule`, `skill-creator`
- Skills are stored as `SKILL.md` files that Claude reads when invoked — they contain expert instructions built up by trial and error
- Skills load on demand, not at every session start (unlike CLAUDE.md)

**How to invoke a skill:** Simply ask Claude to do something that matches the skill's domain. For example:
- "Create a PowerPoint presentation about X" → triggers `pptx` skill
- "Read this Word document and fix the grammar" → triggers `docx` skill
- "Create a scheduled task to run every Monday" → triggers `schedule` skill

---

### Module 3.2 — Document skills: pptx, docx, xlsx, pdf

**Objective:** Be able to create, read, and edit all four major document types using skills.

**Exercise for each skill:**

**PPTX:** Ask Claude to create a 5-slide presentation summarising the phases in this learning plan. Verify the file opens correctly in PowerPoint or Keynote.

**DOCX:** Ask Claude to convert one of your markdown files (e.g., `about-me.md`) into a formatted Word document with a title page. Verify formatting is correct.

**XLSX:** Ask Claude to create a spreadsheet that tracks your learning progress with a row per module, columns for status and notes, and a summary row. Verify formulas work.

**PDF:** Ask Claude to read a PDF you have in your workspace and extract its key points into a markdown summary file.

---

### Module 3.3 — The schedule skill

**Objective:** Create at least one scheduled or on-demand task using the `schedule` skill.

**Key concepts:**

- Scheduled tasks run automatically on a cron schedule, or manually on demand
- Task prompts are stored as `SKILL.md` files in `~/Documents/Claude/Scheduled/`
- Tasks run in new Cowork sessions — they have the same context as a fresh session

**Exercise:** Create an on-demand task called `weekly-cowork-review` that:
1. Reads the progress tracker file
2. Summarises what was learned in the most recent session
3. Identifies the next module to tackle
4. Saves a brief session summary to a log file

---

### Module 3.4 — The skill-creator skill

**Objective:** Understand how to create a custom skill for a repeating workflow you own.

**Key concepts:**

- Custom skills are markdown files (`SKILL.md`) that contain instructions for a specific workflow
- Useful for: any task you perform repeatedly where you want consistent, expert-level output
- The `skill-creator` skill helps you create, test, and optimise new skills

**Exercise:** Identify one repeating task in your architecture work (e.g., producing an ADR, creating a C4 context diagram). Ask the `skill-creator` skill to help you create a custom skill for it.

---

## Phase 4 — Browser Automation: Claude in Chrome

**Objective:** Understand how to use Claude's browser automation capability for research and web-based workflows.

**Estimated time:** 1–2 study sessions

---

### Module 4.1 — What Claude in Chrome can do

**Key concepts:**

- Claude in Chrome is a separate tool (a Chrome extension) that gives Claude access to your browser
- Capabilities: navigate to URLs, read page content, interact with forms, take screenshots, extract data
- Use cases: web research, filling forms, extracting structured data from websites, capturing content for analysis

**Important limitations:**
- Cannot access authenticated content without permission
- Cannot fill in sensitive financial or identity data (by design — security rule)
- Will stop and ask for confirmation before submitting forms or making purchases

**Exercise:** Ask Claude to navigate to the [Claude documentation](https://docs.claude.com) and give you a summary of what's on the main page. Verify Claude successfully reads the page.

---

### Module 4.2 — Research workflows with browser + file

**Objective:** Combine browser access with file creation for a complete research workflow.

**Exercise:** Ask Claude to:
1. Search for the latest Anthropic blog post about Claude
2. Read the post
3. Produce a structured markdown summary saved to your workspace

This combines the browser tool (navigate + read) with the file tools (write) in a single workflow — a pattern you will use frequently.

---

## Phase 5 — Advanced: Multi-Tool Workflows and Optimisation

**Objective:** Combine multiple tools and skills into workflows that handle complex, multi-step tasks reliably.

**Estimated time:** Ongoing — this phase does not have a defined endpoint

---

### Module 5.1 — Workflow design principles

**Key concepts:**

- Complex tasks should be broken into atomic steps before asking Claude to execute them
- Match this to your problem-solving approach from `problem-solving.md` — decompose first, design unit by unit
- For tasks involving multiple files and tools, consider creating a custom skill so the workflow is repeatable

**Exercise:** Take any recurring task from your architecture work. Map it as a workflow: what inputs are needed, what tools would Claude use, what outputs are produced. Then execute it in Cowork and iterate until the output meets your standard.

---

### Module 5.2 — Maintaining and evolving your configuration

**Key concepts:**

- Your `~/.claude/CLAUDE.md` should evolve as you discover new preferences or constraints
- When Claude makes the same mistake twice, add a rule to CLAUDE.md — do not just correct it in-session
- Periodically review your CLAUDE.md to remove outdated instructions (targeting under 200 lines)
- Use project-level rules to keep project-specific standards separate from your global config

**Exercise:** After completing Phase 2, run three Cowork sessions on real work tasks. After each session, note any instructions you had to repeat or corrections you had to make. Add anything recurring to your CLAUDE.md.

---

## Open questions

- [ ] What is the exact version of Cowork / Claude Code running on this machine? — check via `claude --version` in terminal
- [ ] Is auto memory enabled by default in the current Cowork version? — verify by checking `~/.claude/projects/` after a session
- [ ] Are there additional skills beyond the six currently installed? — check the Anthropic skills marketplace

---

## Resources

| Resource | URL | Notes |
|---|---|---|
| Claude 101 course | https://anthropic.skilljar.com/claude-101 | Starting point — foundational concepts |
| Claude Code / Cowork docs | https://docs.claude.com | Official documentation |
| Memory and CLAUDE.md | https://code.claude.com/docs/en/memory | CLAUDE.md and auto memory reference |
| Settings reference | https://docs.claude.com/en/docs/claude-code/settings | Configuration options |
| Skills reference | https://docs.claude.com/en/docs/claude-code/skills | Skills documentation |
