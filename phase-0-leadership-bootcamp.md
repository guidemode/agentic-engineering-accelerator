# Phase 0 - Leadership Bootcamp, Baseline, and Business Case

**Weeks 1–2 of the 14-week envelope (pre-accelerator mobilisation)** · [← back to README](README.md) · [next: Phase 1 →](phase-1-team-onboarding.md)

## Objective

Get engineering leadership to **calibrated intuition** about an AI coding assistant: enough to tell a productive session from an unproductive one, and enough to recognise both over-trust and under-trust when it shows up in teams later.

Also lock in structural decisions (teams, owners, baselines) and produce a first-cut investment case for the pilot.

## Why first

If leaders cannot read an assistant session critically, they either rubber-stamp anything that compiles or panic at the first model error. Both failure modes kill the program. Two days of hands-on work is the minimum to avoid both.

## Who

- Engineering leadership: EMs, staff+, principal engineers
- The two **Agentic Engineers** (see [README](README.md#the-agentic-engineer-role)) — they run the workshop, drive Week 2 setup, and embed with the lighthouse teams from Phase 1 onwards
- *Not yet*: lighthouse team engineers (they come in at Phase 1)

## The work

### 2-day workshop (Week 1)

Compressed, hands-on, in-person if possible. **Run by the Agentic Engineers**, with leadership as participants. The aim is calibration, not completeness.

**Day 1 - Mental model and basics**
- How the assistant works: context limits, tool loop, permission modes
- Assistant instruction files (for example `CLAUDE.md`) as a contract: what belongs there and what does not
- Plan mode: when to use it, how to read a plan critically
- Steering mid-session: course-correcting, abandoning vs. pushing through
- Hands-on: each leader runs a small task in their own repo, observed

**Day 2 - Patterns, failure modes, and decisions**
- Skills, hooks, slash commands, subagents — what each is *for* and when
- Context management: compaction, subagents for context isolation, when to /clear
- Anatomy of a "good" session vs. an "unproductive" session - walk through real recordings
- Failure modes: over-eager edits, hallucinated APIs, scope creep, and uncritical assistant agreement
- Group exercise: pick lighthouse teams, archetypes, champions, marketplace owner
- Commit to baseline metrics and how they'll be captured

### Week 2 - Baseline, structural setup, and explicit decisions

Leaders return to their day jobs. The Agentic Engineers drive:

- **Portfolio selection and scope confirmation** for one team in each main track (acceleration, net new, modernisation)
- **Baseline metrics captured** for each candidate lighthouse team (last 4-8 weeks):
  - PRs merged / engineer / week
  - Lead time ticket → merge
  - Defect escape rate, revert rate
  - Test coverage snapshot
  - Initial confidence + happiness self-reports from team engineers (1-5 scale)
- **Investment-case model drafted** with scenario ranges, expected outcomes, and decision points for scale/no-scale
- **Marketplace repo created**, owner named, contribution process drafted (even if minimal)
- **Tooling check**: every participating engineer has assistant tooling working, with auth, permissions model agreed, and any required network/proxy/secrets sorted
- **Lighthouse teams formally selected** with named champions per team
- **Communication owner named**, channel and format chosen for end-of-phase summaries (see Communication track in [README](README.md#communication))
- **Explicit decisions agreed and recorded** (see next section)
- **Phase 1 kickoff scheduled** with all participating teams

## Explicit decisions to make in Phase 0

These are the program's working contract. Agreed by leadership + champions, recorded in writing, reviewed at each phase boundary. They are deliberately set *here* — not invented per-phase — so teams aren't surprised mid-program by shifting goalposts.

Expect to revisit them at phase reviews. They are starting positions, not commandments.

### 1. Phase 3 PR targets per team

The point is direction-of-travel evidence, not output maximisation. Targets calibrated against the Phase 0 baseline for each team. Phase 3 is the first phase where teams ship real features under supervision, so it's the first phase where PR throughput is a meaningful signal.

**Healthy starting examples** (adapt to your teams):

| Archetype | Suggested Phase 3 target (over 2 weeks) | Rationale |
|---|---|---|
| Greenfield | 8-12 assistant-touched PRs | Low review ceremony, fast iteration, new code is easier |
| Active project | 4-6 assistant-touched PRs | Real users, real review pressure, integration risk |
| Legacy maintenance | 6-10 assistant-touched PRs | Smaller PRs, more of them; bug fixes and backfill |

**A target is not a quota.** Missing the target isn't failure — it's a signal to investigate in the phase review. Hitting it with sloppy work is worse than missing it with good work.

### 2. Stop-the-line triggers

A trigger is a pre-agreed condition that pauses normal operation and forces a structured conversation. It is not automatic rollback. The decision to actually stop is made by the Agentic Engineers in consultation with the affected team's champion and engineering leadership.

#### Program-wide triggers (apply at any time)

Healthy examples:

- Confidence or happiness self-report drops by ≥1 point (on the 1–5 scale) across a team for 2 consecutive weeks
- Defect escape rate climbs more than ~25% above the Phase 0 baseline for any team
- Marketplace owner role becomes vacant and isn't refilled within a week
- A security, compliance, or legal concern surfaces that wasn't in scope at kickoff
- An incident occurs that can't be explained by reading the audit trail

#### Phase-specific candidate triggers

These are the watch-list per phase. The leadership group reviews this list during the Phase 0 workshop, adds, removes, or refines as needed, and commits to the resulting set.

**Phase 1 — team onboarding & discovery:**
- The compressed onboarding workshop didn't land — engineers are still confused about basic mechanics after week 1
- AEs are doing the work instead of pairing — engineers can't run sessions without an AE in the room
- A team has had no engineer report a "good session" by the end of the phase
- The pain point inventory is empty or trivially short — nothing to feed into Phase 2

**Phase 2 — guardrails & substrate:**
- Feedback loop (lint/test/typecheck) is still too slow after substrate work — the work didn't land
- Assistant instruction files were polished but not referenced in real sessions
- Substrate work doesn't trace back to the Phase 1 pain inventory — teams reinventing problems
- All five workstreams attempted shallowly, none done well

**Phase 3 — first features:**
- Reviewers are rubber-stamping assistant-generated PRs (caught in retro or via spot-check)
- A team is shipping but engineers report dropping confidence or happiness
- Defect escape rate climbs above the agreed band
- Scope creep — assistant-driven PRs are quietly growing beyond the originating ticket

**Phase 4 — scale-up:**
- Newly added team members can't reach productive work in their first week using the existing assets
- Lighthouse champions are burning out from onboarding load
- Marketplace has contributions but no reuse across teams
- A new capability (subagents, parallel, spec-driven) is being used because it's new, not because it helps

**Phase 5 — full agentic:**
- An autonomous flow caused a real incident and the chain of causation can't be reconstructed from the audit trail
- A flow is producing PRs faster than humans can meaningfully review them — bottleneck moved, not vanished
- Any flow is running without a named owner
- Throughput is up but confidence or happiness is down

**Phase 6 — graduation & recommendation:**
- Security / compliance / legal review surfaces a serious issue
- No evidence that newly added team members internalised the patterns — transferability claim is unsupported
- Pressure to write a positive recommendation regardless of the evidence

### 3. What "stable or improving" means for the confidence and happiness metrics

Agreed in Phase 0 so the phase reviews aren't arguing about definitions.

Healthy starting example: a team is "stable or improving" if the rolling 2-week average of confidence and happiness self-reports is within 0.3 points of the previous 2-week window, or higher. Drops larger than that go on the agenda for the next review.

## Stage gate to Phase 1

Advisory — but if any of these are missing, Phase 1 will struggle.

- [ ] Each leader has shipped at least one merged PR using the assistant
- [ ] Each leader can articulate (in writing, even one paragraph) one thing the assistant is good at and one thing it is weak at in their codebase
- [ ] Three lighthouse teams selected, archetypes assigned, champions named
- [ ] Marketplace repo exists with a named owner
- [ ] Baseline metrics captured for each lighthouse team
- [ ] Initial investment-case model has been reviewed and accepted by leadership
- [ ] Every participating engineer has assistant tooling installed and working
- [ ] Communication owner named, channel and format for end-of-phase summaries chosen
- [ ] **Explicit decisions recorded**: Phase 3 PR targets per team, stop-the-line triggers (program-wide and per-phase), definition of "stable or improving" for confidence and happiness
- [ ] **Phase 0 end-of-phase summary** drafted and sent org-wide — sets the tone for the comms cadence (what the program is, who's involved, what to expect)

**Special blockers — Phase 1 cannot start without these:**
- Tooling/auth/permissions are not sorted
- No marketplace owner volunteers
- Leadership doesn't feel calibrated after the workshop — extend by a few days rather than push forward unprepared
- The explicit decisions above haven't been agreed and recorded
- Access to repos/environments is incomplete for pilot teams

## Marketplace contributions from this phase

- Seed assistant instruction template (for example `CLAUDE.md`)
- First version of "house style" slash commands (whatever the org's conventions are: PR description format, commit style, ticket linking, etc.)
- Workshop materials themselves, kept as onboarding assets for future cohorts

## Risks specific to this phase

- **Workshop becomes a lecture.** It must be hands-on. If leaders aren't typing, it's failing.
- **Champions are nominated, not chosen.** Champions need to want this. Assigned champions often disengage.
- **Baseline gets skipped because "we know roughly where we are."** Then Phase 5 has nothing to compare against. Capture the numbers even if they're rough.
- **Marketplace owner is "TBD".** TBD means no one. Name a person.
