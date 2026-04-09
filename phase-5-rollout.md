# Phase 5 - Graduation and Recommendation

**Weeks 11–12** · [← Phase 4](phase-4-full-agentic.md) · [README](README.md)

## Objective

Produce a clear, defensible **recommendation to leadership** about whether and how to scale the program beyond the pilot. Close the loop on security, compliance, and legal. Be honest about what graduates, what's still experimental, and what should be killed.

## Premise

The pilot was deliberately bounded — same three lighthouse teams from Phase 1 through Phase 4, with new individuals added in Phase 3 to test transferability at the human level. Phase 5 is **not** a rollout. The decision to roll out (or not) is the *output* of Phase 5, not an assumption built into it.

The question Phase 5 answers: given everything we learned in Weeks 1–10, what should the org do next, and what would it cost?

## Who

- The three lighthouse teams (including the engineers added in Phase 3)
- The two **Agentic Engineers**, now leading on graduation deliverables (recommendation, guide, playbooks) alongside the comms owner. Champions remain the primary operators of day-to-day work; AEs are writing up outcomes, not taking control back.
- Engineering leadership (active again — they were quieter through Phases 1–4)
- Security, compliance, legal stakeholders (formal review)
- Finance / FinOps stakeholder (reviewing the cost forecast and steady-state spend assumptions)

## The work

### Internal "agentic engineering" guide

**Built from Phase 0–4 artefacts, not written from scratch.** If a section can't be sourced from real work in the pilot, it doesn't belong in the guide. The guide is:

- How we use AI coding assistants in this org
- Per-archetype playbooks
- Marketplace pointers
- Supervision patterns
- Autonomous flow guidelines (kill switches, budgets, audit trails, ownership)
- "When not to use the assistant" — equally important

### Scale readiness pack

Consolidate enablement outputs into a package that can be reused by teams outside the pilot:

- Assistant instruction templates and project setup guidance
- Integration patterns (tooling, hooks, environment setup)
- Measurement framework (throughput, quality, confidence, cost)
- Governance and working-agreement templates

### Marketplace v1.0

- Versioned cut
- Named owners per asset (or per category)
- Documented contribution process
- Documented deprecation process — assets that don't get reused get retired
- A health dashboard showing reuse, not just contribution count

### Demos and brown-bags

- Public demo to the broader engineering org
- Per-archetype deep-dives for teams thinking about adoption
- Q&A sessions with lighthouse champions

### Final org-wide communication

The closing piece of the communication track that ran through every phase. Owned by the comms owner named in Phase 0.

This is **not** the recommendation document — that goes to leadership. This is the public-facing version, written for engineers in teams that didn't participate in the pilot.

Coverage:
- What the program set out to do
- What actually happened — wins, learnings, things that didn't work
- The honest read on cost, confidence, and quality
- What this means for the rest of the org (whatever the recommendation turns out to be — including "not yet" or "no")
- Where to find the marketplace, the playbooks, and the people who can help
- What happens next, with timing if known

The aim is to leave the org *oriented*, not hyped or skeptical. Honest summaries are more credible than victory laps and they age better.

### Per-archetype playbooks

A starter pack for any team that wants to adopt:

- "If you're a greenfield team, here's your starter pack"
- "If you're an active project, here's how to start without disrupting current work"
- "If you're legacy maintenance, here's where the wins are"
- "If you're considering a legacy rewrite, here's what we learned (and whether you should attempt it)"

### Security, compliance, legal review

Formal review of everything the pilot did. Coverage:

- **Code provenance** — what's in PRs and where it came from
- **Data egress** — what left the building, where it went
- **Autonomous-action audit trails** — can we reconstruct what flows did and why
- **Production-touching flows** — what touched prod, with what authority
- **Secrets and credential handling** — clean throughout
- **Any third-party integrations** introduced during the pilot

Output: a written sign-off (or a list of remediations required before any broader scaling).

### FinOps review and forecast

Built on the baseline captured in Phase 3 and the cost-per-outcome data from Phase 4.

- **Pilot spend** — total token cost across the 12-week accelerator, broken down by team, phase, and workflow type (interactive sessions vs. subagents vs. autonomous flows vs. legacy rewrite if applicable)
- **Cost per useful outcome** — per archetype, with caveats about what counts as "useful"
- **Steady-state forecast for the lighthouse teams** — if these teams continue operating as they did in Phase 4, what does the next quarter cost
- **Scale forecast** — if every team in the org adopted the same patterns, what would the bill look like, and how confident are we in that number
- **Cost levers identified** — which patterns are cost-efficient, which aren't, where the biggest reductions are available
- **Recommendation on cost guardrails** — org-wide budget caps, per-team allowances, alerting thresholds, FinOps ownership going forward

Reviewed jointly with finance / FinOps stakeholders. Their sign-off goes alongside the security/compliance/legal sign-off.

### Final retro

Honest, structured. Cover:

- What worked
- What didn't
- What we'd do differently
- Which marketplace assets graduate, which get archived, which get killed
- Which patterns are ready for broader rollout, which are still experimental
- Which teams are ready to operate without program support, which need more time

### Steady-state operating model recommendation

A written recommendation to leadership covering **three** decisions:

**1. Should we scale beyond the pilot at all?**
- Yes, fully — patterns are ready, cost is acceptable, evidence is strong
- Yes, with caveats — scale into specific archetypes, hold others back
- Not yet — extend the pilot or run a second cohort to address specific gaps
- No — patterns aren't paying off in this environment, document the learnings, stop here

All four are legitimate outcomes. The recommendation should follow the evidence.

**2. If yes, what operating model?**
- **Centre of excellence** — small central team curating marketplace, running onboarding cohorts, supporting adopters
- **Embedded champions** — no central team; champions live in product teams and meet periodically
- **Both** — central curation + embedded champions
- **Neither** — patterns are documented and self-serve from here

**3. What is the budget envelope?**
- Forecast spend at the recommended scale (from the FinOps review)
- Required cost guardrails and FinOps ownership
- Trigger points for re-evaluation (e.g. if spend exceeds X, or if cost-per-outcome regresses)

The recommendation should be defensible from the pilot's evidence — including the cost numbers. Vague recommendations get rejected by anyone who has to sign the bill.

## Stage gate to "done"

Advisory — but this is the program's final gate, so each item should be genuinely satisfied, not waved through. Triggers were agreed in [Phase 0](phase-0-leadership-bootcamp.md#explicit-decisions-to-make-in-phase-0).

- [ ] Engineers added in Phase 3 have given honest feedback on the onboarding experience — written up as the transferability evidence
- [ ] Marketplace v1.0 has named owners and a contribution process
- [ ] Security / compliance / legal review completed with written sign-off (or remediation list)
- [ ] FinOps review completed with pilot spend, cost-per-outcome, and steady-state forecast
- [ ] Per-archetype playbooks exist
- [ ] Internal guide published
- [ ] Final retro completed and documented
- [ ] Steady-state operating model **recommendation** delivered to leadership, covering: scale yes/no, operating model, budget envelope
- [ ] Metrics show direction-of-travel against Phase 0 baseline (positive or negative — both are findings)
- [ ] Phase 5 stop-the-line triggers reviewed in retro — none currently active, or active ones are explicitly flagged in the recommendation

## Marketplace contributions from this phase

- The guide itself
- Per-archetype playbooks
- Onboarding curriculum for the next cohort (whatever shape that takes)
- Retrospective documents — both successes and failures
- Decision record for the steady-state model

## Risks specific to this phase

- **Victory lap before evidence.** Pressure to declare success regardless of results. Resist. The most valuable thing the program can deliver is an honest assessment, not a positive one.
- **Recommendation written to please leadership.** If the right call is "not yet" or "no", that has to be sayable.
- **Marketplace handed off to no one.** Ownership decided in Phase 0 must still be valid here. If the original owner has moved on, name a new one *before* Phase 5 ends.
- **Security/compliance/legal review deferred "to next quarter".** No. It happens in Phase 5 or the program isn't done.
- **FinOps review skipped or under-evidenced.** Anyone who has to sign the bill will reject a recommendation without credible cost numbers. Better to present rough numbers transparently than precise numbers nobody trusts.
- **Lighthouse teams left with unsustainable load.** They have been doing extra work for 12 weeks. Make sure the steady-state model does not assume that burden continues indefinitely.
- **Confusing the recommendation with a rollout.** Phase 5 produces a recommendation. The actual rollout (if any) starts after, with its own scope, plan, and budget — not as an automatic extension of the pilot.
