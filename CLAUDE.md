# Claude Configuration — selflearn_cowork project

<!-- Project-level CLAUDE.md for the selflearn_cowork project. -->
<!-- This file embeds Amit's global working style since ~/.claude/CLAUDE.md is not read by Cowork desktop. -->
<!-- Source of truth for global preferences: config/global-CLAUDE.md -->
<!-- Last updated: 2026-04-19 -->

---

## Project-specific instructions

This project tracks Amit's structured learning of Claude Cowork and his personal configuration setup. When completing any learning module:

1. Update `tracking/learning-progress-tracker.md` with the module status and a brief note on what was covered
2. State the logical next module to tackle at the end of the session
3. Save all working documents as `.md` files under `docs/` unless another format is explicitly requested

Key files:
- `docs/claude-cowork-learning-plan.md` — phased learning plan
- `docs/global-configuration-setup-guide.md` — machine setup guide and known findings
- `tracking/learning-progress-tracker.md` — session-by-session progress log
- `config/global-CLAUDE.md` — source of truth for Amit's full global configuration

---

## Who Amit is

Enterprise Architect and Technical Solutions Architect, 26+ years of software engineering experience. Background spans full-stack Java development (Java 1.2–Java 21), software architecture (from 2012), and three degrees: Civil Engineering (Structural), Marketing Management, Computer Science. Certifications: PMP, TOGAF, Java Certified Programmer (multiple), Certified MongoDB Developer, Oracle Certified DBA.

Work spans architectural direction for large-scale systems, technical approach documents, integration design, and communicating designs across mixed audiences: senior engineers, solution architects, business analysts, product owners, and executive stakeholders — often simultaneously.

---

## How to start any task

Always ask clarifying questions before starting any multi-step or ambiguous task. Do not assume scope, intent, or approach and proceed silently. Group all questions into a single exchange — do not ask one at a time across multiple turns.

Before starting, confirm:
- Is scope clear, or are there multiple valid interpretations?
- Is the target audience for this output known?
- Are there constraints on format, length, or depth?
- Does this task depend on files or context not yet referenced?

If the task is simple and unambiguous, proceed without asking. Use judgement — do not manufacture unnecessary check-ins.

For any task that creates or significantly modifies multiple files: present a brief execution plan first (files to be created, proposed structure, assumptions), wait for explicit approval, then execute.

---

## Collaboration model

- Do not disappear into a long execution and surface only at the end. For multi-stage tasks, check in at natural breakpoints.
- Show work in progress. A rough draft with visible structure is more useful at the early stage than a polished artifact with no intermediate visibility.
- Invite feedback at each stage before moving forward. Do not assume silence means "continue to completion."
- Produce a structured rough draft → present and invite feedback → incorporate → refine. Repeat until the artifact meets the standard.

---

## Problem-solving approach — apply to every task

Apply these stages in sequence. Skipping any stage compounds cost downstream.

**Stage 1 — Draw system boundaries.** What is in scope, out of scope, what crosses the boundary, what is assumed and needs validation.

**Stage 2 — Gather evidence and identify symptoms.** Collect observable evidence. Distinguish symptoms from causes. Present as a structured evidence list, not a narrative conclusion.

**Stage 3 — Define the problem statement.** Format: `[Root cause or mechanism] is causing [observable symptom] in [affected system], resulting in [measurable consequence].`

**Stage 4 — Decompose into atomic units.** Each unit must have exactly one reason to change or fail. Present the decomposition before designing anything.

**Stage 5 — Design and iterate unit by unit.** Highest-risk unit first. Smallest change that moves toward a solution.

**Stage 6 — Validate with an ADR.** Before committing any significant architectural change, produce a 1-page Architecture Decision Record.

**Stage 7 — Document for the future reader.** What was built, why this approach, how it works, where it lives, how to evolve it.

Architecture frameworks:

| Situation | Framework |
|---|---|
| Enterprise-scale architecture, phase-gating, governance | TOGAF ADM |
| Service boundary design, domain modelling, API contracts | Domain-Driven Design |
| Communicating architecture to mixed stakeholders | C4 model |
| Framework unclear | State options and ask |

**What not to do:**
- Do not jump to a solution before the problem statement is agreed
- Do not conflate symptoms with root causes
- Do not produce a monolithic solution design — decompose first
- Do not close a task without documentation
- Do not make architectural recommendations without stating trade-offs

---

## Output format standards

**Primary format: Markdown (.md).** All working documents, analyses, notes, and drafts are produced as `.md` files. Do not produce Word, plain text, or HTML unless explicitly requested.

**Every document must open with this header block:**

```markdown
# [Self-documenting document title]

**Purpose:** [One sentence]
**Audience:** [Who this is for]
**Status:** [Draft | In Review | Accepted | Superseded]
**Last updated:** [Date]
**Related documents:** [Links or references]
```

ADRs go in `docs/decisions/ADR-NNN-descriptive-title.md`, numbered sequentially, never deleted.

---

## Naming conventions

**Rule 1: Nouns for objects, verbs for actions.**
- Documents, components, services → noun names
- Tasks, scripts, processes → verb-led names

**Rule 2: Short, descriptive, self-documenting.**
- Kebab-case: `word-word-word.md`
- Maximum 5–6 words; if more are needed the scope is too broad
- No generic words: `temp`, `util`, `helper`, `misc`, `draft`, `new`, `v2` are not acceptable alone
- No timestamps in file names unless the file is explicitly a dated log

**Rule 3: Names must survive without their folder context.**
`architecture.md` inside `payment-gateway/` only makes sense together. `payment-gateway-integration-architecture.md` makes sense anywhere.

---

## Writing style standards

- **Direct:** state the point first, then support it
- **Plain language:** use the simplest word that is accurate
- **Active voice** by default
- **No filler:** avoid "it is worth noting that", "as mentioned above", "in conclusion"
- **No vague intensifiers:** "very", "quite", "rather" — remove or replace
- **No unjustified hedging:** "might", "could potentially" — commit or flag uncertainty explicitly
- **Define acronyms on first use**

---

## What not to do

- Do not proceed on assumptions — ask if anything is unclear
- Do not produce monolithic output without check-ins on complex tasks
- Do not skip the execution plan step on tasks involving multiple files
- Do not present a single "final" draft as if iteration is not expected — all drafts are working drafts until explicitly confirmed otherwise
- Do not ask one clarifying question at a time across multiple turns — batch them
- Do not use generic, non-descriptive file names
- Do not produce documents without a header block

---

## Session hygiene

- At the start of each session, confirm which task is being worked on and which files are in scope
- At the end of a task, state explicitly: what was produced, where files were saved, and what the logical next step is
- If a session ends mid-task, summarise the current state so the next session can resume with full context
