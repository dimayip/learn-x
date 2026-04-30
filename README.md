# Learning-X

<p align="left">
  <a href="./README.md"><b>English</b></a> ·
  <a href="./README.zh-CN.md">简体中文</a>
</p>

<p align="left">
  <a href="https://github.com/bellchen/learning-x/stargazers"><img src="https://img.shields.io/github/stars/bellchen/learning-x?style=flat-square" alt="Stars"></a>
  <a href="https://github.com/bellchen/learning-x/network/members"><img src="https://img.shields.io/github/forks/bellchen/learning-x?style=flat-square" alt="Forks"></a>
  <a href="https://github.com/bellchen/learning-x/issues"><img src="https://img.shields.io/github/issues/bellchen/learning-x?style=flat-square" alt="Issues"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/github/license/bellchen/learning-x?style=flat-square" alt="License"></a>
</p>

> **A Socratic learning facilitation skill that turns "I want to learn X" into operational understanding — plus a tangible artifact you can keep.**

`learning-x` is a subject-agnostic coaching framework for AI assistants (and humans who want to run better learning sessions). Instead of lecturing, it diagnoses where the learner actually stands, introduces concepts one at a time, uses structured A/B/C/D prompts, locks in progress every few turns, challenges correct answers with devil's-advocate follow-ups, and always ends with something the learner has produced.

It works whether X is a programming language, a math concept, a design pattern, a tool, a framework, a domain, or a soft skill.

---

## Why this skill exists

Most learning failures come from **being told too much, too fast**, before the learner has grounded the new concept in their own mental model. Traditional "just explain it" interactions leave the learner nodding along and forgetting everything within 48 hours.

`learning-x` is designed around a single shift:

> **Learner steers (making sense). Coach executes (asking, not telling).**

Every rule, question template, and workflow step in the skill is there to keep the learner's mind **active rather than passive**.

---

## When to use it

Trigger this skill whenever a user says things like:

- "教我 X" / "帮我学 Y" / "我想搞懂 Z" / "带我入门 ..."
- "help me learn / understand / get good at ..."
- "can you coach me through ...?"
- "I've been trying to wrap my head around ..."

It shines especially when:

- the topic is complex or multi-layered,
- the learner's starting point is unclear,
- or past attempts to "just read the docs" haven't stuck.

It is **not** the right skill for pure fact lookups ("what year was Python released?") or for doing the work *for* the learner (write my code, debug my bug). Those should route to other skills.

---

## Core philosophy — the 4 active layers

Every turn of dialogue should activate all four layers simultaneously. A turn that only asks questions (L3) without anchoring to the goal (L1) or producing anything (L4) causes the session to drift.

| Layer | Role | Example in a turn |
|-------|------|-------------------|
| **L1 · Anchor** | Keep sight of the goal + a reference exemplar | *"Remember — you said you want to build X by next month. This concept serves that."* |
| **L2 · Discipline** | Enforce tempo: diagnose-first, one-concept, lock-ins, devil's advocate | *"Before I explain — what do you *think* it does?"* |
| **L3 · Tactics** | Socratic moves: prime, hypothesize, verify, apply, reflect, challenge | *"Pick A / B / C — which matches your intuition?"* |
| **L4 · Artifact** | Produce something tangible every few turns | *"Now write a 5-line version in your own words."* |

---

## The 5 ironclad rules

1. **Diagnose before teaching.** Open with questions about *purpose*, *prior impression*, and *adjacent knowledge*. Never open with content.
2. **One new concept per turn.** Queue additional concepts instead of stacking. Pair every concept with a <3-minute micro-task.
3. **Prefer structured choices over open questions.** Replace "what would you use?" with "A / B / C — which, and why?". Always leave room for the learner to pick D.
4. **Lock-in review every ~3 turns.** Explicitly recap what's been nailed and what's next. Specific and short beats vague.
5. **Devil's advocate after correct answers.** Correctness is cheap; depth is expensive. Push on one assumption before moving on.

Full reasoning for each rule lives in [`SKILL.md`](./SKILL.md).

---

## The 4-phase workflow

```
Phase 1 — Onboarding           Phase 2 — Path proposal
(diagnose, don't teach)  ──►  (3–7 milestones, learner confirms)
                                         │
                                         ▼
Phase 4 — Artifact           Phase 3 — Milestone loop
(demo / cheat sheet /   ◄──  (prime → hypothesize → reveal → verify
 mindmap / flashcards...)     → challenge; lock-in every ~3 turns)
```

**Phase 1 — Onboarding.** Ask the 3–4 diagnostic questions from [`references/diagnose-playbook.md`](./references/diagnose-playbook.md). Do not teach anything yet, even if the learner's prior understanding is wrong.

**Phase 2 — Path proposal.** Based on the diagnosis, propose 3–7 ordered milestones and invite the learner to confirm or swap. This builds co-ownership of the plan.

**Phase 3 — Milestone loop.** For each milestone, run the 6-move micro-loop: *prime → hypothesize → reveal + micro-task → verify → challenge*, with a lock-in review roughly every 3 turns.

**Phase 4 — Artifact.** Close every session with something the learner produced: a working demo, a cheat sheet in their own words, a mindmap, reflection notes, flashcards, or a teach-back. A session that ends without an artifact mostly evaporates.

---

## Repository layout

```
learning-x/
├── SKILL.md                               # The full skill spec — philosophy, rules, workflow
├── README.md                              # (this file) overview for humans browsing the repo
├── README.zh-CN.md                        # Chinese translation (auto-generated, see below)
└── references/
    ├── diagnose-playbook.md               # Opening moves: question scripts by topic type
    ├── question-templates.md              # 6 Socratic families (prime / hypothesize / verify / apply / reflect / challenge)
    └── session-patterns.md                # Adapted workflows for concept / tool / skill / domain / language learning
```

- **[`SKILL.md`](./SKILL.md)** — Canonical spec. This is the file an AI agent actually loads to operate. Start here if you want to use or port the skill.
- **[`references/diagnose-playbook.md`](./references/diagnose-playbook.md)** — The first 3–10 minutes of any session. Scripted openings and signals to listen for.
- **[`references/question-templates.md`](./references/question-templates.md)** — A reusable library of phrasings for each Socratic move. Load when you need variety or want to avoid repetitive wording.
- **[`references/session-patterns.md`](./references/session-patterns.md)** — How to shape a session differently for concept learning vs. tool onboarding vs. skill building vs. domain knowledge vs. language acquisition.

---

## Anti-patterns

The skill spec lists these explicitly because they're the most common ways a well-intentioned session still fails:

- **Wall-of-text explanations**, even when the learner begs "just tell me".
- **Empty praise** ("you're so smart!") that trains approval-seeking instead of understanding.
- **Ignoring what the learner said they wanted** and going off on tangential foundations.
- **One-size-fits-all pacing** that doesn't flex for a beginner vs. someone experienced in an adjacent field.
- **No artifact at the end.**

---

## Calibration knobs

The framework adapts to the learner, not the other way around:

| Situation | Adjustment |
|-----------|-----------|
| Complete beginner | More priming, smaller bites, more restatement, early artifacts |
| Experienced in adjacent field | Skip basics, lean into challenge questions, faster pacing |
| Learner says "just tell me" | Negotiate: "after one quick guess, deal?" |
| Learner goes silent | Drop one rung in abstraction or give a concrete example |
| Learner argues with your answer | Celebrate it — engage seriously; they may be right |
| Time-boxed session | Compress milestones; reserve the last 10% for the artifact |

---

## How to use this skill with an AI agent

If your agent platform supports skill loading (CodeBuddy, Claude skills, or similar):

1. Place this directory under the platform's skills folder (e.g. `.codebuddy/skills/learning-x/`).
2. The agent loads `SKILL.md` when the user's request matches the skill's description (learning, coaching, "教我 X", etc.).
3. Reference files under `references/` are loaded **on demand** — the agent pulls them only when it needs the detailed playbook, question phrasings, or pattern guidance for the current moment in the session.

If you're using it as a human facilitator: read `SKILL.md` once to internalize the 5 rules, then keep the three reference files open during sessions for quick lookup.

---

## Design principles (for anyone forking or adapting this skill)

- **Subject-agnostic first.** Everything in the core spec must work for any X. Topic-specific tuning lives in `references/session-patterns.md`, not in the main rules.
- **Rules over tips.** The 5 rules are written to be *hard to wiggle out of*. Soft suggestions get ignored under pressure; ironclad rules survive.
- **References load on demand.** `SKILL.md` stays lean so the agent can hold it in context cheaply; deeper material is opt-in per turn.
- **Artifact or it didn't happen.** The framework optimizes for *retention*, and the single highest-leverage retention move is producing something externalizable.

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=bellchen/learning-x&type=Date)](https://star-history.com/#bellchen/learning-x&Date)

---

## License

Unless noted otherwise in individual files, content in this repository is released under the MIT License. See [`LICENSE`](./LICENSE) if present.

---

## Credits

Authored and maintained by [@bellchen](https://github.com/bellchen). The framework synthesizes ideas from Socratic teaching, cognitive load theory, retrieval practice, and the "harness engineering" pattern of separating *steering* from *execution* — but distilled into rules that are cheap enough to actually follow in a real session.
