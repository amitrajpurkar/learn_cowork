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
