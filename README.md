# interfaces that feel

> Most AI-generated UIs are technically correct and emotionally empty. This skill fixes that.

A Claude Code skill built on one principle: start with the felt state of the person — not the task. Use the physical world as vocabulary to discover or articulate that feeling. Then bring it into the digital.

Works across Claude Code, Codex CLI, Cursor, and any agent that supports the SKILL.md standard.

## Install

```bash
npx skills add mariespreitzer/interfaces-that-feel
```

---

## In practice

Four comparisons — the same interaction with and without intentional coupling decisions.

| | |
|---|---|
| ![Witnessed vs Default](assets/witnessed.gif) | ![Decisive vs Default](assets/decisive.gif) |
| **Witnessed** — message travels to its destination vs. silent disappear | **Decisive** — fires on press vs. fires on release |
| ![Grounded vs Default](assets/grounded.gif) | ![Punctuated vs Default](assets/punctuated.gif) |
| **Grounded** — compress at commit, weighted exit vs. instant fade | **Punctuated** — attack then decay vs. single flat slide |

---

## The practice

This practice works inside-out. Most interfaces are built outside-in: design the component, specify its attributes, ship it, observe how it feels in use. Feel is a byproduct — if it's considered at all.

Inside-out inverts this. Name the felt quality first — before you know what it looks like, before you know what the interaction is. Work backwards from the named quality to the material decisions.

Every interaction attribute — timing, easing, spring resistance, scroll momentum, haptic pattern — shapes experience. These are aesthetic decisions with experiential consequences. The iOS spring curve is not a neutral choice. A 200ms response is not a neutral choice. Own these decisions. Specify them from felt intent, not from what the framework ships by default.

Before designing any interaction, name who is actually there. Not the action they are taking. The emotional truth underneath it.

| The task frame | The felt frame |
|---|---|
| User is saving a file | Someone who just finished three weeks of work |
| User is in onboarding | Someone who decided to try something new and doesn't know yet if it was the right choice |
| User sees an error | Someone whose momentum was just broken |
| User completes a streak | Someone who needed a win today and just got one |
| User misses a streak | Someone already being hard on themselves |

The interface designed for the task is functional. The interface designed for the feeling is felt.

### The physical world as vocabulary

Once you have the feeling, ask where it already exists in the physical world. The behavioral properties of those moments are your raw material — not as metaphor, but as a material decision.

**You want completion to allow rest:** where does that already live? Putting down a heavy bag. Pushing a plate slightly away after a meal. The weight releases, nothing immediately demands the next action. That goes into your post-completion state — no prompt for what's next, animation that settles.

**You want a destructive action to have real weight:** a door closing in an old building. A deadbolt turning. The resistance before a point of no return. Animation that slows at the threshold. Copy that names the consequence. A moment where the user has to mean it.

The full vocabulary (16 entries) is in the SKILL.md.

### Heartbreak as a design brief

The sharpest test: design for an emotional state most software ignores entirely.

**"Your streak continues" — for someone who is numb.** The default "Keep it up!" lands wrong. Instead: "You kept going. 7 days." No emoji. Option to pause the streak without losing it. *Celebration is context-dependent. The system doesn't know what it cost.*

**An empty shared folder after a breakup.** The folder isn't empty — it was cleared. "Folder cleared" with a soft timestamp is more honest than "Add files to get started." Or nothing at all. Some silences should be respected. *Empty states are not always absences. Some are endings.*

If an interface only works for someone who is fine, it was not designed for people — it was designed for an ideal user who does not exist.

---

## The feel framework

**Does it have a voice?** Read the copy out loud. Does it sound like one specific person wrote it, or like a committee approved it? Voice is specificity — written for this screen, this user, this action.

**Is the emotion earned?** Confetti on a routine save is not earned. A warm message on completing a 7-day streak is. Every emotional moment must be proportional to what the user did.

**Does it know when to step back?** The product that tries to feel at every moment is exhausting. Default to restraint. Apply delight only when a moment genuinely earns it — if you're unsure, it doesn't.

> Restraint is the skill.

---

## Product references

Each reference teaches one principle.

**Figma — personality is discovered, not announced.** The mini games live behind keyboard shortcuts. No badge, no "Did you know?" FigJam highfives happen because *you* waved first. The product meets the gesture and steps back. If the product has to tell you it's delightful, it's not.

**How We Feel — no preferred emotional state.** Logging grief gets the same interface as logging joy. Nothing is calibrated to steer you toward a better feeling. Most wellness apps fail this test completely.

**Headspace — pacing as care.** Moving at the speed of attention is the point, not a compromise. Most apps optimize for time-in-app. Headspace optimizes for leaving the app feeling different than when you arrived.

**Gentler Streak — designing for human inconsistency.** Rest is part of the streak. The product's model of the user includes being tired, sick, and overwhelmed. It redesigned the core mechanic around who actually uses fitness apps.

**Amie — time is social.** People are a first-class object. A meeting isn't just a block of time — it's with someone. Most calendars treat time as a grid. Amie treats it as the medium through which you relate to people.

**Arc — the tool becomes yours through use.** Spaces, boosts, custom themes. Arc accumulates into a personal environment. The longer you use it, the more it feels like yours.

---

## Quick rules

**Motion:** never from `scale(0)` — start at `scale(0.95), opacity: 0`. Never `ease-in` on entering elements. Slow in, fast out. If something happens hundreds of times a day, don't animate it.

**Copy:** write to one person. Errors are support, not blame. Empty states are invitations. Loading messages name what's loading.

**Anti-patterns:** confetti on routine saves, "Herding pixels", quirky 404s on otherwise cold products, `transition: all`, animations that animate everything.

The full rules, easing values, accessibility requirements, and review checklist are in the SKILL.md.

---

Built by [Marie Spreitzer](https://github.com/mariespreitzer) — Interaction Designer.
