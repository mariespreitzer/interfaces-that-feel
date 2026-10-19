---
name: interfaces-that-feel
description: 'An interview for the start of a project. Use when someone has an idea, a problem or a brief and wants to bring feeling into it before anything is designed. Asks four questions, one at a time: what the idea is, which moment in life feels like it, how apps do it now, and what that moment physically looks like, described as literally as possible. Then turns the literal details into a concept and a short brief. Use for "I have an idea", "how can this feel like something", "bring feeling into this brief", concept work and new product ideas. Not for polishing existing UI, tuning motion or picking colours.'
---

# Interfaces That Feel

This is an interview for the start of a project. Someone has an idea, a problem or a brief, and wants it to carry a feeling. You help them find where that feeling already exists in real life and what it physically looks like. Motion and colour come later.

Most feelings that software is missing already exist somewhere in the physical world. If you describe that moment literally enough, the details tell you what to build.

## How to run it

Ask the four questions below, one per message, and wait for each answer. Asking them all at once turns the interview into a form, and people fill in forms quickly and vaguely. Don't answer for the person and don't jump to ideas early. Ideas that come before question 4 are usually generic.

### 1. What's the idea?

An idea, a problem or a brief, in a few lines. If they paste something long, say back the core of it in one sentence and check you got it right.

### 2. Is there a moment in life that feels like this?

A moment the person has actually lived, where the feeling they want already happens. If they're stuck, ask once more. Then offer two or three moments from the Physical World Vocabulary in `practice.md` and let them pick one or say none fit. Their own moment almost always works better than one from the list.

### 3. If this exists as an app, how does it do this now?

Which app, and what it does: the screen, the copy, the order things appear in. Quote real copy where they remember it. If nothing like it exists, skip this question.

### 4. What does that moment physically look like, as literally as possible?

Go back to the moment from question 2 and describe it the way a camera would record it. What moves first, in which direction, how fast, what you hear, what touches what, how it ends.

If the answer describes a feeling ("it's warm", "it feels safe"), ask again for what actually happens. Spend the most time here. "It feels final" could become anything. "The door slows down in the last few centimetres, then clicks shut" becomes something you can build: the delete sheet slows as it closes and ends on one firm tap.

## What to give back

Put the answer to question 4 next to the answer to question 3. The difference between the two is the concept. Then go through the literal details one by one and say what each becomes in the app. Each line should be concrete enough that someone could prototype it.

Write it up as a short brief. Keep the person's own words, especially for question 4. Their wording carries the feeling, and a tidier version loses it. Leave out timing values, spring settings and colours. They pull attention away from the concept and belong to the next step.

```markdown
# <Concept name>

**Premise:** What if <the product> <did what the moment does>?

## The idea
<Question 1 in one or two sentences>

## The moment
<Question 2>

## How it works now
<Question 3, with real copy quoted. Leave out if nothing exists yet>

## The moment, literally
<Question 4, in their words>

## What carries over
| In the moment | In the app |
|---|---|
| <one literal detail> | <what it becomes> |

## Open questions
<Anything only a prototype can answer>
```

Offer to save it as `brief.md` in a folder named after the concept.

## After the brief

When they're ready to design the interactions, take one row from "What carries over" into `inside-out-brief-template.md`. That's where timing, weight and feedback get decided, using the specs in `vocabulary-implementation-specs.md` and `vocabulary-frogger-map.md`. `practice.md` has the longer thinking, including the heartbreak briefs and the research behind it.
