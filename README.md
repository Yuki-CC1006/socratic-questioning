# Socratic Questioning

**Never answers until you confirm the real question.**

A problem-diagnosis skill for Cursor / Claude Code / Codex-style agents. It turns a messy, emotional, or half-formed prompt into one precise question — then stops and waits for your confirmation before any advice.

This is **not** a teaching tutor that forever refuses to answer (code/docs Socratic style). It is a short diagnostic interview: find the question worth answering.

## Install

**Cursor** (personal skill):

```bash
mkdir -p ~/.cursor/skills/socratic-questioning
curl -fsSL https://raw.githubusercontent.com/Yuki-CC1006/socratic-questioning/main/SKILL.md \
  -o ~/.cursor/skills/socratic-questioning/SKILL.md
```

Or clone:

```bash
git clone https://github.com/Yuki-CC1006/socratic-questioning.git ~/.cursor/skills/socratic-questioning
```

**Agent Skills CLI** (if you use `npx skills`):

```bash
npx skills add Yuki-CC1006/socratic-questioning
```

Invoke explicitly, e.g. `/socratic-questioning` or “run Socratic questioning”. Auto-invoke is off (`disable-model-invocation: true`) so it will not interrogate you by accident.

## What it does

1. **Steelman** your statement before probing
2. Classify each claim as **fact / interpretation / value / goal**
3. Ask **one** question at a time (max 6); stop when enough
4. Treat emotion as **signal**, never as evidence
5. End with a fixed YAML brief (`outcome` + reframed question) — no judgment until you say **confirm**

### Outcome types

| `outcome` | Meaning |
|-----------|---------|
| `clarified` | Clearer question found |
| `aporia` | Built on a false premise or missing fact |
| `track-change` | Asked A, actually needed B |
| `already-clear` | Original question was already sharp — do not invent a “better” one |

## Why this exists

Most “Socratic” skills either teach (never answer) or frame product problems (appetite, segments). Everyday confusion mixes facts with feelings and “should”. This skill’s edge is the four-way taxonomy, the `already-clear` exit, and hard session boundaries (stop after one question; no advice before confirm).

## License

MIT
