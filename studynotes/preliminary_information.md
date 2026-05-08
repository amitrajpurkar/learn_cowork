# Preliminary Information — Claude, Cowork, and Configuration

**Purpose:** Consolidated study notes drawn from three onboarding infographics and the global configuration setup guide, forming the foundation for structured Cowork learning.
**Audience:** Amit Rajpurkar
**Status:** Draft
**Last updated:** 2026-05-08
**Related documents:** `../docs/global-configuration-setup-guide.md`, `../docs/claude-cowork-learning-plan.md`, `../infographics/claude_intro.JPG`, `../infographics/cowork_intro.JPG`, `../infographics/claude_config_01.JPG`

---

## 1. What Claude Is — Core Concepts

*Source: `claude_intro.JPG` — "Claude For Dummies"*

Claude is an AI assistant made by Anthropic. It writes, summarises, analyses documents, and works with files. It is not the same as ChatGPT — different underlying model, different personality, different strengths.

**Access points:**

- **Claude.ai** — browser-based, free plan available; closest to a ChatGPT-style interface. Best for first-timers.
- **Desktop App** (Mac/Windows) — same account as the browser but adds local file access and unlocks Cowork mode. Best for anyone ready to work with real files.
- **Cowork** — the automation layer inside the desktop app. Claude runs for minutes to hours, doing real tasks autonomously. Best suited to repetitive work: invoices, reports, processing pipelines.

**Pricing tiers (as of infographic):**

- Free — functional but token-capped
- Pro — $20/month (most people land here)
- Max — $100–$200/month for daily power users; pay monthly, not annually

**Where Claude is strong:**

- Writing in the user's voice with examples provided
- Summarising long documents (200-page PDFs) without losing track
- First drafts, document analysis, long-form content
- Tasks where the output format is well-specified

**Where Claude falls short:**

- Real-time news and live data — use Grok for fast search
- Deep research with citations — use ChatGPT
- Precise math without code — use ChatGPT
- Image generation — use ChatGPT or dedicated tools

**Prompting rules (summary):**

Be specific. Give examples. Say what you want, not what you don't want. Start short. Add detail. Open a fresh chat when things get unclear or the context window fills.

**Memory and tokens:**

Claude reads in chunks of approximately 500 tokens per page. Every chat session has a context limit. When Claude starts acting dumb, the memory is full — open a fresh chat.

---

## 2. Getting Started with Cowork — 7-Step Framework

*Source: `cowork_intro.JPG` — "7 Steps to Master Claude Cowork in One Week"*

### Step 1 — Download the desktop app

Go to **claude.com/download**. Cowork only runs in the desktop app, not the browser.

Model selection guidance:
- **Opus 4.6** — for complex, multi-step tasks
- **Sonnet** — for most everyday work

### Step 2 — Build your folder structure

Create a folder called `Claude Cowork` and inside it three subfolders:

```
Claude Cowork/
├── ABOUT ME/
├── OUTPUTS/
└── TEMPLATES/
```

Cowork has real read/write access only to the folder you point it at. `ABOUT ME` is the only folder Cowork reads from at the start; it reads `OUTPUTS` and `TEMPLATES` only when you point to them.

### Step 3 — Write three core context files

All three files live in the `ABOUT ME` folder. Keep all three files under 6,000 tokens total — Cowork reads them completely.

| File | Purpose |
|---|---|
| `about-me.md` | Who you are, what you do, how you work, your standards |
| `anti-ai-writing-style.md` | Every word and pattern Claude must never use. The "AI slop" filter — removes filler, hedging, and robotic phrases |
| `my-company.md` | Your targets, your strategy, what you are working on, what you are saying no to. Update it quarterly |

### Step 4 — Set Global Instructions once

Go to **Settings → Cowork → Edit Global Instructions**. Write your standing rules here so you never have to repeat them.

Suggested rules to include:
- Before every task, read every file in `ABOUT ME`
- Never read `OUTPUTS` or `TEMPLATES` unless explicitly pointed to a file
- Save all deliverables in `OUTPUTS` under a subfolder per project
- If the brief is under 10 words long, ask a clarifying question before starting

### Step 5 — Install Wispr Flow (optional but high-leverage)

Voice-to-text tool. Free tier: 2,000 words per week. Speak prompts rather than type them. Prompts become longer, richer, and faster with minimal effort.

### Step 6 — Use one master prompt for everything

The pattern: describe the role, paste the brief, specify the output format. One well-constructed prompt replaces back-and-forth iteration. Combine with voice input for speed.

### Step 7 — Manage sessions to protect your credits

Sessions degrade. Key habits:
- Do not follow up endlessly in one session — every message re-reads the entire history (context cost)
- Start a fresh session every 30 messages, or any time Claude loses the thread
- Batch tasks: 3 separate prompts → 1 combined prompt with 3 tasks and 1 reload
- Keep files small — Cowork reads thousands of tokens; bloated files burn credits on every prompt
- Use `@` to reference specific files rather than letting Cowork re-read everything

---

## 3. Anatomy of the `.claude/` Directory

*Source: `claude_config_01.JPG` — "Anatomy of .claude/ — 2026 edition" by Brij Kishore Pandey*

Claude's configuration lives in two distinct scopes. Understanding this distinction is the foundation of all personalisation work.

### Project scope — committed to git, shared with the team

These files live inside your project repository:

```
your-project/
├── CLAUDE.md                  ← team instructions
├── CLAUDE.local.md            ← gitignored (personal overrides)
├── .mcp.json                  ← team MCP servers
├── .worktreeinclude           ← NEW (2026)
└── .claude/                   ← control centre
    ├── settings.json          ← permissions, hooks, env vars
    ├── settings.local.json
    ├── rules/                 ← modular instruction files
    ├── commands/              ← slash commands → e.g., /review
    ├── skills/                ← skill definitions (<name>/SKILL.md)
    ├── output-styles/         ← NEW (2026)
    ├── agents/                ← subagent personas
    └── agent-memory/          ← NEW; persists across sessions
```

### Global scope — personal, applies to every project

These files live on your machine, not in any repo:

```
~/.claude/
├── CLAUDE.md                  ← global instructions (applies to all projects)
├── settings.json              ← personal defaults
├── keybindings.json
├── plugins/                   ← do not delete
├── projects/                  ← auto-memory → <project>/memory/
├── commands/                  ← personal slash commands
├── skills/                    ← available everywhere
├── agents/                    ← your own subagents
└── agent-memory/              ← NEW; survives across projects
```

### What is actually loaded at session start

| Slot | What it contains |
|---|---|
| `/context` | Tokens by category |
| `/memory` | CLAUDE.md + rules |
| `/agents` | Subagents configured |
| `/hooks` | Active hooks |
| `/mcp` | MCP servers |
| `/skills` | Skills available |
| `/permissions` | Allow / deny rules |
| `/doctor` | Full diagnostics |

### The mental model — each folder is a dimension of behaviour

```
rules/         → what Claude knows
commands/      → what it does
skills/        → how it works
agents/        → who it becomes
agent-memory/  → what it remembers
output-styles/ → how it communicates
```

**Core principle:** Two `.claude/` directories. One controls the team. One controls you. Learn both.

---

## 4. Work Required — Installing the Global CLAUDE.md

*Source: `../docs/global-configuration-setup-guide.md`*

The global `~/.claude/CLAUDE.md` is the highest-priority configuration action in this learning plan. Without it, every session starts blank — Claude has no knowledge of working style, problem-solving approach, output preferences, or what to avoid.

The ready-to-install configuration file already exists at:

```
selflearn_cowork/config/global-CLAUDE.md
```

### Steps to complete

**Step 1 — Confirm the directory exists**

```bash
ls ~/.claude/
```

If absent:

```bash
mkdir -p ~/.claude
```

**Step 2 — Check for an existing CLAUDE.md**

```bash
cat ~/.claude/CLAUDE.md
```

If a file already exists, review before overwriting — merge rather than replace.

**Step 3 — Install the configuration file**

```bash
cp /Users/amitrajpurkar/workspace/claude_workspace/selflearn_cowork/config/global-CLAUDE.md ~/.claude/CLAUDE.md
```

Verify installation:

```bash
cat ~/.claude/CLAUDE.md
```

**Step 4 — Verify Claude reads it**

Open a new Cowork session and ask:

```
What do you know about my working style and output preferences?
```

Expected: Claude describes iterative working style, explicit plans before execution, markdown as primary format, naming conventions, and the seven problem-solving stages — without any prompting.

If Claude does not, check:
- Path is exactly `~/.claude/CLAUDE.md` (case-sensitive on macOS)
- File is not empty
- This is a genuinely new session, not a continuation

**Step 5 — Optional: set up a rules directory for modular control**

```bash
mkdir -p ~/.claude/rules
```

Example files to create inside:
- `architecture-standards.md` — TOGAF, DDD, C4 usage rules
- `adr-conventions.md` — when and how to write ADRs

### Open questions (unresolved as of 2026-04-19)

- Does Cowork desktop read `~/.claude/CLAUDE.md` in the same way Claude Code CLI does? **Finding from prior session: it does NOT.** Use the project `CLAUDE.md` and auto-memory instead until this is confirmed resolved.
- Is there a way to view which CLAUDE.md files were loaded in a given Cowork session? In Claude Code CLI this is the `/memory` command — confirm availability in Cowork desktop.

### Relationship between CLAUDE.md and auto-memory

Both are loaded at session start and are complementary:

| System | Written by | Scope | Captures |
|---|---|---|---|
| `~/.claude/CLAUDE.md` | You | All projects | Personality, style, standing rules |
| Auto memory | Claude | Per project | Project-specific learnings, corrections |

---

## 5. Summary — Key Takeaways

- Claude is a capable assistant but needs well-structured context to perform at its best. Generic prompts produce generic output.
- Cowork is the automation layer. It is designed for file-heavy, multi-step tasks where you describe the job and walk away.
- The folder structure (`ABOUT ME / OUTPUTS / TEMPLATES`) and three context files (`about-me.md`, `anti-ai-writing-style.md`, `my-company.md`) are the minimum viable setup for Cowork.
- Configuration has two scopes: **project** (shared with team via git) and **global** (personal, applies to every project). The global `~/.claude/CLAUDE.md` is the single highest-leverage action available — install it first.
- The `.claude/` anatomy reveals that Claude's behaviour is decomposed into six dimensions: what it knows (rules), what it does (commands), how it works (skills), who it becomes (agents), what it remembers (agent-memory), and how it communicates (output-styles).
- **Immediate action required:** Install `config/global-CLAUDE.md` to `~/.claude/CLAUDE.md` and verify it is read in a new session.
