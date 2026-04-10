# Agentic Engineering Accelerator

A structured accelerator that helps an engineering organisation move from early assistant usage to repeatable, production-ready agentic workflows, with clear guardrails and measurable outcomes.

A **14-week envelope**: 2 weeks of mobilisation and business-case setup (Phase 0), followed by the 12-week accelerator (Phases 1–6).

This is **v0**. Expect it to change as we run it.

## Shape

A 14-week envelope: 2 weeks of Phase 0 (mobilisation, business case, leadership bootcamp) **before** the 12-week accelerator, then six 2-week phases of accelerator delivery. Each phase has an objective, the work, a stage gate, and what it contributes to the shared marketplace.

| Phase | Envelope weeks | Accelerator weeks | Focus | Doc |
|---|---|---|---|---|
| 0 | 1–2 | — (pre-accelerator) | Mobilisation, leadership bootcamp, baseline, business case | [phase-0-leadership-bootcamp.md](phase-0-leadership-bootcamp.md) |
| 1 | 3–4 | 1–2 | Team onboarding & discovery | [phase-1-team-onboarding.md](phase-1-team-onboarding.md) |
| 2 | 5–6 | 3–4 | Guardrails & substrate | [phase-2-guardrails.md](phase-2-guardrails.md) |
| 3 | 7–8 | 5–6 | First supervised features | [phase-3-first-features.md](phase-3-first-features.md) |
| 4 | 9–10 | 7–8 | Workflow scale-up | [phase-4-scale-up.md](phase-4-scale-up.md) |
| 5 | 11–12 | 9–10 | Full agentic patterns | [phase-5-full-agentic.md](phase-5-full-agentic.md) |
| 6 | 13–14 | 11–12 | Graduation & recommendation | [phase-6-rollout.md](phase-6-rollout.md) |

## How this maps to typical pilot SoWs

The accelerator language stays generic, but it maps cleanly to common pilot structures:

| Typical SoW track | Accelerator archetype / track | Primary outcome |
|---|---|---|
| Acceleration of in-flight delivery | Active project | Faster delivery with stable quality |
| Net new product delivery | Greenfield | AI-native delivery patterns from day one |
| Modernisation | Legacy maintenance (+ optional legacy rewrite) | Safer change in older systems, then selective rewrite experiments |
| Enablement and scale package | Cross-cutting marketplace + playbooks + governance + metrics + comms | Repeatable model ready for wider rollout |

## Participants

**Three lighthouse teams**, one per project archetype:

1. **Greenfield** - new project, no legacy weight, ideal for early agentic patterns
2. **Active project** - under feature development, real users, real review pressure
3. **Legacy maintenance** - keep-the-lights-on systems, bug fixes, test/doc backfill

**Optional fourth track - legacy rewrite via bounded autonomous loops.** Decision is deferred to the end of Phase 3 / start of Phase 4, once foundational patterns are proven.

**The pilot stays bounded.** No new teams are added during the program. In Phase 4 we add 1–2 new engineers to each lighthouse team to test transferability at the individual level. The decision to scale to additional teams happens after the program, as an output of Phase 6.

### The Agentic Engineer role

The program is delivered by **about 2 senior engineers in an Agentic Engineer role**. They are embedded with the lighthouse teams across the full envelope — running the Phase 0 workshop, then embedded with teams through the 12-week accelerator — splitting time across the three teams plus marketplace and communications work.

Their job has four parts:

1. **Facilitate** - run the Phase 0 workshop, coordinate cross-team retros, and hold working agreements
2. **Coach** - pair with engineers in real sessions, give direct feedback, and develop champions
3. **Pair and execute** - ship code with the teams; they are not an external review layer
4. **Curate** - drive the marketplace with the named owner and remove low-value assets

Two seniors is deliberately tight. It forces early champion development and keeps coaching focused. One is too thin to run effectively; more than three usually creates dependency.

## Cross-cutting tracks (run in parallel to all phases)

### Marketplace

A shared, versioned catalogue of skills, hooks, slash commands, subagents, and assistant instruction fragments (for example `CLAUDE.md`) curated from real work. **Owner is named in Phase 0.**

The metric that matters is **assets reused by a team that did not author them**. Contribution count alone is weak signal.

### Community of practice

- Weekly 30-minute demo and retro across the three lighthouse teams
- Async channel for wins, failures, and questions
- Office hours with the Agentic Engineers

### Communication

Lighthouse work only delivers enterprise value if the rest of engineering can follow what changed. A **named communication owner** (assigned in Phase 0) is responsible for this.

- **End-of-phase summary** at the close of every phase: wins, learnings, what did not work, and what is next
- **Mid-program checkpoint** (around end of Phase 4): broader update for leadership and adjacent teams, including early cost baseline
- **Final summary** at end of Phase 6: public-facing version of the recommendation for the wider engineering organisation
- **Channel and format agreed in Phase 0** so people know where to look every time

### FinOps

Token usage and cost forecasting become first-class from Phase 4 onwards. Baseline in Phase 4, operating discipline in Phase 5, formal review and forecast in Phase 6.

### Metrics and telemetry

Baseline is captured in **Phase 0** and tracked to Phase 6. See [Measurement](#measurement).

## Governance and delivery assurance cadence

- **Daily**: team standups include delivery progress, blockers, and assistant usage
- **Per sprint**: planning/refinement with backlog decisions made in normal team ceremonies
- **End of sprint**: demos with progress against throughput, quality, and enablement outputs
- **Fortnightly**: steering review with leadership on risks, metrics, decisions, and escalations
- **End of program**: graduation review, security/compliance/legal review, and recommendation sign-off

## Delivery preconditions

These are assumed before Phase 1 starts:

- Leadership sponsorship is in place and pilot teams are empowered to participate
- Access to repos, environments, CI/CD, and required network tooling is available
- Assistant licenses and tooling access are available for all participating engineers
- Baseline telemetry is accessible (or can be captured in Phase 0)
- Teams can provide timely feedback/sign-off on phase outputs
- Security/compliance stakeholders are engaged and reachable through the program

If these preconditions are not met, Phase 0 should be extended rather than forcing Phase 1.

## Stage gates

Stage gates are **advisory by default**. They force structured discussions between phases and are reviewed in cross-team retros at each phase boundary.

Any gate can be escalated to **stop-the-line** if advancing would be unsafe (for example: quality regressions, autonomy outpacing control, or marketplace debt becoming unmanageable).

## Measurement

Baselined in Phase 0 and tracked weekly through Phase 6. Keep the basket small and practical.

**Throughput**
- PRs merged per engineer per week
- Lead time from ticket open to PR merged

**Quality**
- Defect escape rate (bugs found post-merge)
- Revert rate and time-to-revert

**Substrate**
- Test coverage delta
- Documentation coverage/freshness

**Confidence (critical in early phases)**
- Weekly 1-5 self-report from each engineer: *"I trust the assistant in this codebase"*
- Weekly 1-5 self-report: *"I enjoyed my work this week"*

**Adoption**
- Percent of PRs that used an assistant in the delivery loop (not "AI-generated" claims)

**Marketplace health**
- Assets contributed
- Assets reused by other teams

**Cost (from Phase 4 onwards)**
- Per-engineer and per-team token spend
- Cost per useful outcome (for example, merged PRs, resolved bugs) by workflow type
- Forecast spend at hypothetical org-wide adoption

We do **not** measure lines of code generated. It rewards the wrong behaviour.

## Project archetypes — quick reference

| Archetype | Best for early phases | Risk profile | Phase 5 ambition |
|---|---|---|---|
| Greenfield | Spec-driven workflows, parallel agents | Low blast radius, high learning | Mostly autonomous on bounded modules |
| Active project | Plan mode plus supervised PRs | Medium; real users mean stronger review discipline | Agent as full pair-programmer with selective autonomy |
| Legacy maintenance | Bug reproduction, test backfill, docs | Low if scoped tightly; higher for structural changes | Autonomous flows on low-risk classes of work |
| Legacy rewrite (optional) | Starts Phase 4 at earliest | Highest | Bounded autonomous loops against clear specs and tests |

## Security, compliance, legal

Assumed cleared at kickoff. **A formal review is scheduled in Phase 6** before any broader rollout, covering code provenance, data egress, autonomous-action audit trails, and any production-touching flows.

If this assumption becomes false at any point, that is a stop-the-line trigger.

## What "done" looks like

By end of Phase 6:

- Three lighthouse teams operating with agentic workflows matched to their archetype
- Engineers added in Phase 4 have written onboarding feedback as transferability evidence
- Marketplace v1.0 with named owners and contribution/deprecation process
- Documented playbooks per archetype
- Metrics showing direction of travel against Phase 0 baseline (positive or negative)
- FinOps review with pilot spend, cost-per-outcome, and steady-state forecast
- Security/compliance/legal sign-off or explicit remediation plan
- End-of-phase communications delivered, plus final org-wide summary
- A clear recommendation to leadership covering scale decision, operating model, and budget envelope

The recommendation is the primary deliverable. Any rollout starts after this, with its own scope and plan.

## Open questions still to resolve

- Exact teams and named champions (Phase 0 deliverable)
- Marketplace owner (Phase 0 deliverable)
- Communication owner and channel/format (Phase 0 deliverable)
- Phase 3 PR targets and stop-the-line triggers (Phase 0 deliverable)
- Legacy rewrite track yes/no (end of Phase 3)
- Steady-state operating model recommendation (Phase 6 deliverable)
