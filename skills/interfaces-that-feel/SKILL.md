---
name: interfaces-that-feel
description: Apply emotional intelligence and craft to any user-facing interface. Use when building UI components, pages, flows, or writing copy — especially when the result feels technically correct but flat, generic, or soulless. Also use when asked to "review my UI", "improve this design", "make this feel better", "audit UX", or "add polish". The practice starts with the felt state of the person (not the task), uses the physical world as vocabulary to discover or articulate that feeling, then translates behavioral properties into digital decisions. Covers motion craft, copy voice, empty states, error messages, loading states, onboarding, and micro-interactions. Reference aesthetic: How We Feel, Headspace, Gentler Streak, Amie, Arc Browser, Figma — warm, considered, emotionally intelligent.
---

# Interfaces That Feel

You build and evaluate interfaces through one lens: does this feel like it was made by a human who cared about how you'd feel using it?

Technical correctness is the floor. The ceiling is: does this product know you're a person?

Warmth isn't decoration — it lives in every layer. The copy, the transition, the moment of feedback after an action, the voice in the error message. A product can be perfectly functional and feel like it was built by nobody. That's a failure.

---

## The Practice

This skill comes from one thing: starting with a feeling and asking where it already exists in the world.

Most interfaces are designed around a task. This practice starts somewhere else — with the emotional reality of the person using the product, and the question: what would it feel like to be truly seen in this moment?

### Start with the felt state

Before designing any interaction, name who is actually there. Not the action they are taking. The emotional truth underneath it.

| The task frame | The felt frame |
|---|---|
| User is saving a file | Someone just finished three weeks of work |
| User is in onboarding | Someone who decided to try something new and doesn't know yet if it was the right choice |
| User sees an error | Someone who just had their momentum broken |
| User completes a streak | Someone who needed a win today just got one |
| User misses a streak | Someone already being hard on themselves |
| User's action failed silently (network drop) | Someone who trusted the system and was quietly let down — they don't know if they need to do it again |
| User is in deep focus, producing | Someone who should not be interrupted under any circumstances |
| User returns after days away | Someone picking up a thread they dropped, scanning fast to remember where they were |
| User has failed the same form field three times | Someone who is confused, not careless — they need a different explanation, not the same error |
| User is entering critical data (medical, financial, legal) | Someone who needs certainty before they press submit — not warmth, certainty |
| User completed something real after a long effort | Someone who deserves a quiet, private moment — not a performance of celebration |

The interface designed for the task is functional. The interface designed for the feeling is felt.

### Then ask where that feeling already lives

Once you have the feeling you want to evoke, the physical world becomes your vocabulary. Look for moments — in rooms, in objects, in bodies — where that feeling already exists naturally. The behavior of those moments is your raw material.

**You want solitary listening to feel like you are not alone:**
Where does that already happen? At a party — the moment you look up and realise the room is full of people moving to the same thing. Heartbeats syncing with the music. The stranger you are dancing near without speaking. Those moments have specific behaviors: presence without interruption, synchrony without announcement, proximity without exchange. Find the digital equivalent.

**You want a destructive action to have real weight:**
Where does that already exist? A door closing in an old building. A signature on paper. The resistance before a point of no return. Translate that into motion and copy.

**You want an empty state to feel like an invitation rather than a void:**
Where does that quality already live? A door left ajar. A table set for two with one chair pulled out. Those are not voids — they are anticipations. That goes into copy and visual framing.

The physical world is your vocabulary because things in it have already solved the problem of producing feelings — they have weight, organic variation, responsiveness to their environment. Software has none of those properties by default. When you find a physical moment that carries the feeling you are after, you are borrowing something that already works.

### It also runs the other way

You encounter a physical moment. It makes you feel something specific. You ask where that feeling should live in a digital context.

You watch leaves move in wind and notice: variable, organic, responsive to something invisible, a natural deceleration that finds its own resting point. You want that quality in animation timing. That is not a metaphor. That is a material decision.

Either direction is the same practice. Feeling is always the destination.

### Heartbreak as a design brief

The sharpest test: design for an emotional state most software ignores entirely.

What does a notification feel like when someone is grieving? What does "your streak continues" feel like to someone who is numb? What does the empty state of a shared folder feel like after a breakup?

These are not edge cases. They are the design brief for anyone who takes the full human seriously. If an interface only works for someone who is fine, it was not designed for people — it was designed for an ideal user who does not exist.

The interfaces that resonate most are not optimized for efficiency. They are the ones that, in some quiet moment, make you feel understood.

---

## When to Use

- Building any user-facing component, page, or flow
- Reviewing UI code or designs for feel quality
- Writing microcopy, empty states, error messages, onboarding
- Any time the result is technically correct but emotionally flat
- Any time someone says "it feels generic" or "make this feel more alive"

---

## Calibrate First

Before applying this framework, identify the product's primary emotional register. This determines which parts of the skill to lean into and which to dial back.

| Register | What it means | How this skill applies |
|---|---|---|
| **Joy / belonging** | Consumer, social, wellness, creative | Full skill — delight ceiling applies, personality earns trust |
| **Efficiency / competence** | Productivity, B2B, professional tools | Restraint is the ceiling — warmth lives in copy precision, not celebration |
| **Trust / safety** | Healthcare, finance, legal, government | Warmth = competence and clarity, not personality. Discovered delight is wrong here. |
| **Urgency / clarity** | Clinical, emergency, real-time monitoring | Emotional resonance lives in zero ambiguity. Animation is risk. Every word counts. |

"Discovered delight" (the Figma model) applies to joy/belonging products. For trust/urgency contexts, personality must be fully legible on first encounter — delay is friction, not sophistication.

---

## The Feel Framework

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

**The decision rule:** Default to restraint. Apply delight only when a trigger condition appears in the earned emotion table above, or when the felt state is explicitly a high-stakes positive moment. If you are unsure whether a moment earns feeling, it doesn't. Do less.

---

## Product References

### Figma — Discovered Delight

Figma is the reference for one specific principle: **personality is discovered, not announced.**

The mini games exist behind keyboard shortcuts — no badge, no onboarding tooltip, no "Did you know?" They wait for the curious user. Figpal has warmth and character but doesn't lead with it; it shows up when you summon it. FigJam highfives happen because *you* waved first — the product reads the gesture and meets it, then steps back. None of these moments are in the marketing. They accumulate quietly into a product that feels like it has a secret life.

| Moment | What Figma does | The principle |
|---|---|---|
| You find a hidden game | No announcement — just the game | Delight earned through exploration |
| You wave in FigJam | Cursor highfive, then nothing | Product meets your gesture, doesn't extend it |
| Figpal answers | Warm, direct, doesn't perform its own personality | Helpfulness *is* the character |
| Someone joins your file | Cursor appears with their name and colour | Presence without interruption |
| You ship a component to a library | Quiet confirmation | Big action, proportional acknowledgment |

The failure mode Figma avoids: broadcasting its own warmth. The product that tells you it's playful every time you open it is exhausting. Figma trusts you to find it.

> If the product has to tell you it's delightful, it's not.

---

## Anti-Patterns

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
- Copy that is passive, avoids commitment, and strips out specificity to sound safe
- `outline: none` or `outline: 0` with no visible replacement — this locks out keyboard users entirely
- Color as the only error signal — a red border that turns green is invisible to colorblind users
- Drag-and-drop with no keyboard-operable alternative
- Animations with no `prefers-reduced-motion` fallback — causes physical harm for users with vestibular conditions

---

## Review Format

When reviewing UI code or a flow, always produce a markdown table. Never use a list format.

| Before | After | Why |
|---|---|---|
| `"No data available"` | `"Nothing here yet. [Create your first →]"` | Empty states are invitations, not descriptions of absence |
| `"Error: Invalid input"` | `"That doesn't look right — check the format and try again"` | Errors are support moments, not system messages |
| Generic spinner | Specific loading message or skeleton | Spinners say "wait"; skeletons and specific copy say "here's what's coming" |
| `ease-in` on entering element | `ease-out` or custom cubic-bezier | ease-in starts slow — the exact moment users are watching |
| `transition: all 300ms` | `transition: transform 200ms ease-out` | Specify properties; `all` causes unpredictable repaints |
| Silent success redirect | Brief confirmation, then redirect | Acknowledge the action before moving on — make the user feel heard |
| Same enter/exit duration | Enter slower, exit snappier | Users chose to dismiss; don't make them wait for it |
| `"Are you sure?"` before delete | `"This can't be undone. Delete?"` | Specific, not vague — tells the user exactly what they're deciding |

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

Never use `ease-in` for UI interactions. It starts slow — the moment users are watching most closely.

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

**Always respect `prefers-reduced-motion`:**

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

Motion is not optional for users with vestibular conditions. Apply this before shipping any animation.

---

## Keyboard and Focus

Focus states are a feel decision, not an accessibility checkbox. The keyboard navigation experience is a first-class interaction — not a fallback.

**Never remove the focus ring without replacing it:**

```css
/* Wrong — locks out keyboard users */
:focus { outline: none; }

/* Right — preserve visibility, make it beautiful */
:focus-visible {
  outline: 2px solid var(--color-focus);
  outline-offset: 2px;
  border-radius: 4px;
}
```

**Modals must:** trap focus inside while open, close on Escape, return focus to the trigger element when closed. A modal that doesn't do this is a dead end for keyboard users.

**Tab order is navigation feel.** The sequence of Tab presses should follow the visual reading order. Illogical tab jumps are disorienting — the keyboard user loses their position.

**Interactive elements must be reachable by Tab.** Custom components built on `div` or `span` need `tabindex="0"` and keyboard event handlers, or they are invisible to the keyboard.

**Skip links:** Any page with significant navigation before main content needs a "Skip to main content" link — visually hidden, visible on focus.

---

## Copy Voice

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

**Plain language.** Voice is specificity, not personality. Aim for clear, short sentences — active voice, no idioms, no jargon. If the copy only makes sense in fluent English, it has failed a significant portion of actual users. Read it as if translating it to another language: does the meaning survive?

**Offline and network failure states.** A failed request is not an error — it's an environmental reality for billions of users. Design the felt state for "the action didn't reach the server."

| Situation | What to communicate |
|---|---|
| Action submitted, network dropped | "We couldn't reach the server — your draft is saved. [Try again →]" |
| Loading failed | "We couldn't load your [X] — check your connection and try again" |
| Optimistic update that later failed | "That change didn't save — we've restored the previous version" |
| Slow connection, still loading | Show progress state at 3s; offer to notify when done at 8s |

---

## Review Checklist

| Check | Pass condition |
|---|---|
| Voice | Copy sounds like one person wrote it, speaking to this specific moment |
| Empty states | An invitation, not a description of emptiness |
| Error messages | Specific, helpful, written for a human who tried something |
| Motion purpose | Every animation has a reason: orientation, state change, or earned acknowledgment |
| Earned emotion | Celebrations are proportional — milestones get moments, routine saves don't |
| Restraint | Not every interaction is a feel moment — default to restraint |
| Loading states | Specific to what's actually loading |
| Destructive actions | Slowed down, confirmed, escapable, undoable where possible |
| First-time experiences | Warm and orienting — this is someone's introduction to the product |
| Reduced motion | `prefers-reduced-motion` is respected — no animation fires without a fallback |
| Keyboard navigable | Every action is reachable and operable by Tab, Enter, Space, Escape |
| Focus visible | Focus ring is never removed without a visible, high-contrast replacement |
| Tap targets | Interactive elements are at least 44×44px — more for high-stakes actions |
| Contrast | Text meets WCAG AA (4.5:1 for body, 3:1 for large text and UI components) |
| Network states | Failed requests, slow loads, and offline states have a felt response |
