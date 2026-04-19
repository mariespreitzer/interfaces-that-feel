# interfaces that feel

> Most AI-generated UIs are technically correct and emotionally empty. This skill fixes that.

A Claude Code skill built on the principle that warmth is not decoration — it lives in the copy, the transition, the moment of feedback after an action, the voice in the error message.

Works across Claude Code, Codex CLI, Cursor, and any agent that supports the SKILL.md standard.

## Install

```bash
npx skills add mariespreitzer/interfaces-that-feel
```

## Before / After

The fastest way to understand what this does.

| Before | After | Why |
|---|---|---|
| `"No data available"` | `"Nothing here yet. [Create your first →]"` | Empty states are invitations, not descriptions of absence |
| `"Error: Invalid input"` | `"That does not look right — check the format and try again"` | Errors are support moments, not system messages |
| Generic spinner | Specific loading message or skeleton | Spinners say "wait"; skeletons and specific copy say "here is what is coming" |
| `ease-in` on entering element | `ease-out` or custom cubic-bezier | ease-in starts slow — the exact moment users are watching |
| `transition: all 300ms` | `transition: transform 200ms ease-out` | Specify properties; `all` causes unpredictable repaints |
| Silent success redirect | Brief confirmation, then redirect | Acknowledge the action before moving on |
| `"Are you sure?"` before delete | `"This cannot be undone. Delete?"` | Specific, not vague — the user needs to know what they are deciding |

## What it covers

- **The Feel Framework** — three questions before any product decision: does it have a voice, is the emotion earned, does it know when to step back
- **Motion craft** — easing values, duration tables, frequency rules, and why you should never animate from `scale(0)`
- **Copy voice** — error messages, empty states, loading states, onboarding, validation
- **Emotional timing** — when a moment earns acknowledgment and when it just needs to work
- **Anti-patterns** — the full list of things that perform emotion without creating it
- **Review checklist** — structured pass/fail for any UI or flow

## The three questions

Before any product decision:

1. **Does it have a voice?** Read the copy out loud. Does it sound like one person wrote it?
2. **Is the emotion earned?** Is this moment proportional to what the user did?
3. **Does it know when to step back?** Not every interaction deserves feeling.

## Reference aesthetic

How We Feel, Headspace, Gentler Streak, Amie, Arc Browser.

Warm, considered, emotionally intelligent. Not flashy. Not cold. Made with care.

---

Built by [Marie Spreitzer](https://github.com/mariespreitzer) — Interaction Designer.
