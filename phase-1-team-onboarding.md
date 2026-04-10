# Phase 1 — Team Onboarding & Discovery

**Weeks 3–4 of the 14-week envelope (accelerator weeks 1–2)** · [← Phase 0](phase-0-leadership-bootcamp.md) · [README](README.md) · [Phase 2 →](phase-2-guardrails.md)

## Objective

Get the lighthouse team engineers from **first contact with the assistant** to **calibrated, productive small-task work in their own codebase**. Use the experience to surface the substrate gaps that Phase 2 will close.

## Why this is its own phase

Leaders went through the calibration workshop in Phase 0. The lighthouse team engineers have not. Asking them to *both* learn the assistant *and* tear into hooks, CI, and test backfill in the same two weeks is how you get rushed substrate work and undertrained teams. Phase 1 separates calibration from substrate so neither gets shortchanged.

The substrate work in Phase 2 is also better when it's informed by **real session experience**, not theory. Two weeks of actual sessions tell you which feedback loops are too slow, which bits of the codebase the assistant gets confused by, and which docs are missing — far better than a planning exercise.

## Who

- The three lighthouse teams (engineers, not just champions)
- The two **Agentic Engineers**, embedded across the three teams from this phase onwards. They run the compressed onboarding, pair heavily, observe sessions, and start identifying which engineers in each team have the appetite to grow into the champion role.
- The named champion per team (provisional — confirmed during this phase based on actual engagement)

## The work

### 1. Compressed onboarding workshop (early in Phase 1)

Run by the Agentic Engineers, in each lighthouse team's own repo. Roughly one day per team, hands-on throughout. Compressed version of Phase 0's leadership workshop, retuned for engineers who will actually be doing the work.

Coverage:
- Mental model: how the assistant works, context limits, tool loop, permission modes
- Plan mode and how to read a plan critically
- Steering mid-session and knowing when to abandon
- Skills, hooks, slash commands, subagents — what each is for
- Failure modes: hallucinated APIs, scope creep, uncritical agreement, over-eager edits
- Live session in their actual codebase, observed by an AE

### 2. Small, safe task work under heavy pairing

After the workshop, engineers do real work — but deliberately scoped small and safe.

- Bug fixes in well-tested areas
- Documentation drafts
- Small refactors with strong test coverage
- Test additions in places that need them
- Plan-mode-only sessions (produce a plan, review it, decide whether to execute)

The Agentic Engineers pair on these sessions intensively. The point is not throughput — it's calibration. Engineers should leave Phase 1 with a real, lived sense of "what the assistant is good at in *this* codebase" versus "where it struggles."

### 3. Skeleton context docs

Rough — not polished. Just enough to make sessions work.

- Skeleton assistant instruction file (for example `CLAUDE.md`) with project purpose, conventions, the obvious gotchas
- Glossary of domain terms the assistant keeps misunderstanding
- A first-pass architecture sketch — a paragraph and a diagram, not a treatise

These are working documents. Phase 2 polishes them based on what was actually useful.

### 4. First-pass agent-safe vs. human-led map

Drafted from real session experience, not theory. After two weeks of sessions, each team can name:

- Files / modules where the assistant performs well
- Files / modules where it consistently struggles or makes risky edits
- Areas that need stronger tests or better docs before autonomous-ish work would be safe

This map drives Phase 2's substrate priorities.

### 5. Pain point inventory for Phase 2

The most valuable Phase 1 artefact. Throughout the phase, every engineer captures friction:

- Feedback loops that are too slow (test, lint, typecheck, build)
- Missing or broken hooks
- Docs the assistant needed and didn't have
- Areas where review took disproportionate time
- Anything else that made sessions worse than they could have been

This becomes Phase 2's backlog.

### 6. Session journals

Each engineer logs **one good session and one bad session per week** with what they learned. These become some of the program's most valuable training material later.

## Working pattern

- AE runs the compressed onboarding day for each team in week 1
- After the workshop: daily team standup includes "what is the assistant doing for us today, what got in the way"
- Heavy pairing — AEs with engineers, engineers with engineers
- Mid-phase check-in (end of week 1): each team reports first impressions, surface blockers
- Cross-team demo at end of phase: each team shows one session that worked and one that didn't, plus their pain point inventory

## Stage gate to Phase 2

Advisory. Triggers were agreed in [Phase 0](phase-0-leadership-bootcamp.md#explicit-decisions-to-make-in-phase-0).

- [ ] Every lighthouse engineer has had at least one session they would call productive
- [ ] Each team has a working (rough, but used) assistant instruction file in its repo
- [ ] First-pass agent-safe vs. human-led map exists per team
- [ ] Pain point inventory captured per team — this is Phase 2's input
- [ ] Each engineer has logged at least 2 session journals (good and bad)
- [ ] Champions confirmed (or swapped if the original nominee isn't engaging)
- [ ] **End-of-phase communication** sent org-wide — first impressions, what surprised the teams, what's coming in Phase 2
- [ ] Phase 1 stop-the-line triggers reviewed in retro — none currently active, or active ones have a documented mitigation

## Marketplace contributions from this phase

- Compressed engineer onboarding workshop materials (built and refined here, reusable by future cohorts)
- Skeleton assistant instruction file templates
- Per-archetype "first day" starter packs
- Anonymised session journal extracts as training material

## Risks specific to this phase

- **Skipping the workshop because "they'll pick it up as they go".** They won't, not consistently. The workshop is short for a reason — run it.
- **Treating Phase 1 as wasted time before "real work".** Phase 1 *is* real work. The pain point inventory it produces is what makes Phase 2 effective.
- **Letting tasks drift larger than "small and safe".** Phase 1 is calibration, not feature delivery. Save the bigger stuff for Phase 3.
- **AEs doing the work for engineers.** They are pairing partners, not stand-ins. If at the end of Phase 1 only the AEs can run good sessions, the phase failed.
- **Champions that don't engage.** Better to swap a champion at end of Phase 1 than to discover the wrong person is in the role at end of Phase 3. Watch for this in week 1.
- **Polishing docs prematurely.** The skeleton docs are *meant* to be rough. Polish them in Phase 2 based on what was actually useful.
