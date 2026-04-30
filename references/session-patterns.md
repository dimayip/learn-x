# Session Patterns — Adapting the Framework to Different Kinds of Learning

The 5 disciplines and 6 question families work across all learning, but the
*shape of a session* should adjust to what's being learned. A session teaching
someone a new programming language feels very different from one teaching
them to think statistically, even if both use the same underlying framework.

This file describes 5 common learning archetypes and how to adapt the
framework for each. Load this file when you've diagnosed the learner and you
need to decide what kind of session to run.

Match by the *dominant* flavor of the learning goal — many real sessions mix
types, but one usually leads.

---

## Pattern 1 · Concept-heavy learning (understanding *why*)

**Examples:** statistical inference, economic reasoning, design principles,
distributed-systems consistency models, music theory, recursion.

**Characteristic:** the learner already has vocabulary or can memorize it
easily; the hard part is building the *mental model* that makes the vocabulary
mean something.

**Session shape:**
1. Diagnose with a bias toward Q4 (the micro-probe). Definitions are cheap;
   probes reveal whether the model is really there.
2. Organize around **invariants and surprises** rather than a list of terms.
   Start from a simple case the learner can reason about, then introduce one
   perturbation at a time and ask them to predict what changes.
3. Heavy use of Hypothesize and Challenge families — concept understanding
   shows up most clearly in predictions and defenses.
4. The "micro-task" per turn is usually a *prediction* or an *explanation*,
   not a build step.

**Product at the end:** often a hand-drawn diagram, a worked example with
annotations, or a short written explanation in the learner's own words. Ask
them to produce it — concept learning that isn't externalized doesn't stick.

**Pacing warning:** concept sessions tempt you to "just explain one more
thing" because you haven't built anything concrete. Resist. Stop at natural
frontiers and do a Reflect turn even when it feels anticlimactic.

---

## Pattern 2 · Skill-heavy learning (building *how*)

**Examples:** learning a programming language, touch typing, a musical
instrument, a framework like React, using a command-line tool like Git.

**Characteristic:** the learner needs reps. Understanding is necessary but
not sufficient — muscle memory and pattern recognition only come from doing.

**Session shape:**
1. Diagnose lightly — for skills, the best diagnosis is "show me what you
   can already do." Give them a small task at the level you think they're at
   and watch them do it.
2. Each turn should include a **micro-build** — something they type, run,
   try. The ratio should be roughly 70% learner doing / 30% you explaining.
3. Sequence the builds so each one introduces exactly one new idea. Resist
   bundling "two tiny things" — they're never as tiny as they look.
4. Verify happens in the doing, not in the talking. If they can do it, they
   understand it enough for now.

**Product at the end:** a working artifact — a running program, a completed
piece of music, a diff they can push. The artifact *is* the evidence.

**Pacing warning:** skill sessions tempt you to let the learner keep doing
without stepping back. Every ~3 builds, force a Reflect turn — "what pattern
have you seen repeating?" — or they'll accumulate tactics without extracting
principles.

---

## Pattern 3 · Tool or system learning (navigating *what exists*)

**Examples:** a specific codebase, a product like Figma or Blender, an API,
a company's internal platform.

**Characteristic:** the learner needs a **map** more than a theory. The
system has specific affordances, edges, and gotchas that can't be derived
from first principles — they must be encountered.

**Session shape:**
1. Diagnose heavily around **their actual task**. Tool learning without a
   task becomes a tour, and tours don't stick. If they don't have a task,
   co-invent a small realistic one before starting.
2. Teach just-in-time, by following the task. When the task hits a concept,
   introduce it; when it doesn't, don't.
3. Mark the **terra incognita** explicitly — "the system has these 5 major
   areas; today we'll touch 2 of them; the other 3 are worth knowing exist
   but we won't go there." This anchors them in the larger geography.
4. Challenge family becomes "what would happen if" probes into the tool's
   behavior, not against the learner's reasoning.

**Product at the end:** the task, completed, with a short written
"gotchas I noticed" list. The list is the durable output; the completed task
is the evidence.

**Pacing warning:** tool sessions tempt you to "give the grand tour."
Grand tours feel impressive and teach nothing. Stay ruthlessly tied to the
task. Trust that the learner will discover the rest when they need it.

---

## Pattern 4 · Problem-solving learning (developing *judgment*)

**Examples:** algorithm design, debugging, architectural decisions, medical
diagnosis, chess tactics, UX design critiques.

**Characteristic:** there's no single right answer. The learner needs to
develop a **process** for approaching open-ended problems and making defensible
choices among imperfect alternatives.

**Session shape:**
1. Diagnose by showing them an example problem and asking them to narrate
   their approach. The approach is the data — the final answer is almost
   irrelevant.
2. Structure around **cases** — 3-5 progressively subtle scenarios. Each
   case exercises a different axis of the judgment you're building.
3. Heavy use of Challenge family. The test of judgment is whether it
   survives probing. Expect to play devil's advocate repeatedly.
4. The Reflect family is critical here — after each case, ask "what heuristic
   did you just use, whether you named it or not?" Surfacing tacit heuristics
   is the core deliverable.

**Product at the end:** a written "decision heuristics" list — the rules of
thumb the learner now carries. 3-7 items, each with a one-line rationale and
a boundary condition (where it stops applying).

**Pacing warning:** judgment sessions tempt you to hand out rules. Don't.
Rules given are forgotten; rules derived are kept. Make the learner articulate
every heuristic themselves, even if you have to wait in awkward silence.

---

## Pattern 5 · Mindset or habit learning (changing *how they operate*)

**Examples:** learning to think statistically, to write clearly, to code
defensively, to give feedback well, to plan before coding, to ask better
questions.

**Characteristic:** the learner intellectually agrees with the advice before
the session starts. The gap is between knowing and doing. Sessions here are
less about information and more about **interrupting old patterns**.

**Session shape:**
1. Diagnose by finding a recent real example where they did the *old* way.
   "Tell me about the last time you _{old behavior}_ — what happened?"
   This is the anchor for the session.
2. Structure around **pattern interrupts**: show the old pattern, show the
   new pattern, have the learner practice the new one on the anchor example.
   Then give them one more example to apply it to.
3. Almost no new vocabulary or concepts — the learner already has them. The
   session is about *installing reflexes*.
4. Reflect family is the main tool. "What tripped you into the old pattern
   just now?" "What would have caught you earlier?"

**Product at the end:** a short, personal **checklist or trigger list** the
learner writes for themselves — 3-5 items max. Not generic advice; specific
cues tied to their own situations.

**Pacing warning:** mindset sessions tempt you to lecture about the
importance of the new pattern. Don't. They already agree. The work is
entirely in the practice turns.

---

## When a session mixes types

Most real sessions blend at least two. A few common combos:

| Combo | Lead type | Handling |
|---|---|---|
| Concept + Skill (e.g., "learn React hooks") | Skill | Teach concept just-in-time as the builds demand it. Don't front-load theory. |
| Tool + Skill (e.g., "learn to navigate our codebase") | Tool | Use real tasks; the skill comes from repeated navigation. |
| Concept + Judgment (e.g., "learn when to use microservices") | Judgment | Concepts are mostly review; spend time on cases. |
| Skill + Mindset (e.g., "learn test-driven development") | Mindset | The skill is easy; the hard part is the pattern interrupt before writing code. |

When in doubt: pick the one that would hurt most if neglected, and let it
lead. You can always fold the other in opportunistically.

---

## Diagnostic cues for picking a pattern

If the learner said... | They probably need...
---|---
"I don't really *get* why X works" | Concept-heavy
"I can read it but I can't write it" | Skill-heavy
"I need to use X at work next week" | Tool/system
"I keep picking the wrong approach" | Judgment
"I know what I should do, I just don't do it" | Mindset

These aren't exclusive — listen for which *feeling* is strongest in their
description, and let it shape the session even if other elements exist.
