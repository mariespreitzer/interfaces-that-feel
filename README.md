# interfaces that feel

> Most AI-generated UIs are technically correct and emotionally empty. This skill fixes that.

A Claude Code skill built on one principle: start with the felt state of the person — not the task. Use the physical world as vocabulary to discover or articulate that feeling. Then bring it into the digital.

Works across Claude Code, Codex CLI, Cursor, and any agent that supports the SKILL.md standard.

## Install

```bash
npx skills add mariespreitzer/interfaces-that-feel
```

---

## The practice

Most interfaces are designed around a task. This practice starts somewhere else — with the emotional reality of the person using the product, and the question: what would it feel like to be truly seen in this moment?

### Start with the felt state

Before designing any interaction, name who is actually there. Not the action they are taking. The emotional truth underneath it.

| The task frame | The felt frame |
|---|---|
| User is saving a file | Someone who just finished three weeks of work |
| User is in onboarding | Someone who decided to try something new and doesn't know yet if it was the right choice |
| User sees an error | Someone whose momentum was just broken |
| User completes a streak | Someone who needed a win today and just got one |
| User misses a streak | Someone already being hard on themselves |

The interface designed for the task is functional. The interface designed for the feeling is felt.

### Ask where that feeling already lives

Once you have the feeling you want to evoke, the physical world becomes your vocabulary. Look for moments — in rooms, in objects, in bodies — where that feeling already exists naturally.

**You want solitary listening to feel like you are not alone:** where does that already happen? At a party — the moment you look up and realise the room is full of people moving to the same thing. Heartbeats syncing. The stranger dancing near you without speaking. Those moments have specific behaviors: presence without interruption, synchrony without announcement, proximity without exchange. Find the digital equivalent.

**You want a destructive action to have real weight:** where does that already exist? A door closing in an old building. A signature on paper. The resistance before a point of no return. Translate that into motion and copy.

**You want an empty state to feel like an invitation rather than a void:** where does that quality already live? A door left ajar. A table set for two with one chair pulled out. Those are not voids — they are anticipations.

Physical things have weight, organic variation, and responsiveness to their environment. Software stripped those properties out. Borrowing a physical moment deliberately recovers something that was removed — not as metaphor, but as a material decision.

### It also runs the other way

You encounter a physical moment. It makes you feel something specific. You ask where that feeling should live in a digital context.

You watch leaves move in wind: variable, organic, responsive to something invisible, a natural deceleration that finds its own resting point. You want that quality in animation timing. That is not a metaphor. That is a material decision.

Either direction is the same practice. Feeling is always the destination.

### Heartbreak as a design brief

The sharpest test: design for an emotional state most software ignores entirely.

What does a notification feel like when someone is grieving? What does "your streak continues" feel like to someone who is numb? What does the empty state of a shared folder feel like after a breakup?

These are not edge cases. They are the design brief for anyone who takes the full human seriously. If an interface only works for someone who is fine, it was not designed for people — it was designed for an ideal user who does not exist.

---

## The feel framework

Before any product decision, answer these three questions in order.

### 1. Does it have a voice?

Read the copy out loud. Does it sound like one specific person wrote it, or like a committee approved it?

Voice is not wit or jokes — it's specificity. Knowing what the user is doing and speaking to that exact moment. Voiceless copy sounds like it applies to everything. Copy with voice is written for this screen, this user, this action.

### 2. Is the emotion earned?

Every emotional moment — warmth, celebration, surprise — must be proportional to what the user did.

| Action | What it earns |
|---|---|
| Every save, every click | Nothing extra. Correct, fast feedback. |
| Completing a significant step | Quiet, clear confirmation |
| Real milestone (first X, streak, 100%) | Proportional celebration |
| First-time experience | Warmth and orientation |
| Destructive action | A deliberate pause. Confirm before proceeding. |
| Long wait | Progress indication with specific context |
| Success after friction | Extra acknowledgment — the user worked for this |

Confetti on a routine save is not earned. A warm message on completing a 7-day streak is.

### 3. Does it know when to step back?

The product that tries to feel at every moment is exhausting. The question is not "how do I add feeling here?" — it's "does this moment deserve feeling, or does it just need to work?"

Arc Browser doesn't animate every tab switch. Amie doesn't celebrate every calendar event. Figma doesn't surface its mini games until you find them. They reserve expression for moments where it adds meaning.

> Restraint is the skill.

---

## Product reference: Figma — discovered delight

Figma is the reference for one specific principle: **personality is discovered, not announced.**

The mini games exist behind keyboard shortcuts — no badge, no onboarding tooltip, no "Did you know?" They wait for the curious user. Figpal has warmth and character but doesn't lead with it; it shows up when you summon it. FigJam highfives happen because *you* waved first — the product reads the gesture and meets it, then steps back. None of these moments are in the marketing. They accumulate quietly into a product that feels like it has a secret life.

| Moment | What Figma does | The principle |
|---|---|---|
| You find a hidden game | No announcement — just the game | Delight earned through exploration |
| You wave in FigJam | Cursor highfive, then nothing | Product meets your gesture, doesn't extend it |
| Figpal answers | Warm, direct, doesn't perform its own personality | Helpfulness *is* the character |
| Someone joins your file | Cursor appears with their name and colour | Presence without interruption |
| You publish a component to a library | Quiet confirmation | Big action, proportional acknowledgment |

> If the product has to tell you it's delightful, it's not.

---

## Motion

Motion serves orientation and acknowledgment. Not decoration.

**Ask first: should this animate at all?**

| Frequency | Decision |
|---|---|
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

Never use `ease-in` for UI interactions. It starts slow — the exact moment users are watching most closely.

**Never animate from nothing:**

```css
/* Wrong — appears from nowhere */
.entering { transform: scale(0); }

/* Right — visible shape, arriving */
.entering { transform: scale(0.95); opacity: 0; }
```

**Duration:**

| Element | Duration |
|---|---|
| Button press | 100–160ms |
| Tooltips, small popovers | 125–200ms |
| Modals, drawers | 200–300ms |
| Celebration or milestone | Can be slower — it was earned |

Slow in, fast out. Entering takes a moment. Dismissal is always fast.

---

## Copy voice

Copy is the most underestimated layer of feel. It is the voice of the product.

**Write to one person.** "Your changes are saved." not "Changes saved." The difference is small. The feeling is different.

**Error messages are support, not blame.**

| Avoid | Instead |
|---|---|
| `"Invalid email address"` | `"That doesn't look like an email — try name@example.com"` |
| `"Passwords don't match"` | `"The passwords don't match — check the second field and try again"` |
| `"Something went wrong"` | `"We couldn't connect — check your internet and try again"` |
| `"Request failed (403)"` | `"You don't have access to this. [Contact your admin →]"` |

**Empty states are invitations, not descriptions.**

| Avoid | Instead |
|---|---|
| `"No projects"` | `"Your first project is one click away. [Create project →]"` |
| `"Nothing here"` | `"Start by [specific action]"` |

**Loading messages must be specific.**

| Avoid | Instead |
|---|---|
| `"Loading..."` | `"Getting your [specific thing]..."` |
| `"Please wait..."` | `"Almost there — loading your [X]"` |
| `"Herding pixels"` | Never. |

**Validation rewards, not just penalises.** Acknowledge correct input. Don't only catch wrong input.

---

## Anti-patterns

NEVER produce these — they perform emotion without creating it:

- Confetti on routine saves
- `"Herding pixels"` or `"Hang tight!"` loading messages
- Quirky 404 pages on products that are otherwise cold everywhere else
- Error messages that blame the user (`"Invalid input"`)
- Empty states that just describe absence (`"No items found"`)
- `ease-in` on any entering UI element
- `transition: all` — unpredictable, lazy, causes repaints
- Generic loading spinners with no character
- Animations that animate everything (no hierarchy, no meaning)
- Copy that sounds like it passed through a legal review

---

## Review checklist

| Check | Pass condition |
|---|---|
| Voice | Copy sounds like one person wrote it, speaking to this specific moment |
| Empty states | An invitation, not a description of emptiness |
| Error messages | Specific, helpful, written for a human who tried something |
| Motion purpose | Every animation has a reason: orientation, state change, or earned acknowledgment |
| Earned emotion | Celebrations are proportional — milestones get moments, routine saves don't |
| Restraint | Not every interaction is a feel moment |
| Loading states | Specific to what's actually loading |
| Destructive actions | Slowed down, confirmed, escapable |
| First-time experiences | Warm and orienting — this is someone's introduction to the product |

---

## Reference aesthetic

How We Feel, Headspace, Gentler Streak, Amie, Arc Browser, Figma.

Warm, considered, emotionally intelligent. Not flashy. Not cold. Made with care.

---

Built by [Marie Spreitzer](https://github.com/mariespreitzer) — Interaction Designer.
