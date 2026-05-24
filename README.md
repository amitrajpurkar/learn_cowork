# Claude Cowork Self-Learning Project

**Purpose:** A structured learning project to systematically understand and master Claude Cowork — covering how sessions work, how to configure Claude globally to understand your personality and working style, and how to build productive workflows.
**Audience:** Amit Rajpurkar (personal working project)
**Status:** In Progress
**Last updated:** 2026-04-19
**Related documents:** `docs/claude-cowork-learning-plan.md`, `docs/global-configuration-setup-guide.md`, `docs/usage-guide.md`, `tracking/learning-progress-tracker.md`

---

## What this project is

This project tracks the journey from basic Claude Cowork usage toward a fully configured, personalized Cowork environment. It covers two parallel tracks:

1. **Learning track** — Understanding what Cowork can do, how it works, and how to use it effectively through structured modules
2. **Configuration track** — Setting up the machine so Claude understands Amit's personality, working style, problem-solving approach, and output preferences across every session

The learning resources include the [Claude 101 course on Skilljar](https://anthropic.skilljar.com/claude-101) and the [official Claude Code / Cowork documentation](https://docs.claude.com).

---

## How to navigate this project

| File | Purpose |
|---|---|
| `docs/claude-cowork-learning-plan.md` | Phased learning plan with objectives, resources, and exercises per module |
| `docs/global-configuration-setup-guide.md` | Step-by-step guide to setting up `~/.claude/CLAUDE.md` and related config files on this machine |
| `docs/usage-guide.md` | How to use and maintain this project going forward |
| `tracking/learning-progress-tracker.md` | Module-by-module progress log — update after each study session |
| `config/global-CLAUDE.md` | The ready-to-install global `CLAUDE.md` file capturing Amit's full configuration |

---

## Quick start — setting up global configuration

The highest-value action in this project is installing the global `CLAUDE.md` file. This makes every future Cowork session aware of Amit's working style, preferences, and problem-solving approach without having to re-explain them.

See `docs/global-configuration-setup-guide.md` for the complete setup steps.

---

## Project structure

```
selflearn_cowork/
├── README.md                              ← this file
├── config/
│   └── global-CLAUDE.md                  ← ready-to-install global configuration
├── docs/
│   ├── claude-cowork-learning-plan.md     ← phased learning plan
│   ├── global-configuration-setup-guide.md ← machine setup guide
│   └── usage-guide.md                    ← how to use this project
└── tracking/
    └── learning-progress-tracker.md      ← session-by-session progress log
```


## about Claude's config file
to construct a desired config file for specific persona, you need to develop following files under ABOUT_ME folder:
 - about-me.md
 - output-preference.md
 - my-work-style.md
 - any special instructions that you would like AI to use when working on specific tasks
 - as Claude to read these input files and generate a single CLAUDE.md file for that persona.


Location for storing these files:
~/.claude/CLAUDE.md                          ← global default (Claude Code only)

workspace/claude_workspace/ABOUT_ME/
    student-CLAUDE.md                        ← Engineering students persona
    swe-CLAUDE.md                            ← Software engineers persona
    Amit-CLAUDE.md                           ← (upcoming) personal/non-SWE persona

  [in each project folder]/
    CLAUDE.md                                ← ADD one line (1st line as): @path/to/relevant-persona.md

  + project-specific instructions below


  ### further notes
  a very good reference guide for CoWork = https://github.com/SatyaKomatineni/articles-repo/blob/master/ai/cowork/claude-cowork-learning-intro.md
  few links from this reference:
   - https://www.youtube.com/watch?v=JdQ_FHgP5ms (Cowork Tutorial)
   - https://www.youtube.com/watch?v=C9gKWTzRukM (tutorial 2)
   - https://www.youtube.com/watch?v=xEoVCx9CmxQ (tutorial 3)
   - https://www.youtube.com/watch?v=1oYDEa5Edho (tutorial 4)
   - https://www.youtube.com/watch?v=SNo_recKZyY (another one)
   - https://ccforpms.com/cowork (12-lesson course)


Another technique for building CLAUDE.md
Use this structure instead:
 - who am i
 - my working style
 - my voice
 - my rules, constraints
 - my output formatting style

For each person, you will typically see a need for a main-persona and a general-purpose-persona as well
Hence Dhanesh will need Electrical-Engineering-Student-persona as main-persona and General-Purpose-Student-persona as general-purpose-persona
Yuvan will need High-School-Student-persona as main-persona and General-Purpose-Student-persona as general-purpose-persona
At work, we need to see one personal each for Analyst role, Project Manager/ coordinator, Quality/Test Lead, and Software Engineer roles.