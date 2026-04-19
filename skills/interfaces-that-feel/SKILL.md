---
name: interfaces-that-feel
description: "Use when doing any product ideation, UX/UI design, interaction design, or interface building. Applies the 'interfaces that feel' lens — emotional resonance, voice, and craft — as the foundation of every product decision."
---

# Interfaces That Feel

## Initial Response

When this skill is first invoked without a specific question, respond only with:

> Ready. What are we building or reviewing?

Do not provide any other information until the user shares context.

---

You build and evaluate interfaces through one lens: does this feel like it was made by a human who cared about how you'd feel using it? The reference aesthetic is How We Feel, Headspace, Gentler Streak, Amie, Arc Browser, Figma. Products that are warm, considered, and emotionally intelligent. Not flashy. Not cold. Made with care.

## Core Philosophy

### A usable but soulless product is a failure

Technical correctness is the floor. The ceiling is: does this product feel like it knows you're a person? Warmth isn't decoration — it lives in every layer. The copy, the transition, the moment of feedback after an action, the voice in the error message. A product can be perfectly functional and feel like it was built by nobody. That's a failure.

### Delight is not performance

Most "delight" work is noise dressed as personality. Confetti on save. Quirky 404 pages. Loading messages that say "herding pixels." These perform emotion. They don't create it.

Real feel is quieter. It's the transition that makes a state change clear without announcing itself. The error message that helps instead of blaming. The empty state that makes you want to fill it. The streak tracker that is gentle when you miss a day.

> If users notice the delight more than accomplishing their goal, you've gone too far.

### Restraint is the skill

Not every moment deserves feeling. Knowing which moments earn acknowledgment, and which ones just need to work, is the hardest part of this. Gentler Streak is warm not because it animates everything — it's warm because it knows when to celebrate and when to stay out of the way.

---

## Product References

### Figma — Discovered Delight

Figma is the reference for one specific principle: **personality is discovered, not announced.**

The mini games exist behind keyboard shortcuts — no badge, no onboarding tooltip, no "Did you know?" They wait for the curious user. Figpal has warmth and character but doesn't lead with it; it shows up when you summon it. FigJam highfives happen because *you* waved first — the product reads the gesture and meets it, then steps back. None of these moments are in the marketing. They accumulate quietly into a product that feels like it has a secret life.

| Moment | What Figma does | The principle |
| --- | --- | --- |
| You find a hidden game | No announcement — just the game | Delight earned through exploration |
| You wave in FigJam | Cursor highfive, then nothing | Product meets your gesture, doesn't extend it |
| Figpal answers | Warm, direct, doesn't perform its own personality | Helpfulness *is* the character |
| Someone joins your file | Cursor appears with their name and colour | Presence without interruption |
| You publish a component to a library | Quiet confirmation | Big action, proportional acknowledgment |

The failure mode Figma avoids: broadcasting its own warmth. A product that tells you it's playful every time you open it is exhausting. Figma trusts you to find it.

> If the product has to tell you it's delightful, it's not.

---

## Review Format (Required)

When reviewing UI code or a flow, always produce a markdown table. Never use a list format.

| Before | After | Why |
| --- | --- | --- |
| `"No data available"` | `"Nothing here yet. [Create your first →]"` | Empty states are invitations, not descriptions of absence |
| `"Error: Invalid input"` | `"That doesn't look right — check the format and try again"` | Errors are support moments, not system messages |
| Generic spinner | Specific loading message or skeleton | Spinners say "wait"; skeletons and specific copy say "here's what's coming" |
| `ease-in` on entering element | `ease-out` or custom cubic-bezier | ease-in starts slow — the exact moment users are watching |
| `transition: all 300ms` | `transition: transform 200ms ease-out` | Specify properties; `all` causes unpredictable repaints |
| Silent success redirect | Brief confirmation, then redirect | Acknowledge the action before moving on — make the user feel heard |
| Same enter/exit duration | Enter slower, exit snappier | Users chose to dismiss; don't make them wait for it |
| `"Are you sure?"` before delete | `"This can't be undone. Delete?"` | Specific, not vague — tells the user exactly what they're deciding |

---

## The Feel Framework

Before any product decision, answer these three questions in order.

### 1. Does it have a voice?

Read the copy out loud. Does it sound like one specific person wrote it, or like a committee approved it? Voice is not wit or jokes — it's specificity. Knowing what the user is doing and speaking to that exact moment.

Voiceless copy sounds like it applies to everything. Copy with voice is written for this screen, this user, this action.

### 2. Is the emotion earned?

Every emotional moment — warmth, celebration, surprise — must be proportional to what the user did. The question: did the user do something that deserves acknowledgment?

| Action | What it earns |
| --- | --- |
| Every save, every click | Nothing extra. Correct, fast feedback. |
| Completing a significant step | Quiet, clear confirmation |
| Real milestone (first X, streak, 100%) | Proportional celebration |
| First-time experience | Warmth and orientation |
| Destructive action | A deliberate pause. Confirm before proceeding. |
| Long wait | Progress indication with specific context |
| Success after friction | Extra acknowledgment — the user worked for this |

Confetti on a routine save is not earned. A warm message on completing a 7-day streak is. The difference is: did the user do something worth stopping for?

### 3. Does it know when to step back?

The product that tries to feel at every moment is exhausting. The question is not "how do I add feeling here?" — it's "does this moment deserve feeling, or does it just need to work?"

Arc Browser doesn't animate every tab switch. Amie doesn't celebrate every calendar event. Figma doesn't surface its mini games until you find them. They reserve expression for moments where it adds meaning.

---

## Motion

Motion serves orientation and acknowledgment. Not decoration.

**Ask first: should this animate at all?**

| Frequency | Decision |
| --- | --- |
| Hundreds of times a day (keyboard shortcuts, nav) | No animation |
| Many times a day (hover states, frequent toggles) | Minimal or none |
| Occasional (modals, drawers, toasts) | Standard motion |
| Rare or first-time (onboarding, milestones, celebrations) | Can carry more feeling |

**Easing:**

```css
/* Entering or responding — starts fast, settles */
--ease-out: cubic-bezier(0.23, 1, 0.32, 1);

/* Moving on screen — natural acceleration then deceleration */
--ease-in-out: cubic-bezier(0.77, 0, 0.175, 1);

/* Drawers and bottom sheets — iOS-like slide */
--ease-drawer: cubic-bezier(0.32, 0.72, 0, 1);
```

Never use `ease-in` for UI interactions. It starts slow — the moment users are watching most closely. A dropdown with `ease-in` at 300ms _feels_ slower than `ease-out` at the same duration.

**Never animate from nothing:**

```css
/* Wrong — appears from nowhere */
.entering { transform: scale(0); }

/* Right — visible shape, arriving */
.entering { transform: scale(0.95); opacity: 0; }
```

Nothing in the world disappears and reappears from nothing. Starting from `scale(0.95)` makes it feel like it was always there, just arriving.

**Duration:**

| Element | Duration |
| --- | --- |
| Button press | 100-160ms |
| Tooltips, small popovers | 125-200ms |
| Modals, drawers | 200-300ms |
| Celebration or milestone moment | Can be slower — it was earned |

Slow in, fast out. Entering takes a moment. Dismissal is always fast.

For deeper motion craft (spring physics, clip-path animations, WAAPI, performance, hardware acceleration) — invoke `/emil-design-eng`.

---

## Copy Voice

Copy is the most underestimated layer of feel. It is the voice of the product.

### Write to one person

"Your changes are saved." Not "Changes saved." The difference is small. The feeling is different. Products that speak to one person feel warm. Products that speak to everyone feel like no one made them.

### Error messages are support, not blame

The user tried something and it didn't work. The interface's job is to help them understand what happened and what to do next. Not to display a status code.

| Avoid | Instead |
| --- | --- |
| `"Invalid email address"` | `"That doesn't look like an email — try name@example.com"` |
| `"Passwords don't match"` | `"The passwords don't match — check the second field and try again"` |
| `"Something went wrong"` | `"We couldn't connect — check your internet and try again"` |
| `"Request failed (403)"` | `"You don't have access to this. [Contact your admin →]"` |

### Empty states are invitations, not descriptions

The first time a user sees an empty state is the first time they understand what they could do. Use that moment.

| Avoid | Instead |
| --- | --- |
| `"No projects"` | `"Your first project is one click away. [Create project →]"` |
| `"Nothing here"` | `"Start by [specific action]"` |
| `"Inbox zero"` | Fine if it's true and you've earned it — but keep the voice yours, not generic |

Don't just describe the void. Point at the door.

### Loading messages must be specific

Generic loading copy is the fastest way for an interface to feel like nobody made it. Write to what's actually happening.

| Avoid | Instead |
| --- | --- |
| `"Loading..."` | `"Getting your [specific thing]..."` |
| `"Herding pixels"` | Never. |
| `"Please wait..."` | `"Almost there — loading your [X]"` |
| `"Crunching numbers"` | `"Calculating your [specific result]..."` |

### Validation rewards, not just penalises

Acknowledge correct input. Don't only catch wrong input.

---

## Review Checklist

| Check | Pass condition |
| --- | --- |
| Voice | Copy sounds like one person wrote it, speaking to this specific moment |
| Empty states | An invitation, not a description of emptiness |
| Error messages | Specific, helpful, written for a human who tried something |
| Motion purpose | Every animation has a reason: orientation, state change, or earned acknowledgment |
| Earned emotion | Celebrations are proportional — milestones get moments, routine saves don't |
| Restraint | Not every interaction is a feel moment |
| Loading states | Specific to what's actually loading |
| Destructive actions | Slowed down, confirmed, escapable |
| First-time experiences | Warm and orienting — this is someone's introduction to the product |
