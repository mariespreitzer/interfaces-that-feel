# Vocabulary × Frogger Map

Each felt quality is produced by a specific combination of Interaction Frogger coupling characteristics. This is the recipe for each term — specific enough to brief against, specific enough to diagnose what's wrong when a product misses.

---

## Weight Terms

### Settled
Completes at its own pace, comes to rest naturally, nothing asks what's next.

| Characteristic | Setting |
|---|---|
| Time | Completion at the natural end of the action — not rushed |
| Dynamics | Natural deceleration to stillness. Long ease-out tail. Low energy at rest. |
| Modality | Soft or absent at completion |

`cubic-bezier(0.23, 1, 0.32, 1)` at longer duration. No haptic or very soft. Energy resolves rather than announces.

---

### Grounded
Consequential, leaves a mark, something real happened.

| Characteristic | Setting |
|---|---|
| Time | Slight pause at completion — allowed to land |
| Dynamics | Heavy at commit, resolves firmly. Not a bounce — a drop. |
| Modality | Heavier haptic at commit |
| Expression | Responds to deliberateness — a hasty tap shouldn't feel grounded |

Settled rests. Grounded *lands*. The weight is at the moment of completion, not after it.

---

### Weightless
Happens with you, requires almost no effort, near-predictive.

| Characteristic | Setting |
|---|---|
| Time | Immediate — begins before you finish the gesture |
| Dynamics | Near-zero stiffness. Response floats rather than snaps. |
| Modality | Absent — any haptic would add weight |
| Expression | Responds to the smallest signal |

`spring(mass: 0.5, stiffness: 200, damping: 20)`. Very light, quick settle. The mechanism disappears.

---

### Featherweight
Responsive, light, explicitly reversible — you're trying, not deciding.

| Characteristic | Setting |
|---|---|
| Time | Quick but not instant — just enough acknowledgment |
| Dynamics | Low stiffness, gentle deceleration |
| Direction | Both directions equally open |
| Modality | Very light or absent |

Weightless doesn't acknowledge — it just happens. Featherweight acknowledges, lightly.

---

## Resistance Terms

### Decisive
Clicks into place at the moment of action, no hesitation.

| Characteristic | Setting |
|---|---|
| Time | Immediate — no gap |
| Dynamics | High stiffness, very short settle — snaps |
| Modality | Crisp haptic at exact moment of commitment |
| Direction | Resolves in one clear direction |

`UIImpactFeedbackGenerator.impactOccurred(intensity: 0.8)` at tap registration. Spring: `stiffness: 500, damping: 30`.

---

### Resistant
Requires deliberate intent, there's a moment where you feel you're choosing.

| Characteristic | Setting |
|---|---|
| Time | Requires hold or deliberate timing |
| Dynamics | Resistance curve — high initial resistance that gives way past a threshold |
| Modality | Haptic at the threshold moment, not at completion |
| Expression | Low-expression inputs don't complete |

Progressive spring. Below threshold: returns on release. Above threshold: gives way. Haptic fires at threshold crossing. The deadbolt turning.

---

### Tentative
Soft threshold, reversible, exploratory.

| Characteristic | Setting |
|---|---|
| Time | Slow to commit — time to change your mind |
| Dynamics | Very low stiffness — yields easily, returns easily |
| Direction | Both directions equally open |
| Modality | Absent |

The opposite of Decisive in almost every characteristic. For first-time experiences, exploratory states, moments where trying without consequence is the point.

---

### Yielding
The system gives way without friction, your momentum carries through.

| Characteristic | Setting |
|---|---|
| Time | Immediate, follows your pace exactly |
| Direction | Follows input direction exactly |
| Dynamics | Near-zero stiffness — momentum preserved |
| Modality | Absent |

Different from Weightless: Weightless is light. Yielding is *compliant* — it borrows your momentum rather than having its own.

---

## Rhythm Terms

### Gathered
Attention converges, the moment narrows, a breath before a starting gun.

| Characteristic | Setting |
|---|---|
| Time | Pause before completion — held at the threshold |
| Location | Ambient elements recede — field narrows to the action point |
| Dynamics | Slowing — deceleration toward stillness |
| Modality | Reduction — ambient motion stills, sound drops |
| Expression | Reads the deliberateness of the approaching action |

Requires all six working together, which is why Gathered is rare. The moment before a significant submit. Most products rush past this moment entirely.

---

### Patient
The system has time, nothing is pressing.

| Characteristic | Setting |
|---|---|
| Time | Unhurried — loading feels like preparation |
| Dynamics | Slow, gentle — low frequency, low amplitude |
| Modality | Quiet — no urgency haptics or sounds |
| Expression | Accepts low-pace engagement |

Headspace's session flow. Patient is the deliberate choice to design for a different pace than the user is typically in. That contrast is the experience.

---

### Punctuated
Clear beat, before and after, you feel the boundary.

| Characteristic | Setting |
|---|---|
| Time | Distinct threshold moment — marked before and after |
| Dynamics | Sharp peak at threshold, then settling — like a downbeat |
| Modality | Distinct haptic at the boundary moment |
| Direction | Resolves cleanly into the after-state |

Attack then decay. Most digital interactions have only decay — no attack, no felt boundary.

---

## Echo Terms

### Heard
Specific acknowledgment, reflects back what actually happened.

| Characteristic | Setting |
|---|---|
| Time | Immediate — at the moment of completion |
| Location | Proximate to the action |
| Dynamics | Proportional — quiet for small, more for significant |
| Modality | Multi-modal — visual and haptic both |
| Expression | Specific to the action — "Your 14 files are saved" not "Saved" |

Heard vs. Confirmed: Expression is the difference. The response reflects what you specifically did.

---

### Echoed
Action reverberates, consequence unfolds after the moment.

| Characteristic | Setting |
|---|---|
| Time | Primary immediate, secondary delayed — stone then ripple |
| Location | Effect radiates outward from action point |
| Dynamics | Decreasing energy over time |
| Modality | Initial haptic/visual, then visual trailing |

iMessage send animation: the message leaves, travels, delivers. Three distinct moments. The action went somewhere.

---

### Absorbed
Disappears quietly, no acknowledgment, the system continues.

| Characteristic | Setting |
|---|---|
| Time | Immediate state change, no acknowledgment pause |
| Dynamics | Near-zero |
| Modality | Absent |
| Location | No spatial feedback |

Right for high-frequency, low-stakes actions. Wrong when used for actions that deserve Heard — the user doesn't know if it worked.

---

### Witnessed
Something external noted this, it was seen.

| Characteristic | Setting |
|---|---|
| Time | Confirmed after a beat — something received it |
| Direction | Outward — the action traveled beyond the local system |
| Modality | Distinct notification quality — arrived from elsewhere |
| Expression | Responsive to what was done |

Requires the product to convey that the action crossed a boundary. The receipt notification. "Sent to 312 subscribers." Something happened beyond the edge of the screen.

---

## The Pattern

**Dynamics is load-bearing for almost everything.** Appears in 10 of 14 terms. The most neglected characteristic in digital products — because events are binary — and the one doing the most work in producing felt quality. Where most products leave the most on the table.

**Expression is the amplifier.** Doesn't produce felt quality alone — it intensifies and personalizes whatever the other characteristics produce. Heard without Expression is just Confirmed. Grounded without Expression is just heavy. Expression is what makes an interaction feel like a response to *you* rather than to the action category you performed.

**The brief recipe:** Set the primary characteristic (usually Dynamics or Time) → set the secondary (usually Modality) → decide whether Expression amplifies it. That's enough to orient every material decision.

---

*From the "Interfaces That Feel" project — mapping the felt vocabulary to the Interaction Frogger (Wensveen et al., DIS 2004)*
