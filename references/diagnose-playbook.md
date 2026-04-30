# Diagnose Playbook — The Opening Moves of a Learning Session

This file is your script for the **first 3-10 minutes** of any learning
session. A bad opening locks in a bad session — you end up either boring
someone who already knew the material, or burying a beginner under jargon
they can't catch.

The cost of spending a few minutes diagnosing is tiny. The cost of skipping
it is enormous. Do not skip it, even when the learner seems impatient.
Especially when the learner seems impatient.

---

## Why diagnosis matters more than it seems

Learners usually can't accurately describe what they already know. Three
patterns show up constantly:

1. **Overconfidence at the name level.** "Yeah, I know recursion." Probes
   reveal they can recite a definition but can't trace a simple call stack.
2. **Underconfidence at the skill level.** "I don't really know Git." Probes
   reveal they use it fluently for common cases and just haven't faced rebases.
3. **Mismatched goal and path.** Learner asks to learn X, but their actual
   goal is solvable by learning a much smaller Y, or requires a much bigger Z.

Your job in diagnosis is to surface all three — politely and quickly.

---

## The 4-question opening (use every time)

Ask these in order. Do not batch them into one message — ask, wait, read the
answer, then ask the next. The *delay* is part of the pedagogy; it signals
that answers matter.

### Q1 — Destination

> "What do you want to be able to *do* after we're done? Paint me the
> concrete scene — who's using it, what are you showing, what does success
> feel like?"

**What you're listening for:**
- A tangible artifact or capability → good, we can reverse-engineer a path.
- "I just want to understand it better" → push for why. "Understand it in
  order to _{what}_?" Unspecified motivation kills follow-through.
- A destination that's too big for this session → gently scope down. "That's
  a 10-week road. Which slice would give you the most value this week?"

### Q2 — Current standing

> "What's your starting point? What have you already tried, read, watched,
> or built that's related? Even the half-finished attempts count."

**What you're listening for:**
- Real prior experience → start mid-path, skip basics. Confirm with a micro-probe
  (Q4) before you commit.
- Almost nothing → start from first principles, but find at least one analogy
  from their non-related background.
- A failed attempt → gold. The failure contains a concrete obstacle you can
  use as the organizing problem of the session.

### Q3 — Constraints and context

> "How much time do you have for this — today and over the coming weeks?
> And are you learning this alone, or alongside someone / for a specific
> project?"

**What you're listening for:**
- Available time shapes depth. 30 minutes → one concept + one application.
  Several weeks → full curriculum.
- Presence of a real project → use it as the running example. Hugely
  accelerates learning.
- Isolation → they'll need you to play the role of the peer review. Plan for
  more Challenge-family questions later.

### Q4 — Micro-probe (the calibration shot)

> "Before we start, humor me with a quick one: _{a concrete question at the
> level you think they're at}_. No pressure if you don't know — I just want
> to calibrate where to start."

**Construction rules for the probe:**
- It should be answerable in one or two sentences.
- It should discriminate: easy if they're past the level, hard if they're
  below it. Avoid "fair middle" — those tell you nothing.
- Frame it as calibration, not a test. Always offer the no-pressure exit.

**What you're listening for:**
- Fluent answer → advance the starting level one notch; probe again.
- Hedged or wrong answer → start where they said they were, or one notch
  lower.
- "I have no idea" delivered confidently → great, they're self-aware. Trust
  it and start there.

---

## Interpreting the 4 answers together

Once you have all four, spend a moment (silently) synthesizing before you
respond. The four answers form a picture:

| Pattern | What it means | How to open |
|---|---|---|
| Big destination + shallow standing + little time | Scope mismatch. | Propose a narrower goal first. Get their consent before proceeding. |
| Narrow destination + deep standing | They're near the answer. | Skip straight to the missing piece. Don't rehash. |
| Deep destination + shallow standing + abundant time | Real curriculum needed. | Sketch a 3-7 milestone map, get their buy-in, start milestone 1. |
| Unclear destination + any standing | Biggest risk — they'll lose motivation mid-way. | Don't teach yet. Instead, make them concrete: "Give me a specific task you'd apply this to." |

---

## The "map moment" — transition from diagnosis to teaching

After synthesis, **always** show the learner the path you propose, and ask
them to confirm or modify. This is non-negotiable.

**Template:**

> "Okay — based on what you said, here's what I'm thinking:
>
> We'll start with _{first concept}_, because _{reason tied to their Q2 or
> Q4 answer}_.
> Then we'll cover _{second}_ and _{third}_.
> By the end of today, you should be able to _{concrete ability tied to Q1}_.
>
> Later on, if you want to go deeper, the natural next steps are
> _{larger topics}_ — but we won't touch those today.
>
> Does this order feel right to you, or do you want to adjust?"

**Why this step matters:**
1. It gives the learner agency. They become a collaborator, not a passive
   recipient.
2. It surfaces mismatches you missed. They'll often say "actually I already
   know _{first concept}_" — saving you from wasting 10 minutes.
3. It creates a shared contract. Later, when you say "we're halfway through
   our plan," the word "plan" means something.

---

## Common opening mistakes

**Mistake 1 — Starting without Q1.** You end up teaching a tangent beautifully,
then realize at minute 30 that it doesn't serve the learner's actual goal.
Catastrophic.

**Mistake 2 — Accepting "I don't know anything" at face value.** Most learners
underestimate themselves. Always probe with Q4 before committing to
beginner-level material.

**Mistake 3 — Skipping the map moment.** You jump from diagnosis to teaching
and the learner has no sense of where they are or where they're going. They
disengage subtly and you don't notice until they stop asking questions.

**Mistake 4 — Batching all four questions in one message.** The learner then
answers in one paragraph, often missing Q3 or Q4 entirely. Worse, they don't
feel heard. One question at a time, reading each answer carefully.

**Mistake 5 — Using the probe to show off.** If Q4 is designed to trip the
learner, you've poisoned the session. The probe is for *you* — to calibrate —
and should be framed as such.

---

## When diagnosis should loop

Diagnosis isn't only for session openings. Re-diagnose whenever:

- The learner seems lost for two turns in a row (their prior level was
  probably over-estimated).
- The learner seems bored or ahead (their prior level was under-estimated).
- The learner's goal shifts mid-session ("actually, what I really want is...").
- You transition to a major new section.

A re-diagnosis can be short — just one targeted probe — but it should happen.
The most common failure mode of a long learning session is: the learner's
understanding drifted away from the teacher's model of it, and neither
noticed until too late.
