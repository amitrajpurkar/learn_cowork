# Claude Cowork Learning Progress Tracker

**Purpose:** Session-by-session log of modules completed, key learnings, and open questions. Update this file after every study session.
**Audience:** Amit Rajpurkar
**Status:** In Progress
**Last updated:** 2026-05-17
**Related documents:** `../docs/claude-cowork-learning-plan.md`, `../README.md`

---

## How to update this file

After each study session:

1. Find the module you worked on in the table below and update its status
2. Add a dated entry in the Session Log section with: what you covered, what worked, what was unclear, and any open questions
3. Note the next module to tackle at the bottom of the most recent session entry

Status values: `Not started` | `In progress` | `Complete` | `Revisit`

---

## Module status

### Phase 1 — Foundations

| Module | Title | Status | Completed |
|---|---|---|---|
| 1.1 | What Claude Cowork is | Not started | — |
| 1.2 | Sessions, context, and memory | Not started | — |
| 1.3 | File access and workspace model | Not started | — |

### Phase 2 — Configuration

| Module | Title | Status | Completed |
|---|---|---|---|
| 2.1 | Understanding CLAUDE.md file scopes | Not started | — |
| 2.2 | Installing your global CLAUDE.md | Not started | — |
| 2.3 | Auto memory: how Claude learns from corrections | Not started | — |
| 2.4 | Project-level rules with .claude/rules/ | Not started | — |

### Phase 3 — Skills

| Module | Title | Status | Completed |
|---|---|---|---|
| 3.1 | What skills are | Not started | — |
| 3.2 | Document skills: pptx, docx, xlsx, pdf | Not started | — |
| 3.3 | The schedule skill | Not started | — |
| 3.4 | The skill-creator skill | Not started | — |

### Phase 4 — Browser Automation

| Module | Title | Status | Completed |
|---|---|---|---|
| 4.1 | What Claude in Chrome can do | Not started | — |
| 4.2 | Research workflows with browser + file | Not started | — |

### Phase 5 — Advanced

| Module | Title | Status | Completed |
|---|---|---|---|
| 5.1 | Workflow design principles | Not started | — |
| 5.2 | Maintaining and evolving configuration | Not started | — |

---

## Session log

### Session 1 — 2026-04-19

**What was set up:**
- Created the `selflearn_cowork` project structure
- Produced the learning plan (`docs/claude-cowork-learning-plan.md`)
- Produced the global configuration setup guide (`docs/global-configuration-setup-guide.md`)
- Produced the ready-to-install global CLAUDE.md (`config/global-CLAUDE.md`)
- Produced this progress tracker

**Key finding:** The global `~/.claude/CLAUDE.md` is the highest-priority action in this entire plan. Installing it will eliminate the need to re-explain working style, problem-solving approach, and output preferences at the start of every session.

**Status of configuration installation:**
- [ ] `~/.claude/CLAUDE.md` installed from `config/global-CLAUDE.md`
- [ ] Verified in a new session — Claude correctly describes working style without prompting

**Next module to tackle:** Module 2.1 (Understanding CLAUDE.md file scopes) → then immediately proceed to Module 2.2 (Install global CLAUDE.md)

---

<!-- Add new session entries below this line, most recent first -->

### Session 4 — 2026-05-17

**What was covered:**
- Config file maintenance session for `config/ABOUT_ME/about-me.md`
- Reviewed, cleaned up, and updated the file to reflect Dhanesh's transition from IB Grade 12 to UCF Electrical Engineering student
- Fetched UCF's responsible AI use policy and saved it as a standalone reference document

**Changes made to `about-me.md`:**
- Added "As a UCF Engineering Student" section with UCF AI policy link and proper separator formatting
- Fixed typos in the four-D framework line (`Discription` → `Description`, `Deligence` → `Diligence`)
- Standardised bullet style in "Claude's Role" and "Examples of Study Protocols" subsections
- Updated "My goal" section — now reflects UCF enrolment, not IB graduation
- Updated "Who I am" paragraph — removed IB/Grade 12 references
- Updated "Write notes in my voice" — changed "12th-grade IB student" to "first-year Electrical Engineering student"
- Updated document title and `Last updated` date

**New file created:**
- `config/ABOUT_ME/ucf-ai-policy.md` — full UCF Responsible AI Use policy saved as a clean, structured markdown reference document (sourced from https://aiforall.ucf.edu/about/responsible-ai-use-at-ucf/)

**Next action:** Amit will return to this file after gathering additional information to add. No module work was covered this session — resume at Module 2.1 (Understanding CLAUDE.md file scopes) in the next available session.

### Session 3 — 2026-05-09

**What was covered:**
- Studied Anthropic's AI Fluency Framework and Foundations course (Skilljar) — five source PDFs from `skilljar/`
- Read and incorporated personal study notes from `studynotes/ai-fluency-notes.md`
- Produced a 13-page shareable presentation PDF: `docs/understanding-ai-fluency.pdf`

**Course content covered:**
- AI Fluency definition: effective, efficient, ethical, safe use of AI
- The 4Ds framework: Delegation, Description, Discernment, Diligence — each with three sub-dimensions (product / process / performance)
- Three interaction modes: Automation, Augmentation, Agency
- The Description–Discernment loop: the iterative cycle between communicating and evaluating
- Machine properties: Next Token Prediction, Knowledge, Working Memory, Steerability — how each creates both capability and limitation
- Property interactions: how failure modes arise from two properties meeting (e.g. hallucination = token prediction + knowledge gap)
- Key terminology: LLMs, pre-training, fine-tuning, context window, hallucination, RAG, prompt engineering, few-shot learning, etc.

**Key personal takeaways noted (from study notes):**
- Delegation: domain expertise is the non-negotiable foundation
- Description: context + examples + conversation; not just prompts
- Discernment: do not blindly accept AI output — the responsibility to verify is yours
- Diligence: disclose AI's role; take ownership of AI-assisted outputs
- The loop is multi-cycle — iterate until standard is met, not until the AI declares done

**Deliverable produced:**
- `docs/understanding-ai-fluency.pdf` — 13-page presentation PDF with cover, 4Ds deep-dives, loop section, machine properties, terminology glossary, and practical takeaways. Designed with soothing pastel navy/periwinkle colour theme for ease of reading.

**Next module to tackle:** Return to Module 2.1 (Understanding CLAUDE.md file scopes) → Module 2.2 (Install global CLAUDE.md). Installation steps remain fully documented in `studynotes/preliminary_information.md` Section 4.

### Session 2 — 2026-05-08

**What was covered:**
- Read and synthesised three onboarding infographics from the new `infographics/` folder: `claude_intro.JPG`, `cowork_intro.JPG`, `claude_config_01.JPG`
- Produced `studynotes/preliminary_information.md` covering: Claude fundamentals, the 7-step Cowork setup framework, the full anatomy of the `.claude/` directory (project vs global scope), and the outstanding work to install the global CLAUDE.md
- Noted the confirmed finding from Session 1: Cowork desktop does **not** read `~/.claude/CLAUDE.md` the same way Claude Code CLI does

**Key findings from infographics:**
- The Cowork folder structure (`ABOUT ME / OUTPUTS / TEMPLATES`) and three context files are the minimum viable setup for productive Cowork use
- The `.claude/` anatomy infographic (2026 edition) clarifies that configuration decomposes into six behavioural dimensions: rules, commands, skills, agents, agent-memory, output-styles
- `agent-memory/` at global scope is new in 2026 and survives across projects — relevant to long-term personalisation

**Status of configuration installation:**
- [ ] `~/.claude/CLAUDE.md` installed from `config/global-CLAUDE.md` — **still pending**
- [ ] Verified in a new session — Claude correctly describes working style without prompting — **still pending**

**Next module to tackle:** Module 2.1 (Understanding CLAUDE.md file scopes) and Module 2.2 (Install global CLAUDE.md) — the installation steps are fully documented in `studynotes/preliminary_information.md` Section 4; execution is the remaining action.
