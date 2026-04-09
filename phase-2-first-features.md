# Phase 2 — First Supervised Features

**Weeks 5–6** · [← Phase 1](phase-1-guardrails.md) · [README](README.md) · [Phase 3 →](phase-3-scale-up.md)

## Objective

Ship **real features** through the assistant with strong human supervision. Build the team's intuition for what "good supervision" looks like in practice on their actual codebase.

## Premise

Smallest possible *real* features. Not toy. Not throwaway. But scoped so a single human reviewer can hold the whole diff in their head in one sitting.

The point is not to maximise output. The point is to discover where the agent thrives, where it struggles, and what supervision pattern fits each archetype.

## Who

The same three lighthouse teams, with the two **Agentic Engineers** still embedded across them. In Phase 2 the AEs shift slightly — less time leading sessions themselves, more time pairing on tricky reviews, coaching champions, and surfacing patterns into the marketplace. They are still hands-on; they are *not* yet stepping back. No new teams yet — that's Phase 3.

## Modes by archetype

### Greenfield
- Assistant drafts modules with tests
- Human reviews at plan stage and at PR
- Paired sessions encouraged for the first week
- Higher tolerance for assistant-led structural choices since there's no legacy weight

### Active project
- Assistant implements well-specified tickets
- **Plan mode is mandatory** for any non-trivial change
- Human review at plan-mode and at PR
- Existing review discipline applies - no shortcuts because "the assistant wrote it"

### Legacy maintenance
- Bug triage, reproductions, and minimal fixes
- Documentation backfill
- Test backfill against existing behaviour
- **Any structural change requires human approval before the assistant proceeds**

### Legacy rewrite (optional fourth track)
- **Not yet.** This track does not start in Phase 2.
- Decision on whether to start it at all is made at the end of this phase.

## Working pattern

- Plan mode is mandatory for any change beyond a one-line fix
- One human reviewer per PR. No rubber-stamping. Reviewer initials on the PR mean "I understand this diff."
- Session journals continue: one good, one bad, per engineer per week
- Cross-team demo at end of each week — each team shows one PR they're proud of and one session that didn't work
- Champions meet mid-week to compare notes and spot cross-team patterns

## Decision: legacy rewrite track

At the **end of Phase 2**, the Agentic Engineers and leadership decide jointly whether to start the optional fourth track in Phase 3.

**Go criteria:**
- Phases 0–2 have gone roughly to plan
- A suitable legacy module exists (bounded, well-defined behaviour, reasonable test coverage or ability to add it)
- A team has bandwidth and appetite
- There's a clear hypothesis about which patterns (bounded autonomous loops, spec-driven, evaluation-driven) we are testing

**No-go is fine.** Skipping this track is not a failure — it's a deliberate scope decision to keep the program focused.

## Stage gate to Phase 3

Advisory. Targets and triggers were agreed in [Phase 0](phase-0-leadership-bootcamp.md#explicit-decisions-to-make-in-phase-0).

- [ ] Each team has hit (or meaningfully approached) its Phase 0–agreed PR target
- [ ] Defect escape rate is within the agreed band relative to the Phase 0 baseline
- [ ] Lead time on assistant-touched PRs is being measured (direction-of-travel, not absolute target)
- [ ] At least one "I would not have done it that way and I'm glad I did" moment per team (qualitative — captured in retro)
- [ ] Each team has identified the kinds of tasks where the assistant works best in their codebase
- [ ] Decision made on legacy rewrite track for Phase 3
- [ ] Phase 2 stop-the-line triggers reviewed in retro — none currently active, or active ones have a documented mitigation
- [ ] **End-of-phase communication** sent org-wide — first real feature work, honest read on what's working, the legacy rewrite go/no-go decision and why

The phase-specific stop-the-line conditions for Phase 2 live in the Phase 0 explicit-decisions section. Watch them weekly; raise them in retro.

## Marketplace contributions from this phase

- Ticket-to-plan skills (read a Jira/Linear/GitHub issue, produce a plan)
- PR description generators that fit the org's style
- Archetype-specific subagents (e.g. "bug repro agent" for legacy maintenance)
- Review checklists for assistant-touched PRs
- Curated "good session" recordings or transcripts as training material

## Risks specific to this phase

- **The features are too small to be representative.** Don't pick PRs so trivial that they teach nothing. The smallest *real* feature, not the smallest possible feature.
- **Reviewers default to trust.** Once a few assistant PRs land cleanly, review discipline slips. Catch this in retros and reset hard.
- **Scope creep mid-session.** The assistant starts "improving" adjacent code. Plan mode + tight reviews catch most of this.
- **Premature claims of victory.** Two weeks of supervised features is not proof of long-term value. Resist the urge to tell the rest of the org "it works" until Phase 4.
- **Engineers feel demoted to reviewers.** Watch for this in the happiness metric. Pairing and rotation help.
