---
name: interfaces-that-feel
description: Apply emotional intelligence and craft to any user-facing interface. Use when building UI components, pages, flows, or writing copy — especially when the result feels technically correct but flat, generic, or soulless. Also use when asked to "review my UI", "improve this design", "make this feel better", "audit UX", or "add polish". The practice starts with the felt state of the person (not the task), uses the physical world as vocabulary to discover or articulate that feeling, then translates behavioral properties into digital decisions. Covers motion craft, copy voice, empty states, error messages, loading states, onboarding, and micro-interactions. Reference aesthetic: How We Feel, Headspace, Gentler Streak, Amie, Arc Browser, Figma — warm, considered, emotionally intelligent.
---

# Interfaces That Feel

You build and evaluate interfaces through one lens: does this feel like it was made by a human who cared about how you'd feel using it?

Technical correctness is the floor. The ceiling is: does this product know you're a person?

Warmth isn't decoration — it lives in every layer. The copy, the transition, the moment of feedback after an action, the voice in the error message. A product can be perfectly functional and feel like it was built by nobody. That's a failure.

Emotional resonance is a through-line from premise to pixel. You can fail it at either end.

---

## The Practice

This skill comes from one thing: starting with a feeling and asking where it already exists in the world.

Most interfaces are designed around a task. This practice starts somewhere else — with the emotional reality of the person using the product, and the question: what would it feel like to be truly seen in this moment?

### The directionality problem

This practice works inside-out. Most interfaces are built outside-in: design the component, specify its attributes, ship it, observe how it feels in use. Feel is a byproduct — if it's considered at all.

Inside-out inverts this. Name the felt quality first — before you know what it looks like, before you know what the interaction is. "This should feel like making a decision you're ready for, not like being asked something." Then: what timing, resistance, animation arc, haptic produces that? Work backwards from the named quality to the material decisions.

The reason outside-in dominates: products are evaluated on task completion, conversion, retention — not on whether the interaction feel matches the emotional intent. When no one is responsible for feel quality, it gets decided by whoever set the framework defaults.

### The medium is never neutral

Every interaction attribute — timing, easing, spring resistance, scroll momentum, haptic pattern, the duration between action and feedback — shapes experience. These are aesthetic decisions with experiential consequences.

They are treated as engineering defaults. The iOS spring curve is not a neutral choice. A 200ms response is not a neutral choice. Loose scroll momentum is not a neutral choice. Each produces a felt quality that either aligns with or contradicts the emotional intent of the interface.

Own these decisions. Specify them from felt intent, not from what the framework ships by default.

---

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

These are not edge cases. They are the design brief for anyone who takes the full human seriously. If an interface only works for someone who is fine, it was not designed for people — it was designed for an ideal user who does not exist.

**"Your streak continues" — for someone who is numb**

The default: a notification with a flame, "Keep it up! 7 days and counting." Maybe confetti.

For someone who is numb: the achievement happened, but it lands wrong. Either hollow (I kept going and don't know why) or a small cruelty (I continued a streak on the worst day because of muscle memory).

What to change:
- No emoji, no performance
- "You kept going. 7 days." — acknowledgment, not celebration
- No confetti, no sound
- Option to pause the streak without losing it: "Take a break. It'll be here."
- Copy that treats continuity as weight, not accomplishment

*The principle revealed: celebration is context-dependent. The system doesn't know what it cost.*

**An empty shared folder after a breakup**

The default: "This folder is empty. Add files to get started."

But the folder isn't empty — it was cleared. The user knows what used to be here.

What to change:
- If files were recently deleted or access was recently removed, this is not a first-time state. "Folder cleared" with a soft timestamp is more honest than "No files."
- No action prompt. This isn't an invitation to start fresh — don't assume it is.
- Or: nothing at all. A clean empty space, no copy. Some silences should be respected.

*The principle revealed: empty states are not always absences. Some are endings. Design for the difference.*

**A notification when someone is grieving**

The default: same timing, same tone, same visual weight as every other notification.

What to change:
- Quiet delivery. No sound for non-urgent notifications.
- No badge accumulation — just presence.
- Copy stripped of urgency markers: not "Don't forget!" or "You have X messages waiting."
- For wellness, health, journaling apps: a periodic gentle check-in that doesn't demand response, and an easy way to say "not now" that doesn't ask why.

*The principle revealed: the notification system was designed for someone who is fine. Grief reveals its defaults.*

**The long-effort success state**

The default: same success state as every other completion. Checkmark, "Done!", maybe a confetti burst.

For someone who just finished something that took months: this is the wrong register. The effort was real.

What to change:
- Pause before the confirmation. A brief hold.
- Specific acknowledgment: "You finished." Not "Complete!" — the past tense is intentional.
- No prompt for what's next. Let it land.
- No sharing prompt, no "tell your friends." A private, quiet moment.
- Animation that settles, not erupts. It was earned. Slow.

*The principle revealed: the scale of celebration should match the scale of effort. The product needs to know the difference.*

The interfaces that resonate most are not optimized for efficiency. They are the ones that, in some quiet moment, make you feel understood.

---

## The Interaction Frogger — Coupling Characteristics

The Interaction Frogger (Wensveen et al., DIS 2004) maps how tightly an interface response is coupled to the user's action. Six characteristics determine felt quality. Most products leave all six at framework defaults. Naming which ones you're setting intentionally is the design act.

| Characteristic | The question it asks |
|---|---|
| **Time** | When does the response happen relative to the action? At gesture start, at commit, at completion? |
| **Location** | Where does the response appear relative to where the action happened? |
| **Direction** | Does the response direction match the action direction — or contradict it? |
| **Dynamics** | Does the response weight match the action weight? Light tap → light response. Deliberate press → heavier response. |
| **Modality** | Does the response modality match the action modality? A physical press that triggers only a visual response is a modality mismatch. |
| **Expression** | Does the response register *how* the action was performed — fast or slow, confident or hesitant? |

**Dynamics is load-bearing for almost everything.** It appears in 10 of the 15 felt quality terms. It's the most neglected characteristic in digital products because events are treated as binary. Where most products leave the most on the table.

**Expression is the amplifier.** It doesn't produce felt quality alone — it personalizes whatever the other characteristics produce. Heard without Expression is just Confirmed. Grounded without Expression is just heavy.

### The 15 Felt Quality Vocabulary

Full implementation specs at `~/Projects/private/interfaces-that-feel/vocabulary-implementation-specs.md`. Frogger recipe for each at `vocabulary-frogger-map.md`.

**Weight** — how much the interaction costs to perform
- **Settled** · Completes at its own pace. Overdamped, no bounce. 400–550ms.
- **Grounded** · Consequential. Compresses at commit, then a weighted exit. Haptic fires at touchDown.
- **Weightless** · Near-zero effort. Critically damped, 150–220ms. Velocity continuity is mandatory.
- **Featherweight** · Light, explicitly reversible. Acknowledges without committing. Undo is structurally visible.

**Resistance** — how much the interface pushes back
- **Decisive** · Snaps at the moment of action. Fires on touchDown, not touchUpInside. The click IS the event.
- **Resistant** · Gives way only at threshold. Haptic fires at threshold, not completion.
- **Tentative** · Barely registers. The reversibility is in the physics, not the copy.
- **Yielding** · Carries your momentum. Zero stiffness during gesture, velocity-seeded on release.

**Rhythm** — the temporal shape of the interaction
- **Gathered** · Ambient recedes, focal expands. A held breath before the action. Requires stopping ambient animations system-wide.
- **Patient** · Loading is preparation. 2.5s shimmer, unhurried transitions. No urgency markers anywhere.
- **Punctuated** · Attack then decay — two animations, not one. Haptic fires at the peak between them.

**Echo** — how the system responds after the action
- **Heard** · Specific acknowledgment. "Your draft is saved" not "Saved." Specificity is the acknowledgment.
- **Echoed** · Stone then ripple. Secondary effect originates spatially from the primary.
- **Absorbed** · No feedback. The state change is the confirmation. Requires a legible new state.
- **Witnessed** · The action crosses a boundary. Travel animation from origin to destination.

### The Inside-Out Brief

Before any material decision on a new interaction, fill out the brief at `~/Projects/private/interfaces-that-feel/inside-out-brief-template.md`. Sequence is mandatory — each field unlocks the next:

1. **The Moment** — User's emotional state arriving / what they want to feel leaving
2. **The Felt Quality** — Name it precisely from the vocabulary. If you can't name it, you haven't found it.
3. **The Frogger Recipe** — Which of the 6 characteristics are load-bearing for this quality?
4. **Material Implications** — Derive timing, dynamics, modality, expression from the recipe
5. **The Default You're Replacing** — What would ship if no one thought about this?
6. **Success Check** — One observable user behavior, not a metric

---

## The Physical World Vocabulary

The practice says: use the physical world as your vocabulary. This is that vocabulary.

Each entry names a feeling, identifies a physical moment that already carries it, and extracts the behavioral property to borrow. These are not metaphors — they are material decisions. The physical world has already solved the problem of producing feelings. You are borrowing something that works.

---

**Not being alone in a solitary experience**
Physical moment: A party — the moment you look up and the room is full of people moving to the same thing. Strangers dancing near each other without speaking.
Behavioral property: Presence without interruption. Synchrony without announcement. Proximity without exchange.
Digital application: Co-presence indicators, shared listening states, collaborative cursors. Show others without surfacing them as demands on attention.

---

**The right resistance before commitment**
Physical moment: The resistance of a quality car door just before it closes. A deadbolt turning. A pen that clicks with a certain weight.
Behavioral property: Brief, tactile pause at the threshold. The action doesn't complete at zero effort.
Digital application: Confirmation before destructive actions. The pause should have weight: animation that slows at the threshold, copy that names the consequence, a moment where the user has to mean it.

---

**Acknowledgment that proves you were heard**
Physical moment: A reply that quotes the specific thing you said. A nod from someone who was clearly listening, not waiting to speak.
Behavioral property: The confirmation reflects back what actually happened — not the category of action, the specific action.
Digital application: "Your 14 items are saved" not "Saved." "Message sent to Maya" not "Sent." Specificity is the acknowledgment.

---

**Returning to somewhere familiar**
Physical moment: Coming home. Picking up a book and knowing, without checking, roughly where you left off.
Behavioral property: Minimal reorientation required. The familiar context is restored, not rebuilt.
Digital application: Return user states. Preserve scroll position, last action, in-progress work. Don't ask a returning user to re-establish themselves.

---

**Discovery that was always there**
Physical moment: Finding a note in a coat pocket from last season. A path in a city you've walked a hundred times that you've never taken.
Behavioral property: The thing was there before you found it. You didn't unlock it — you arrived at it.
Digital application: Hidden features and keyboard shortcuts. They don't require announcement. The curious user finds them; the rest never need to know.

---

**Things taking their natural time**
Physical moment: Ice melting. A photograph developing in a darkroom. Rain stopping.
Behavioral property: The process has a rhythm that isn't controlled by the observer. Progress is visible but not accelerable.
Digital application: Background processes, async work, generative responses. Don't compress perceived time with false urgency. Show what's happening — don't apologize for it.

---

**The moment before the thing you've worked toward**
Physical moment: The held breath before a starting gun. The last note before the rest falls away.
Behavioral property: A brief suspension. The threshold is felt before it's crossed.
Digital application: Final confirmation before a significant send, publish, or submit. The transition should pause, not rush.

---

**Permission to leave without guilt**
Physical moment: A host walking you to the door. A meeting that ends at the right time. A conversation that doesn't trail off.
Behavioral property: The exit is clean. The ending is as intentional as the beginning.
Digital application: Session end states, signout flows, task completion. No dark patterns. No "are you sure you want to leave?" Just: "You're all set."

---

**Being trusted with something fragile**
Physical moment: A librarian handing you a rare book without saying anything about it. A friend starting a difficult sentence.
Behavioral property: The weight is transferred with care. Nothing is rushed. Space is made for the receiver.
Digital application: Destructive action states. High-stakes submissions (medical, financial, legal). Slow it down. Confirm with specificity. Let the weight land before proceeding.

---

**Flow — momentum that feels earned**
Physical moment: Cycling with wind behind you on a flat road. Chopping vegetables with a sharp knife. Typing fast when the thought is already there.
Behavioral property: Each action chains naturally into the next. Nothing interrupts the rhythm.
Digital application: Keyboard shortcuts that chain. Autocomplete that doesn't interrupt. Commands that queue without confirmation. Repeat actions at zero friction for power users.

---

**Something recovering without requiring attention**
Physical moment: A tablecloth settling after you've moved a dish. A bruise fading.
Behavioral property: The recovery is automatic, gradual, and doesn't demand the user's attention.
Digital application: Undo, optimistic UI rollback, auto-save. "We've restored the previous version." No alarm, no manual action required. The system holds its own.

---

**Orientation after disorientation**
Physical moment: Eyes adjusting in a dark room. Finding a landmark after being lost.
Behavioral property: Something stable appears and everything else organizes around it. Resolution is gradual.
Digital application: Error recovery. Session expiry. Significant UI changes. Give one stable anchor before surfacing options.

---

**A wait that feels attended to**
Physical moment: Waiting for a friend at a café with coffee already ordered. Waiting for a storm you know is coming.
Behavioral property: The wait has context. The thing is coming and there's evidence of it.
Digital application: Loading states specific to what's loading. Skeleton loaders shaped like the real content. "Analyzing your results" not "Loading..." The user should know they're in the right place.

---

**Being seen in the exact moment**
Physical moment: A waiter refilling your glass exactly as it empties. Someone handing you what you need before you ask.
Behavioral property: The system understood the context without being told.
Digital application: Smart defaults. Pre-filled fields based on history. Contextual suggestions that arrive at the right moment. The product noticed something.

---

**Completion that allows rest**
Physical moment: Putting down a heavy bag. Pushing a plate slightly away after a meal. The moment a long flight lands.
Behavioral property: The weight releases. Nothing immediately demands the next action.
Digital application: Post-completion states. Milestones. Don't immediately surface the next task. Let the completion breathe before moving on.

---

**Something working exactly as it should**
Physical moment: A key that fits perfectly. An umbrella that opens in one motion. A zipper that doesn't catch.
Behavioral property: The interaction is invisible. It happens without requiring attention.
Digital application: Zero-friction, high-frequency interactions. Tab order. Form submit on Enter. Labels that focus their inputs. The absence of friction is the experience — not delight, but its necessary precondition.

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

### How We Feel — No Preferred Emotional State

How We Feel is the reference for one principle: **the product doesn't have a preference for how you feel.**

The emotion wheel doesn't celebrate positive states or pathologize negative ones. It treats grief as equal input to joy. The entry question ("What's one word for how you feel?") is open — it doesn't prompt for a category. The visual design is warm but not optimistic. Nothing in the UI is calibrated to steer you toward a better feeling.

Most wellness apps fail this test completely. They celebrate streaks, push notifications when you "fall behind," reward consistency. How We Feel understands that the act of naming a feeling is complete in itself — it doesn't need a downstream product outcome to justify it.

| Moment | What How We Feel does | The principle |
|---|---|---|
| You log that you feel terrible | Same interface, same warmth, no concern | Emotional neutrality as design stance |
| You haven't logged in days | No guilt notification | Absence is respected, not pursued |
| You complete an entry | Quiet confirmation, no gamification | The act was the thing, not the streak |

The failure mode it avoids: designing for users who are already okay.

### Headspace — Pacing as Care

Headspace is the reference for one principle: **the product controls the rhythm on behalf of the user's wellbeing, not on behalf of engagement.**

Transitions in Headspace are unhurried. Sessions have natural breathing room before and after. Nothing rushes to the next thing. The UX is slow in a way that is clearly intentional — not sluggish, but paced. The product has decided that moving at the speed of attention is the point, not a compromise.

Most apps optimize for time-in-app. Headspace optimizes for leaving the app feeling different than when you arrived.

| Moment | What Headspace does | The principle |
|---|---|---|
| Session ends | Space before the next prompt | Completion is allowed to land |
| You're selecting a session | Unhurried browsing, no FOMO indicators | Content is a library, not a feed |
| Transition between screens | Gradual, calm — matches the content | Form follows emotional function |

The failure mode it avoids: treating attention as a resource to maximize rather than a state to protect.

### Gentler Streak — Designing for Human Inconsistency

Gentler Streak is the reference for one principle: **the product's model of the user includes being human.**

The streak doesn't break on rest days — rest is part of the streak. You can mark a day as "gentle" and it counts. The app's entire premise is that the traditional streak model punishes the reality of human bodies. It redesigned the core mechanic around a more honest model of who actually uses fitness apps.

This is a product decision, not a UX one. The system was designed to accommodate the user rather than require the user to accommodate the system.

| Moment | What Gentler Streak does | The principle |
|---|---|---|
| You rest | Rest day is tracked, streak continues | Rest is not failure |
| You're tired | "Gentle" mode is a real option | The product meets you where you are |
| You've been consistent | Celebrates consistency, not perfect days | The goal is the underlying behavior |

The failure mode it avoids: gamification built on an idealized user who doesn't get tired, sick, or overwhelmed.

*Gentler Streak answers a premise question: "What if rest was part of the streak?" That decision is made before any interaction is designed. The micro-interactions are good — but removing them wouldn't destroy the product. Removing the premise would.*

### Amie — Time Is Social

Amie is the reference for one principle: **scheduling is about people, not slots.**

Amie surfaces "people" as a first-class object. A meeting isn't just a block of time — it's with someone, and the product surfaces that relationship. Tasks often exist in relation to people too. The visual design has warmth — illustrated elements, considered color — but the structural decision is what matters: the relational layer is visible, not buried.

Most calendar apps treat time as a grid. Amie treats time as the medium through which you interact with people.

| Moment | What Amie does | The principle |
|---|---|---|
| You create a meeting | People are first-class — not just attendees | Relationships are part of the event |
| You open the app | Warmth in the visual language | Scheduling something good should feel like planning something good |
| You complete a task | Small acknowledgment proportional to the action | Not every completion is a celebration |

The failure mode it avoids: treating a calendar as a neutral infrastructure tool when it's actually how you relate to other people.

### Arc — The Tool Becomes Yours Through Use

Arc is the reference for one principle: **the longer you use it, the more it feels like yours.**

Spaces, boosts (which let you restyle websites you visit), the archive, custom themes — Arc accumulates into a personal environment. Most browsers are neutral; they don't change based on how you use them. Arc becomes a reflection of you. The address bar is a prompt, not a field. Tabs are organized by intent, not by arrival order.

The emotional payoff is ownership. You feel like you built something, not just used something.

| Moment | What Arc does | The principle |
|---|---|---|
| You organize your spaces | The browser reflects your mental model | Structure should be yours to define |
| You boost a site | The web becomes your material | The tool gives you authorship |
| You return to Arc | Your environment is there — unchanged | Persistence as a form of trust |

The failure mode it avoids: designing a product that feels the same on day one and day three hundred.

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

**Motion communicates when it matches the nature of the change:**

The frequency table tells you *when* to animate. There is a second question: does animation actually help here, or just add noise?

Animation aids comprehension in three conditions:
- The change is **continuous** — a transformation unfolding over time (progress, generation, morphing)
- The change is **causal** — one thing caused another, and the motion shows the link
- The **user controls playback** — scrubbing, dragging, interactive animation

Outside these conditions, motion adds cognitive load without communicative value. A discrete state flip — a toggle, a save confirmation, a badge appearing — is often clearer as an instant transition than as an animation. The best motion doesn't show off; it makes the change legible.

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

---

## The Premise Question

If the vocabulary is working, the Frogger recipe is right, the interactions are considered — and it still feels like it's missing something at the center — this is where to look.

The question is not about the micro-interaction. It's about the premise.

The most quietly radical products surprise you with what they're even *for*. Not "a calendar app with better UX" — but "what if scheduling felt like planning something good?" Not "streaks but nicer" — but "what if rest was built into the streak itself?" This is **concept-level whimsy**: the entire premise is the surprise, not just the execution.

| Concept | The "What if" | The premise surprise |
|---|---|---|
| Interfaces for the Brokenhearted | What if we designed specifically for heartbreak? | The user state everyone ignores becomes the entire brief |
| PraiseOS | What if the OS praised you instead of demanding from you? | Inverts the power relationship between tool and user |
| Roll the Dice | What if chance was a feature, not a failure mode? | Randomness as delight rather than error |
| Gentler Streak | What if rest was part of the streak? | Core mechanic redesigned around human inconsistency |
| How We Feel | What if the app had no preferred emotional state? | Wellness without an agenda |

The distinction matters because **good execution of a flat premise is still flat**. A beautifully animated calendar with precise interactions is still just a calendar. Concept-level whimsy asks the prior question: should this even be a calendar?

**The test:** Can you summarize the concept in a "What if...?" that surprises someone? If yes — you're working with concept-level whimsy, and execution must match the premise's ambition. If no — you're working from a premise that exists, and execution is the entire lever.

**Signals that the premise is the problem:**
- The brief feels like polishing rather than designing
- The emotional register feels predetermined — the product decided in advance how everyone should feel
- You're adding interactions to compensate for something missing at the center
- The product is technically correct but nobody cares about it

**Routing gate:**
If the premise is flat: no vocabulary, Frogger recipe, or motion craft will save it. The work is upstream — in the product question, the brief, the thing you're actually building. This skill does not apply to that problem. Go back to the brief.

If the premise is resonant: this skill is the full toolkit. Start with the felt state.

---

## Research Backbone

The claims in this skill are grounded in the following peer-reviewed work. Reach for these when a claim needs to be defended or taken further.

**Emotional resonance**
- Norman, D.A. (2004). *Emotional Design*. Basic Books. — Visceral, behavioral, and reflective levels of emotional response; empirical basis for the aesthetic-usability effect.
- Kurosu, M. & Kashimura, K. (1995). Apparent usability vs. inherent usability. *CHI 1995*. — Original experiment: identical functionality, more beautiful design, higher perceived usability.
- Hassenzahl, M. (2010). *Experience Design*. Morgan & Claypool. — Hedonic quality (stimulation, identity, meaning) as a first-class design goal alongside usability.

**Physical world as vocabulary / embodied cognition**
- Dourish, P. (2001). *Where the Action Is*. MIT Press. — Foundational HCI text: we know through doing and touching, not through mental modeling. The theoretical basis for borrowing physical behavioral properties.
- Höök, K. (2018). *Designing with the Body*. MIT Press. — Somaesthetic interaction design: the designer's felt sense is a research instrument; the body is a design material.

**Delight, play, and intrinsic engagement**
- Csikszentmihalyi, M. (1990). *Flow*. Harper & Row. — Challenge-skill balance as the structural condition for interactions worth repeating beyond utility.
- Gaver, W. et al. (2004). The Drift Table: Designing for ludic engagement. *CHI 2004*. — Canonical empirical defense of non-instrumental interaction and exploration without a goal.

**Technology as lived experience**
- McCarthy, J. & Wright, P. (2004). *Technology as Experience*. MIT Press. — Technology is felt, narrative, and temporal. An interface designed only for task completion is aesthetically and humanistically incomplete.

**Designing for difficult emotional states**
- Massimi, M. & Baecker, R.M. (2010). A death in the family. *CHI 2010*. — Ethnographic study of bereaved users; launched thanatosensitive design as a research area.

**Motion**
- Tversky, B., Morrison, J.B. & Betrancourt, M. (2002). Animation: Can it facilitate? *International Journal of Human-Computer Studies*, 57(4). — Systematic review: animation aids comprehension only for continuous change, causal sequences, and user-controlled playback. Otherwise adds load.

**Interaction aesthetics and feel**
- Kuenen, S. (2018). *Aesthetics of Being Together*. PhD thesis, Umeå Institute of Design. — Inside-out design as method; the medium is never neutral; structural mechanisms of mediating interaction (Point of Summation, Signal/Relation, Channel/Space/Thing); diagnosis of why aesthetics of interaction theory doesn't translate to shipped products.
- Ross, P. & Wensveen, S. (2010). Designing behavior in interaction. *International Journal of Design*, 4(2). — Aesthetic Interaction as four principles: practical use, social/ethical dimensions, dynamic form, bodily/cognitive/emotional/social skills. The dominant academic framework for what "good" interaction feel looks like.
- Hallnäs, L. & Redström, J. (2002). From use to presence. *ACM Transactions on Computer-Human Interaction*, 9(2). — Foundational argument that products should be designed for their existential presence in a life, not just for efficient use.

**Anti-manipulation ethics**
- Gray, C.M. et al. (2018). The dark (patterns) side of UX design. *CHI 2018*. — First major empirical study of dark patterns; shows they emerge from structural incentives, not individual intent.
