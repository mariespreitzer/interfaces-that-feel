# The Interaction Frogger — Digital Disassembly

Taking the six coupling characteristics of the Interaction Frogger (Wensveen, Djajadiningrat & Overbeeke, DIS 2004) and running each through three stages: the theoretical claim, where it breaks in digital products, and implementation specs for getting it right.

This is the closest existing academic bridge to practice — extended and translated for digital product design.

---

## 1. Time

**The claim**
The response should happen at the right moment relative to the action. There should be a felt temporal relationship between what you do and what happens — not too early (before the action is complete), not too late (after you've moved on). The timing of the effect should feel caused by the timing of the action.

**Where it breaks in digital**
Response timing in digital products is designed around network latency and render cycles, not around felt interaction timing. These are completely different problems. The result:

- Animations that play *after* the state has already changed. The UI flips to the new state, then the transition animates. Backwards. Slightly uncanny.
- Loading states with no temporal texture. A spinner gives no felt relationship to time — you're in a void, not waiting for something specific.
- Operations that acknowledge completion at the wrong moment. The action lands at the network layer; the UI responds when the server replies. The user's felt sense of "I did the thing" and the system's confirmation of it are decoupled by an invisible gap.
- Optimistic UI that silently rolls back. The action appeared to complete, the confirmation appeared, and then — without announcement — it didn't happen. The temporal relationship was a lie.

**The felt consequence**
When time coupling is right, the action and its response feel *unified* — one thing, not two. When it breaks:

- Too fast or immediate-before-complete: feels mechanical, like the system was doing this regardless of you
- Too slow: the action and consequence feel unrelated — you're watching a system event, not receiving a response
- Animation-after-state: uncanny, slightly wrong, like the body and the shadow moving out of sync
- Generic loading: temporal relationship disappears entirely. You're waiting, but not *for something*

**Spec toward the right**
- Direct manipulation: response begins within 100ms. Not completes — *begins*. The animation starts at the moment of action.
- The animation should *start* at the moment of commitment, not after state resolves. Motion is the acknowledgment; completion is the confirmation.
- Loading states need temporal texture. Not a spinner — a skeleton shaped like the real content, specific copy ("Analyzing your results" not "Loading..."), progress that feels proportional to actual wait.
- Where the operation is async: give two-stage confirmation. Immediate acknowledgment (the action was received), then completion (the result is here). Don't make the user wait through both in one moment of silence.
- For long waits: offer to notify on completion. Don't trap attention.

---

## 2. Location

**The claim**
Feedback should appear at — or originate from — the location of the action. Where the effect happens should have a spatial relationship to where the cause happened. The response should feel *connected* to the action in space, not just in sequence.

**Where it breaks in digital**
This is violated constantly, because UI feedback systems are designed at the system level, not the interaction level:

- Toasts appear at the top of the screen regardless of where the action happened. You tap something at the bottom — a confirmation appears at the top. Spatially disconnected.
- Error messages appear in banners, not at the element that caused them.
- Modals and sheets emerge from screen center or screen edge regardless of where the triggering element lives.
- Success states appear in a different part of the UI from where you completed the action.

**The felt consequence**
When location is decoupled: the feedback feels like a *system announcement*, not a *direct response*. Something the product decided to show rather than something your action caused. It breaks direct manipulation — the felt sense that you're touching and moving things rather than sending commands.

The opposite: iOS share sheet originates from the share button. That's why it feels like you *lifted* the share sheet out of the button rather than *summoned* it from nowhere.

**Spec toward the right**
- Modals, sheets, and popovers should expand from the element that triggered them. Use transform-origin tied to the triggering element's position, not a fixed screen coordinate.
- Error states appear at the input, not in a banner. The label turns, the helper text changes, the border shifts — all at the field itself.
- Success confirmation appears proximate to the completed action.
- If feedback genuinely must appear elsewhere: at minimum, animate it from the action point to its destination. The spatial relationship is preserved in motion even if not in position.
- Dropdowns and menus: open toward available screen space from the trigger element. Never materialize from a fixed position.

---

## 3. Direction

**The claim**
The direction of the action should correspond to the direction of the response. If you move something right, it goes right. If you navigate deeper, you move in a consistent spatial direction. Cause and effect share a directional logic — you can feel the spatial model of the interface through the gesture.

**Where it breaks in digital**
Navigation systems are the main failure point. Most are designed as logical hierarchies, not spatial ones:

- Navigating into a modal that slides in from the right — then dismissing it with a gesture that sends it to the bottom. Directionally inconsistent.
- Tab navigation where swiping between tabs doesn't match the direction of tab order.
- Swipe-to-delete: the element moves right (matching the gesture) but then disappears from the right — the direction is used then violated at conclusion.
- Pull-to-refresh: you pull down, but the content refreshes from the top — directional tension.
- Any navigation that feels like teleportation rather than movement.

**The felt consequence**
When direction is inconsistent: navigation feels like *pressing buttons*, not *moving through space*. The mental model collapses. When direction is consistent: the interface has *spatial memory* — you know without thinking which direction back is.

iOS gets this right: swiping right navigates back because you came from the left. The direction is semantically consistent with the spatial model.

**Spec toward the right**
- Define a spatial model for your navigation and hold to it. Deeper = right or down. Back = left or up. Everywhere.
- Entrance direction of a screen determines its exit direction. If it slid in from the right, it dismisses to the right.
- Swipe-to-action: the element moves in the swipe direction and the consequence continues from that direction.
- Drag-and-drop: the dragged element follows the finger exactly, arrives at the drop zone from the direction it was travelling, and settles in place. No teleportation at drop.
- Avoid crossed axes in the same gesture space.

---

## 4. Dynamics

**The claim**
The dynamics of the response should match the dynamics of the action. A fast, forceful action should produce a proportional response. A slow, deliberate action should produce a proportional response. The *how* of the action (its speed, force, weight) should be reflected in the *how* of the response.

**Where it breaks in digital**
Almost universally violated, because input events are binary at the semantic level — a tap is a tap, regardless of how it was tapped:

- Every tap produces the same spring animation, whether decisive or hesitant.
- A fast swipe and a slow one produce identical responses.
- A long press produces the same visual weight as a quick tap.
- A destructive delete and a routine save have the same animation weight.

**The felt consequence**
When dynamics are unmatched: the interaction feels *generic*. The system responded to what you did but not how you did it. This is one of the deepest sources of "it doesn't feel alive" — a living thing responds to how you touch it, not just that you did.

**Spec toward the right**
- Gesture velocity → animation velocity. Use velocity from the gesture recognizer as a parameter in the animation.
- Spring stiffness and damping as a dial, not a fixed value. Higher stiffness for decisive, high-velocity actions. Lower stiffness for exploratory, gentle ones.
- Destructive actions get heavier dynamics than constructive ones — not the same spring curve.
- Long-press → heavier initial response weight at release. The held energy transfers.
- Where hardware allows (Force Touch, Apple Pencil): response weight tied to applied pressure.

---

## 5. Modality

**The claim**
The sensory modality of the action should be met by a response in a complementary modality. Touch should get touch back. Sound should get a sonic response. There should be felt correspondence between the sense used to act and the sense used to receive. The action and the feedback should exist in the same sensory world.

**Where it breaks in digital**
Most digital interactions are touch-in, visual-out:

- Touch interactions with no haptic response. You press a surface and receive only a visual acknowledgment. The touch modality is unacknowledged — you pressed glass and it changed color at you.
- Haptic at the wrong moment — fires when animation completes, not when action commits. Temporally decoupled.
- Generic haptic patterns for every action type. The same buzz for success and error. Modality present but semantically empty.
- Vision-only error states. The error registers visually but not in the modality of the mistake.

**The felt consequence**
When modality is unmatched: the interaction is one-dimensional. You gave something embodied; the system replied in a different language. When it's right: the response feels *immediate* and *complete* — you got something back in the same register you gave.

**Spec toward the right**
- Every meaningful touch action → haptic + visual.
- Destructive actions → heavy impact feedback.
- Success → `.success` notification feedback (UINotificationFeedbackGenerator). Light, positive, resolved.
- Error → `.error` notification feedback + visual. Felt, not just seen.
- Haptic fires at moment of action commitment, not at animation completion.
- Differentiate haptic patterns semantically: success ≠ error ≠ selection ≠ impact.
- Sound as modality complement: match sound weight to action weight. Destructive actions are not silent.

---

## 6. Expression

**The claim**
The qualitative character of the action — not just *what* you did but *how* you did it — should influence the qualitative character of the response. A careful, slow action should be received differently from a bold, decisive one. The *expression* of the action matters, not just its type.

**Where it breaks in digital**
The most profoundly and universally violated characteristic — because event systems strip expression at the protocol level. A tap event contains coordinates and a timestamp. It doesn't contain hesitation, confidence, care, or uncertainty:

- Typing hesitantly produces the same autocomplete as typing confidently.
- A user who navigates slowly (reading, uncertain) receives the same interface as a power user who moves quickly.
- Repeated failure on the same field produces the same error message the third time as the first.
- Hover dwell time — a clear signal of attention, interest, or uncertainty — is almost never responded to differently.

**The felt consequence**
When expression is ignored: the interaction feels *mechanical*. Like pressing a piano key that plays the same note regardless of how hard you press it. Your care, uncertainty, boldness are invisible. This is the deepest explanation for interfaces that feel generic even when visually polished — they can see what you did, but not how you were.

**Spec toward the right**

*Through hardware where available:*
- Pressure (Force Touch, Apple Pencil): response weight tied to applied pressure.
- Gesture velocity as expression proxy: fast = confident; slow = exploratory. Use accordingly.

*Through behavioral patterns:*
- Repeated field failure (3+): response escalates. Acknowledge the pattern, not just the error. "Let's try a different approach."
- Hover dwell time: long hover on a complex element → deeper tooltip or secondary action surface. Short hover → standard affordance.
- Navigation hesitation (back immediately, re-enter): surface a clarifying anchor. The user is lost — acknowledge it without announcing it.
- Typing pace in search: slowing down mid-query suggests uncertainty. Don't aggressively autocomplete. Give space.

The rule: capture expression through the behavioral signal closest to the felt character of the action, and respond in kind.

---

## Summary: What the Frogger reveals about digital products

| Characteristic | Most common failure | Felt consequence |
|---|---|---|
| Time | Response timing driven by network/render, not felt interaction | Action and consequence feel unrelated |
| Location | Feedback at system level, not interaction level | Feedback feels like announcement, not response |
| Direction | Navigation designed as logic, not space | Interface feels like buttons, not places |
| Dynamics | Input events are binary — no dynamic differentiation | Everything feels generic, same weight |
| Modality | Touch-in, visual-out by default | Touch feels like touching glass |
| Expression | Event systems strip the how, keep only the what | The system sees your actions, not you |

The pattern: every failure is a case where a technical default took over an aesthetic decision. None of these are hard problems. They require intention, not engineering breakthroughs.

---

*From: Interaction Frogger (Wensveen, Djajadiningrat & Overbeeke, DIS 2004) — translated to digital product design for "Interfaces That Feel"*
