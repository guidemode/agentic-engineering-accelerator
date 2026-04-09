# Phase 4 — Full Agentic Patterns

**Weeks 9–10** · [← Phase 3](phase-3-scale-up.md) · [README](README.md) · [Phase 5 →](phase-5-rollout.md)

## Objective

Move from "agent as pair-programmer" to **"agent as autonomous worker on bounded tasks."** Land the patterns that will define the org's steady-state agentic workflows.

## Premise

By now teams know how to supervise. The question is: where can we *reduce* supervision safely, and where can't we? Phase 4 finds out by deliberately running autonomous flows in production — with kill switches, budgets, and audit trails from day one.

## Who

The three lighthouse teams (now including the engineers added in Phase 3) plus the optional legacy rewrite track if running.

The two **Agentic Engineers** are still embedded but their role has shifted further: they pair on autonomous flow design, push hard on the kill-switch / budget / audit / ownership non-negotiables, and start handing more facilitation responsibility to the champions. By the end of this phase, the champions should be running their teams' sessions; the AEs should be the second opinion, not the first.

## Patterns to land

### Long-running loops with clear exit criteria
Spec-driven, evaluation-driven loops that know when they are done and stop. **No loop without an exit condition** - open-ended loops are a failure mode, not a feature.

### Multi-agent orchestration
Where it actually helps. Be honest where it doesn't. The right answer is sometimes "one capable agent in a tight loop" not "five agents in a swarm."

### Autonomous PR flows for low-risk classes
Candidates:
- Dependency bumps
- Lint / format fixes
- Test backfill against existing behaviour
- Documentation updates
- Mechanical refactors with strong test coverage

These flows produce PRs that humans still review — but the human isn't in the loop during generation.

### Auto-triage on incoming bugs and failing tests
Agent reads the failure, attempts a reproduction, drafts a hypothesis (and optionally a fix). Human picks up from there.

### Scheduled agent runs
Cron-style maintenance work — coverage reports, dependency audits, doc freshness checks, drift detection.

## Non-negotiables for any autonomous flow

Every autonomous flow ships with **all four** of these or it doesn't ship:

1. **Kill switch** — turn it off in 30 seconds, no deploy required
2. **Budget** — both wall clock *and* token spend, plus a PR-count cap where it fits. Hits any limit → stops.
3. **Audit trail** — humans can see what it did, why, when, and **what it cost**, after the fact
4. **Ownership** — a named human is responsible for it (including the bill)

If any of these are missing, the flow stays supervised. The token-budget requirement is non-negotiable — autonomous loops without a spend cap are how surprise bills happen.

## FinOps — operating phase

Phase 3 captured the baseline. Phase 4 is where autonomous flows make cost a first-class operating concern.

**Activities:**
- Each autonomous flow reports its weekly token spend alongside its output
- Track **cost per useful outcome** for each flow — cost per merged PR, cost per resolved bug, cost per doc page generated. This is the only number that actually matters.
- Distinguish flows where cost scales linearly with value (good) from flows where cost scales with repeated retries (bad - fix or stop)
- Forecast updated: with real autonomous-flow spend numbers, refine the "what would this look like at org-wide scale" projection from Phase 3
- Surprise spend reviews: if any flow's weekly spend deviates >2x from the prior week without a known cause, investigate

The FinOps view feeds directly into the Phase 5 recommendation. By the end of Phase 4, leadership should be able to look at the program and answer "if we doubled the number of teams, what would the bill look like" with a number, not a guess.

## Working pattern

- Each team picks **one or two** autonomous flows to land — not five. Depth over breadth.
- Daily check on autonomous flows: what did they do, what did they get wrong, what surprised us, **what did they spend**
- Mid-phase incident review: there *will* be at least one thing that goes sideways. Treat it as a learning artefact, not a failure.
- Demo at end of phase shows autonomous flows in action with their kill switches, budgets, audit trails, and cost-per-outcome numbers

## Stage gate to Phase 5

Advisory. Targets and triggers were agreed in [Phase 0](phase-0-leadership-bootcamp.md#explicit-decisions-to-make-in-phase-0).

- [ ] At least one autonomous flow per team running in production with measurable value
- [ ] Every autonomous flow has kill switch, budget (wall clock + token), audit trail, named owner — verified, not assumed
- [ ] Mid-phase incident review completed and lessons captured (something *will* have gone sideways)
- [ ] Each archetype has a documented "what we'd do differently next time"
- [ ] Confidence + happiness metrics within the agreed band
- [ ] Cost-per-useful-outcome captured for each autonomous flow
- [ ] Updated org-scale cost forecast ready for Phase 5
- [ ] Phase 4 stop-the-line triggers reviewed in retro — none currently active, or active ones have a documented mitigation
- [ ] **End-of-phase communication** sent org-wide — autonomous flows in production (with the kill-switch story), incident learnings, updated cost picture

## Marketplace contributions from this phase

- Autonomous flow templates (with kill switches and budgets baked in)
- Audit trail and observability patterns
- Incident playbooks specific to agentic workflows
- Loop scaffolding (spec-driven, evaluation-driven)
- Per-archetype "what worked, what didn't" writeups

## Risks specific to this phase

- **Superficial autonomy.** Flows look autonomous but still require constant manual intervention. Be honest about the real supervision level.
- **PR volume outpaces review capacity.** The bottleneck moves from writing code to reviewing code. If you do not plan for this shift, delivery slows down.
- **Loops without exit conditions.** A loop that never terminates is just a budget burn — sometimes literal.
- **Cost runaway.** A misconfigured loop can spend more in a weekend than a team did all phase. Token budgets are non-negotiable for a reason.
- **Cost-per-outcome ignored in favour of throughput numbers.** "We shipped 40 PRs" is meaningless if each one cost more than the engineer time it replaced.
- **One incident triggers panic rollback.** Autonomous flows will occasionally make poor decisions. The right response is a retro and a fix, not cancelling the program.
- **Forgetting the legacy maintenance team.** Autonomous flows are arguably most valuable here. Don't let the shinier teams hog attention.
- **Confidence drops quietly.** Throughput goes up, mood goes down, no one mentions it because the dashboards look good. Watch the self-reports.
