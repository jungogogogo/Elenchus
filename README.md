# decision-untangle

A Claude Skill for people who need concrete options before they can think — and then need someone to dig past the surface-level answer instead of just handing back a coin flip.

## What it does

When you're stuck on something you "haven't thought through" — a big life decision (job, relocation, values trade-offs) or a smaller task you don't know how to approach (how to frame a report, where to start on a project) — this skill:

1. **Classifies the problem.** If you already have concrete options or a concrete task, it skips straight to digging. If you're in a total vacuum with no options in sight, it proposes 3–4 concrete candidate directions first, because having something concrete to react to is what actually starts the thinking.
2. **Digs in two layers**, entirely through clickable multiple-choice questions (via `ask_user_input_v0`), never a blank text box:
   - **Fact layer** — background, audience, purpose, current state.
   - **Essence layer** — at least one full round pushing past the fact layer to find what you're *actually* conflicted about, uncomfortable with, or afraid of. The bar for stopping isn't "enough facts" — it's being able to fill in: *"You say you're torn about ___, but what's actually stuck is ___"* with something specific, not a generic platitude.
3. **Delivers the result as a character card**, not a report:
   - **【LABEL】** — a punchy, MBTI-style label for the pattern, derived only from this session's answers.
   - A short paragraph with the core verdict plus what's working, what isn't, and where you currently stand.
   - Now / next / not-yet actions.
   - A plain log of the questions asked and what you picked this round.

Every run is self-contained — no reference to past conversations or stored history, since the skill isn't assumed to be used by the same person twice.

## Usage

Trigger it naturally by describing what you're stuck on, or invoke it explicitly:

```
/decision-untangle I can't decide whether to take this offer
/decision-untangle 5    # cap the dig at 5 questions instead of the default (no fixed cap, ~2 rounds minimum, 12 max)
```

## Installing

1. Download [`decision-untangle.skill`](./decision-untangle.skill) (or just the `decision-untangle/SKILL.md` file).
2. In Claude, go to **Settings → Capabilities → Skills** (naming may vary by platform) and upload it.
3. Trigger it in any conversation as described above.

## Structure

```
decision-untangle/
└── SKILL.md      # the whole skill — trigger conditions + full behavior spec
```

## License

MIT — see [LICENSE](./LICENSE).
