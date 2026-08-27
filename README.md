# Elenchus

[中文](./README.zh-CN.md) | English

You're not short on opinions — you're short on options to react to. This Claude Skill builds the options for you, then asks its way to what's actually stuck.

## Why this exists

Something's been circling in your head for months with zero progress. Someone asks about it, you say "still thinking about it." They ask again two months later — still "still thinking about it." It's not that you don't care; it's that every time you approach it, the same headless, tailless question pops up in your mind. We live in an era of constant, rapid change — how long has it been since you last asked yourself "what do I actually want?" Every time an abstract decision like this comes up, you freeze, staring at it like a blank exam page. Day after day, the thing doesn't get any clearer. It just gets older.

The moment you actually start talking is usually when someone asks something concrete: "So do you want A, or do you want B?" That's it — suddenly everything clicks. Not because the other person figured it out for you, but because those two letters (A, B) pried loose something that was already in your head, just out of reach.

This isn't a willpower problem. It's a format problem. Our generation was raised on multiple-choice tests — from childhood through graduation, almost every question came with A/B/C/D already attached. Then we walked out of school and into a world that suddenly demanded "independent thinking," "open-ended thinking." The exam format switched from multiple choice to essay, and nobody ever taught us how to answer that kind of question.

Most indecision isn't a thinking-capacity problem — it's a missing-scaffolding problem. This skill builds that scaffolding for you (concrete options), then uses Socratic cross-examination to help you actually work through it and figure out what you want.

## Where this logic comes from

**The core is Socratic maieutics.** Socrates called his method "midwifery" — he never handed his interlocutors an answer, because he believed the answer was already inside them; it just hadn't been "delivered" yet. That's exactly what this skill's whole question-and-choice loop does: instead of generating a conclusion that's foreign to you, it draws out — through round after round of questions and your own choices — a thought that was already yours, just out of reach. The specific move used in the "diagnosis" step is maieutics' sharpest tool: *elenchus* (cross-examination) — questioning until a contradiction surfaces between your own answers. That moment of contradiction is where real insight actually happens. Socrates never tells you "you're wrong" — you find it yourself, inside your own answers.

**But pure open-ended Socratic questioning doesn't work here.** Plato's dialogues are open-ended and unstructured — the other party has to compose their own response from scratch. That's precisely the pain point for a lot of people: it's not that we lack ideas, it's that we can't put our own internal thoughts and feelings into words. J.P. Guilford's 1950s distinction between *convergent thinking* (narrowing many possibilities down to one — the mode standardized multiple-choice tests reward) and *divergent thinking* (generating ideas from nothing) explains why: most of us spent our education being drilled in convergent thinking and got comparatively little practice at the divergent kind. So this skill translates Socratic questioning into multiple choice — doing the same thing, in the format you're actually good at.

**Motivational Interviewing.** "You say you're torn about X, but what's actually stuck is Y" is structurally the same move as *developing discrepancy*, the core technique in Motivational Interviewing (Miller, 1983; later Miller & Rollnick). MI doesn't hand out advice — it surfaces the gap between someone's stated position and what their own answers actually reveal.
<img width="1672" height="941" alt="c8815466-903c-4150-93ca-931eb68037dd" src="https://github.com/user-attachments/assets/a40ec29e-2cda-456e-b315-ce18ddb43112" />


**When you're stuck on "I want both," the move is to step back to needs, not invent a new question.** When A and B are both still standing after being pushed hard, the problem usually isn't the options themselves — it's that the need each option quietly serves hasn't been named yet. So instead of re-asking the same position, this skill steps back and asks about the underlying needs instead (a classic move from negotiation theory — *positions vs. interests*, from *Getting to Yes*). Once the needs are named, the options usually sort themselves out. If the needs are still tied, it turns to a couple of transparent, evidence-based techniques (imagining your emotional reaction a year out, or imagining one option is permanently gone and noticing what that loss feels like) — and you always know exactly what you're answering and why. It will never design a question whose connection to your real dilemma is hidden from you, because that would violate the whole premise of this skill: every input has to come from something you knowingly said, not from an interpretation invented on your behalf. If it's a genuine toss-up even after that, it switches to criteria that don't depend on more introspection — which option is easier to reverse, or the well-documented temporal pattern in regret (people tend to regret actions more in the short term, but regret inactions more looking back over the long run — Gilovich & Medvec, 1994) — rather than manufacturing more questions to fake a clarity that isn't actually there.

This skill isn't therapy, but these frameworks are cited for a reason: they're what makes the final output something genuinely valuable — a result built entirely out of your own round-by-round questions and choices, and yours alone.

## How it works

When you're stuck on something you haven't thought through — a big life decision (a job change, whether to stay or go, sorting out values) or a concrete task you don't know how to approach (how to structure a report, where to start a project) — this skill will:

1. **Classify the problem first.** If you already have concrete options or a concrete task, it skips straight to digging in. If you're in a total vacuum and can't even name an option, it first proposes 3-4 concrete candidate directions, because having something to react to is what actually starts the thinking.
2. **Dig in two layers**, done almost entirely through Claude's built-in clickable options (`ask_user_input_v0`), never a blank text box:
   - **Fact layer** — background, audience, purpose, current state.
   - **Essence layer** — at least one full round pushing further, to find what you're actually conflicted about, uncomfortable with, or afraid of. The bar for stopping isn't "enough facts" — it's being able to fill in: "You say you're torn about ___, but what's actually stuck is ___" with something specific. If you can't fill that in with something real, it isn't deep enough yet.
3. **Delivers the result as a character card**, not a report:
   - **【LABEL】** — a punchy, MBTI-style label for the pattern, derived only from this session's answers.
   - A short paragraph with the core verdict, plus what's working, what isn't, and where you currently stand.
   - Now / next / not-yet actions.
   - A plain log of the questions asked and what you picked this round.

Every run is self-contained — no reference to past conversations or stored history, since the skill isn't assumed to be used by the same person twice.

## Usage

Trigger it naturally by describing what you're stuck on, or invoke it explicitly:

```
/elenchus I can't decide whether to take this offer
/elenchus 5    # cap the dig at 5 questions instead of the default (no fixed cap, ~2 rounds minimum, 12 max)
```

## Installing

1. Download [`elenchus.skill`](./elenchus.skill) (or just the `elenchus/SKILL.md` file).
2. In Claude, go to **Settings → Capabilities → Skills** (naming may vary by platform) and upload it.
3. Trigger it in any conversation as described above.

## Structure

```
elenchus/
└── SKILL.md      # the whole skill — trigger conditions + full behavior spec
```

## License

MIT — see [LICENSE](./LICENSE).
