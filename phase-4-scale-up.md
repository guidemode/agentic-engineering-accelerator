# Phase 4 — Workflow Scale-Up

**Weeks 9–10 of the 14-week envelope (accelerator weeks 7–8)** · [← Phase 3](phase-3-first-features.md) · [README](README.md) · [Phase 5 →](phase-5-full-agentic.md)

## Objective

Two things at once:

1. **Test transferability at the individual level.** Add 1–2 new engineers to each lighthouse team. If they can reach productive work in a week using the marketplace, the workshop materials, and a champion — *without the Agentic Engineers in the onboarding loop* — then the patterns are transferable to humans, not just memorised by the original cohort.
2. **Introduce the next layer of capabilities** — subagents, parallel work, custom commands, spec-driven workflows.

## Premise

The pilot stays bounded. We do **not** bring new teams on during the program — that's a scaling decision, not a pilot decision, and it gets made *after* the program based on the recommendation from Phase 6.

What we *do* test is whether a new individual can be onboarded into a working agentic team using the assets the pilot produced. That's a real transferability signal without expanding scope.

Phase 3 proved supervised features work. Phase 4 is where we find out whether the patterns survive contact with someone who wasn't there from day one, and whether richer agentic workflows pay off in this org's environment.

## Who

- The three lighthouse teams continue
- **1–2 new engineers added to each lighthouse team** for the remainder of the pilot — joined to the team, not rotated through. They go through a compressed onboarding led by the team's champion, using existing assets (marketplace, assistant instruction files, workshop materials, session journals from Phases 1–3).
- The two **Agentic Engineers** are still embedded with the original teams but **deliberately stay out of the onboarding loop for the new joiners**. The new joiners learn from the champion and the assets, not from the AEs. This is the test: if patterns only transfer with an AE in the room, they're not really transferable. The AEs continue pairing with the original team members and supporting the new capabilities work below.
- **Optional fourth track (legacy rewrite)** starts here if go decision was made at end of Phase 3

## New capabilities introduced

### Subagents for context isolation
Split research from implementation. A research subagent reads the codebase and reports findings; the main session implements. Keeps the main context window clean and the implementation focused.

### Background tasks
Long-running jobs that don't block the engineer's session.

### Parallel agent runs
On independent slices of work — e.g. running the same refactor across multiple files in parallel, or exploring multiple implementation strategies simultaneously.

### Custom slash commands per project
Codify the "how we do things here" patterns from Phase 3 into commands that any engineer (or agent) can invoke.

### Spec-driven workflows
Write a clear spec, have the assistant implement against it, and validate against the spec. Closer to autonomous than Phase 3's supervised model.

## Optional: legacy rewrite track begins

If the go decision was made at end of Phase 3:

- Pick **one bounded module** of a legacy system. Bounded means: clear inputs, clear outputs, reasonable test coverage (or ability to backfill it quickly).
- Use bounded autonomous loops with **strict specs + tests as the fitness function**.
- Expect failures. The point is to learn what works in *this* environment, not to deliver a rewrite in two weeks.
- Document everything — failed attempts are as valuable as successes here.
- **Hard kill switch**: if the loop is burning resources without progress for more than a day, stop and reflect. Don't let a loop run forever just because it's running.

## FinOps — first pass

Phase 4 is where token spend and infrastructure cost start to matter. Until now teams have been running supervised sessions; subagents, parallelism, and (optionally) autonomous loops change the cost shape meaningfully.

**Activities:**
- Capture **per-engineer and per-team token usage** for Phase 4 — this becomes the FinOps baseline the same way Phase 0 metrics became the throughput baseline
- Tag spend by workflow type (interactive sessions vs. subagent fan-out vs. loops) so the contribution of each pattern is visible
- Note which capabilities are cost-efficient and which aren't — multi-agent fan-out in particular needs scrutiny
- Light forecast: extrapolate Phase 4 weekly spend to "what would this look like if every team in the org ran this way?" Even a rough number changes the conversation in Phase 6.

The point is not to optimise yet. The point is to *see* the cost so Phase 5 can make informed choices and Phase 6 can give leadership a credible forecast.

## Working pattern

- Lighthouse champions take the lead on onboarding new team members — explicit time allocated, not squeezed in around their day jobs
- New members follow a compressed Phase 1 + Phase 2 + Phase 3 path, using only existing assets and the team's champion
- Agentic Engineers deliberately stay out of the onboarding loop — the experience should reflect what self-serve adoption would look like
- Marketplace pull requests pick up sharply this phase as patterns get codified
- Cross-team demo expands to include new members' first wins and stumbles

## Stage gate to Phase 5

Advisory. Targets and triggers were agreed in [Phase 0](phase-0-leadership-bootcamp.md#explicit-decisions-to-make-in-phase-0).

- [ ] Newly added engineers have reached productive work in their first week using only existing assets and their champion
- [ ] Marketplace assets have been *consumed* by an engineer who didn't author them (evidence of reuse, not just contribution)
- [ ] Each lighthouse team is running at least one workflow that uses subagents, parallel work, or spec-driven patterns — and can articulate why it's worth it
- [ ] If legacy rewrite track started: either a working module exists, OR a documented "why this didn't work yet" exists. Both are acceptable.
- [ ] Confidence + happiness metrics are within the agreed band
- [ ] FinOps baseline captured: per-engineer and per-team token spend, broken down by workflow type
- [ ] Phase 4 stop-the-line triggers reviewed in retro — none currently active, or active ones have a documented mitigation
- [ ] **End-of-phase communication** sent org-wide — onboarding new engineers, FinOps baseline, what new capabilities are paying off
- [ ] **Mid-program checkpoint** delivered to leadership and adjacent teams — broader update covering progress and the cost picture, so the FinOps conversation starts before Phase 6

## Marketplace contributions from this phase

- Subagent definitions for research, code review, test generation
- Custom slash commands codifying the org's workflows
- Spec templates that work well as assistant inputs
- Onboarding playbook for new teams (built from the actual experience of onboarding teams in this phase)
- If applicable: autonomous loop scaffolding and lessons learned

## Risks specific to this phase

- **Champions become bottlenecks.** They have to do their own work *and* onboard new team members. Allocate explicit time for the latter.
- **New members copy patterns without understanding.** Lighthouse practices may not all fit a new joiner's mental model. Encourage adaptation and open Q&A sessions.
- **Subagents and parallelism added because they are novel, not because they help.** Each new capability needs to justify itself with a concrete win, not "we tried it."
- **Legacy rewrite eats the program.** It's the most exciting track and the most likely to consume disproportionate attention *and* budget. Time-box it and watch its token spend.
- **Marketplace becomes a dump.** Curation matters more than contribution. Owner from Phase 0 should be active here.
- **FinOps treated as a Phase 6 problem.** By Phase 6 the conversation needs numbers. If you skip the baseline here, you'll be guessing.
