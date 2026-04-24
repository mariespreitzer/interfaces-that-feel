# Vocabulary — Full Implementation Specs

For each felt quality: spring parameters, easing curve, duration, haptic call (iOS + web), additional visual spec, and the critical note that separates it from the adjacent term.

**Spring parameters** use physics values: stiffness (speed/snappiness), damping (decay of oscillation), mass (weight/inertia). These translate to Framer Motion, React Spring (tension = stiffness, friction = damping), iOS UISpringTimingParameters, and SwiftUI .spring().

**Critical damping** = `2 × √(stiffness × mass)`. Below: bouncy. Above: overdamped. At: fastest settle with no bounce.

---

## Weight Terms

### Settled
Completes at its own pace, comes to rest naturally, nothing asks what's next.

```
Spring:    stiffness: 120, damping: 22, mass: 1.0  →  overdamped, no bounce
CSS:       cubic-bezier(0.23, 1, 0.32, 1)
Duration:  400–550ms
```

Haptic: None at completion. If any: `UIImpactFeedbackGenerator.impactOccurred(intensity: 0.2)`. Web: none.

Visual: No scale change. If container: subtle elevation reduction (3 → 1) communicates settling.

**Critical note:** Requires overdamping — `damping > 2√(stiffness × mass)` = `2√120 ≈ 21.9`. Go to 22+. The moment you go underdamped, it becomes Punctuated.

---

### Grounded
Consequential, leaves a mark, something real happened.

```
Spring:    stiffness: 300, damping: 25, mass: 1.2  →  underdamped, heavy — slight overshoot then resolves
CSS:       cubic-bezier(0.34, 1.56, 0.64, 1) for drop phase
Duration:  280–360ms
```

Haptic: `UIImpactFeedbackGenerator.impactOccurred(intensity: 0.9)` — fires at tap registration, not animation completion. Web: `navigator.vibrate(12)` on pointerdown confirmed.

Visual: `scale: 1.0 → 0.97 → 1.0` — compression and haptic fire together. The overshoot in the spring reads as the element finding its footing.

**Critical note:** Haptic fires on commit (touchDown), not on animation end. A 30ms misalignment makes it feel like two separate events instead of one landing.

---

### Weightless
Happens with you, requires almost no effort, near-predictive.

```
Spring:    stiffness: 200, damping: 20, mass: 0.5  →  critically damped (2√100 = 20), fastest settle
CSS:       cubic-bezier(0.16, 1, 0.3, 1)
Duration:  150–220ms
```

Haptic: None. Any haptic adds weight.

Visual: For direct manipulation — set initialVelocity to gesture's terminal velocity. No velocity discontinuity at gesture end.

```swift
let velocity = gestureRecognizer.velocity(in: view)
let springParams = UISpringTimingParameters(
    mass: 0.5, stiffness: 200, damping: 20,
    initialVelocity: CGVector(dx: velocity.x / distance, dy: 0)
)
```

**Critical note:** Velocity continuity is mandatory. If the animation starts from zero velocity while the gesture was moving, you get a jerk — the opposite of weightless.

---

### Featherweight
Responsive, light, explicitly reversible — trying not deciding.

```
Spring:    stiffness: 150, damping: 18, mass: 0.8  →  slightly underdamped, minimal oscillation
CSS:       cubic-bezier(0.25, 0.46, 0.45, 0.94)
Duration:  220–300ms
```

Haptic: `UISelectionFeedbackGenerator.selectionChanged()` on hover/highlight before commit. Web: `navigator.vibrate(6)`.

Visual: `scale: 0.98 → 1.0`, `opacity: 0.85 → 1.0`. Undo must be immediately visible — surfaced in the completion state.

**Critical note:** Featherweight acknowledges the action; Weightless doesn't. If the user should know something happened, use Featherweight. If it should be invisible infrastructure, use Weightless.

---

## Resistance Terms

### Decisive
Clicks into place at the moment of action.

```
Spring:    stiffness: 500, damping: 30, mass: 0.8  →  underdamped (critical = 40), snaps with brief oscillation
CSS:       cubic-bezier(0.34, 1.56, 0.64, 1)
Duration:  140–180ms
```

Haptic: `UIImpactFeedbackGenerator.impactOccurred(intensity: 0.8)` — fires on touchDown (tap registration), before animation begins. Web: `navigator.vibrate([8, 0])`.

```css
@keyframes decisive-press {
  0%   { transform: scale(1.0); }
  30%  { transform: scale(0.94); }
  70%  { transform: scale(1.06); }
  100% { transform: scale(1.0); }
}
animation: decisive-press 160ms cubic-bezier(0.34, 1.56, 0.64, 1);
```

**Critical note:** Haptic fires on touchDown, not touchUpInside. 80–150ms difference changes "this clicked" to "this confirmed." Decisive requires the click.

---

### Resistant
Requires deliberate intent — high resistance that gives way at threshold.

**Below threshold (drag phase):**
```
Rubber-band: visual_offset = gesture_offset × (1 − gesture_offset/max_displacement)^0.55
Return spring: stiffness: 400, damping: 30  →  snaps back firmly on release below threshold
```

**At threshold:**
Haptic: `UIImpactFeedbackGenerator.impactOccurred(intensity: 0.7)` at exact threshold crossing. Web: `navigator.vibrate([6, 30, 10])`.
Visual: brief color/opacity shift (1.0 → 1.04) — signals "you've crossed it."

**Above threshold (completion):**
```
Spring:    stiffness: 350, damping: 22, mass: 1.0  →  slight overshoot (the "give way")
Duration:  220–280ms
```

**Critical note:** Haptic fires at threshold during the gesture, not at completion. If it fires at completion, the threshold moment is unfelt — you crossed an invisible line. The haptic is the line.

---

### Tentative
Soft threshold, reversible, exploratory.

```
Spring:    stiffness: 100, damping: 18, mass: 1.0  →  slightly underdamped, very gentle
CSS:       cubic-bezier(0.25, 0.1, 0.25, 1.0)
Duration:  300–420ms
```

Haptic: `UISelectionFeedbackGenerator.selectionChanged()` or none. Web: none.

Visual: `opacity: 0.88 → 1.0`, `scale: 0.98 → 1.0`. Low visual weight even after action. Undo prominently surfaced in the completion state.

**Critical note:** Tentative communicates reversibility. Don't use it for actions with real consequences — it's a trust violation if the action isn't actually reversible.

---

### Yielding
The system gives way without friction, your momentum carries through.

```
Release spring: stiffness: 60, damping: 12, mass: 1.0  →  underdamped, momentum-preserving
iOS:            UIScrollView.DecelerationRate.normal (0.998)
Duration:       momentum-dependent, not fixed
```

Haptic: None. A haptic would mark a threshold that doesn't exist.

Visual: Zero lag during gesture — no easing while touching. Velocity-matched release:

```swift
UIView.animate(
    withDuration: 0, delay: 0,
    usingSpringWithDamping: 0.7,
    initialSpringVelocity: velocity.x / targetDistance,
    options: .curveLinear
) { ... }
```

**Critical note:** Any velocity discontinuity at gesture end breaks Yielding. The animation must start from the gesture's terminal velocity — not from zero.

---

## Rhythm Terms

### Gathered
Attention converges, ambient recedes, a breath before the action.

```
Ambient dimming:   opacity: 1.0 → 0.35, duration: 300ms, cubic-bezier(0.4, 0, 0.2, 1)
Ambient motion:    stop all non-focal animations
Focal element:     scale: 1.0 → 1.02, elevation increase
Gather duration:   300–500ms
```

Haptic: `UIImpactFeedbackGenerator.impactOccurred(intensity: 0.15)` — a breath, at gather start. Web: none.

```css
.gathered-context .non-focal {
  opacity: 0.35;
  transition: opacity 300ms cubic-bezier(0.4, 0, 0.2, 1);
  pointer-events: none;
}
.gathered-context .focal {
  transform: scale(1.02);
  transition: transform 300ms cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

**Critical note:** Gathered requires stopping ambient animations system-wide. Continuous motion (pulsing badges, spinning indicators, blinking presence dots) prevents the visual field from narrowing. This is a systemic decision, not per-component.

---

### Patient
The system has time. Nothing is pressing.

```
Screen transitions:  450–600ms (vs. typical 280–350ms)
CSS:                 cubic-bezier(0.4, 0.0, 0.2, 1)
Shimmer animation:   2.5s ease-in-out infinite (vs. typical 1.2–1.5s)
Content stagger:     80–120ms between elements
```

Haptic: None on transitions.

```css
@keyframes patient-shimmer {
  0%   { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}
.skeleton {
  background: linear-gradient(90deg, #f0f0f0 25%, #e0e0e0 50%, #f0f0f0 75%);
  background-size: 200% 100%;
  animation: patient-shimmer 2.5s ease-in-out infinite;
}
```

Loading copy: "Getting your [thing] ready" not "Loading..." Copy communicates preparation, not apology.

**Critical note:** Patient requires removing urgency markers entirely — no countdown timers, no badge accumulation, no "X items waiting." Urgency breaks Patient the way ambient motion breaks Gathered.

---

### Punctuated
Clear beat, before and after — attack then decay.

```
Phase 1 (attack):   120–160ms, cubic-bezier(0.34, 1.56, 0.64, 1)  →  scale 1.0 → 1.07
Phase 2 (decay):    320–400ms, cubic-bezier(0.23, 1, 0.32, 1)      →  scale 1.07 → 1.0
Total:              440–560ms — asymmetric by design
```

Haptic: `UIImpactFeedbackGenerator.impactOccurred(intensity: 0.75)` — fires at attack peak (after attack phase ends), not at start. Web: `navigator.vibrate([10])` at peak.

```javascript
// Two-phase implementation — do not collapse into one animation
element.animate(
  [{ transform: 'scale(1)' }, { transform: 'scale(1.07)' }],
  { duration: 140, easing: 'cubic-bezier(0.34, 1.56, 0.64, 1)', fill: 'forwards' }
).onfinish = () => {
  haptic.fire(); // at the peak
  element.animate(
    [{ transform: 'scale(1.07)' }, { transform: 'scale(1)' }],
    { duration: 380, easing: 'cubic-bezier(0.23, 1, 0.32, 1)', fill: 'forwards' }
  );
};
```

**Critical note:** Two-phase structure is mandatory. A single animation can't place the haptic at the peak because there's no definable peak in a single curve. Attack + decay = the downbeat.

---

## Echo Terms

### Heard
Specific acknowledgment — reflects back exactly what happened.

```
Spring:    stiffness: 200, damping: 20, mass: 1.0 (confirmation pulse)
Animation: scale 1.0 → 1.04 → 1.0, duration: 280ms
Display:   2.5–3.5s, no auto-dismiss for consequential actions
Position:  proximate to action — not top-of-screen
```

Haptic: `UINotificationFeedbackGenerator.notificationOccurred(.success)` at confirmation appearance. Web: `navigator.vibrate([10, 50, 10, 50, 20])`.

Copy rule — template: "Your [specific thing] [past-tense verb]"

| Generic | Heard |
|---|---|
| "Saved" | "Your draft is saved" |
| "Sent" | "Message sent to Maya" |
| "Done" | "14 files exported" |

**Critical note:** Heard ≠ Confirmed. Confirmed says it worked. Heard proves the system understood what specifically you did. Specificity is the acknowledgment.

---

### Echoed
Action reverberates — stone then ripple.

```
Primary:     fires at completion (Heard quality)
Secondary:   delay: 250–400ms after primary
             opacity: 1.0 → 0.0, scale: 1.0 → 2.2
             duration: 600ms, cubic-bezier(0.2, 0.8, 0.4, 1)
             origin: from the action point
```

Haptic: Primary: `.success` notification. Secondary: `UIImpactFeedbackGenerator.impactOccurred(intensity: 0.3)` at 300–400ms delay. Web: `navigator.vibrate([10, 300, 6])`.

```css
@keyframes echo-ripple {
  0%   { transform: scale(1); opacity: 0.6; }
  100% { transform: scale(2.2); opacity: 0; }
}
.echo-ripple {
  animation: echo-ripple 600ms 350ms cubic-bezier(0.2, 0.8, 0.4, 1) forwards;
  border-radius: 50%;
  border: 1.5px solid currentColor;
}
```

**Critical note:** Secondary must originate spatially from the primary. A ripple appearing elsewhere reads as a separate event. Echoed requires spatial continuity — the consequence visibly travels from the cause.

---

### Absorbed
Disappears quietly. The system continues.

```
Transition: instant — 0ms — OR opacity crossfade: 80ms maximum
Animation:  none
Haptic:     none
Copy:       none
```

The state change is the confirmation. If you must explain that the action worked, use Heard instead.

When to use: auto-save, background sync, tab switching, any high-frequency low-stakes action.

**Critical note:** Absorbed without a legible state change = silent failure. "The spinner disappeared" is not legible. "The document title lost its unsaved indicator" is. The new state must be immediately self-explanatory.

---

### Witnessed
The action crossed a boundary — went somewhere, reached someone.

```
Travel animation:  path from origin to destination, slight arc
                   duration: 400–600ms, cubic-bezier(0.4, 0, 0.2, 1)
Destination:       element arrives with Settled quality
Secondary receipt: appears after appropriate delay (100ms to seconds)
```

Haptic: `UINotificationFeedbackGenerator.notificationOccurred(.success)` — the notification-level pattern, distinct from impact. Receipt: `UIImpactFeedbackGenerator.impactOccurred(intensity: 0.4)` when receipt arrives. Web: `navigator.vibrate([8, 40, 12])`.

Copy: destination-specific — "Sent to maya@..." / "Delivered to 312 subscribers."

**Critical note:** Witnessed requires spatial movement. A toast saying "Sent" without any travel animation is Heard at best. The action must visibly cross a boundary.

---

## Implementation Summary

| Term | Spring (s/d/m) | Duration | Haptic | Key characteristic |
|---|---|---|---|---|
| Settled | 120/22/1.0 overdamped | 400–550ms | None | No bounce |
| Grounded | 300/25/1.2 overshoot | 280–360ms | Heavy at touchDown | Lands, doesn't rest |
| Weightless | 200/20/0.5 critical | 150–220ms | None | Velocity continuity |
| Featherweight | 150/18/0.8 soft | 220–300ms | Selection (lightest) | Acknowledges lightly |
| Decisive | 500/30/0.8 snap | 140–180ms | Medium at touchDown | Haptic before animation |
| Resistant | Progressive | Gesture-dependent | Medium at threshold | Threshold haptic |
| Tentative | 100/18/1.0 gentle | 300–420ms | None | Reversibility structural |
| Yielding | 60/12/1.0 momentum | Momentum-dependent | None | Velocity continuity |
| Gathered | Compositional | 300–500ms | Feather at start | Stop ambient motion |
| Patient | Slow all transitions | 450–600ms | None | Remove urgency markers |
| Punctuated | Two-phase | 440–560ms | Medium at attack peak | Two animations, not one |
| Heard | Pulse + display | 280ms + 2.5–3.5s | Success notification | Specific copy |
| Echoed | Ripple from origin | Primary + 350ms | Success + light echo | Spatial continuity |
| Absorbed | 0–80ms | Instant | None | Legible state change |
| Witnessed | Path travel | 400–600ms | Success + receipt | Travel animation |

---

*From the "Interfaces That Feel" project — full implementation specs for the felt interaction vocabulary*
