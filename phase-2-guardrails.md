# Phase 2 — Guardrails & Substrate

**Weeks 5–6 of the 14-week envelope (accelerator weeks 3–4)** · [← Phase 1](phase-1-team-onboarding.md) · [README](README.md) · [Phase 3 →](phase-3-first-features.md)

## Objective

Close the substrate gaps that Phase 1 surfaced. Make each lighthouse team's codebase **fast to iterate on with the assistant** and **safe enough for the assistant to act on with confidence**.

## Premise

You can't move quickly with an assistant in a codebase where feedback loops are slow, hooks aren't wired, agent-safe areas aren't understood, and instruction docs are missing or wrong. Phase 1 produced a pain point inventory from real session experience. Phase 2 works through it.

This phase is **driven by the Phase 1 inventory**. Teams don't invent substrate work to do — they fix what they already proved was broken.

## Who

The three lighthouse teams. Each team prioritises the workstreams that match the gaps their Phase 1 sessions surfaced.

The two **Agentic Engineers** continue embedded across teams, pairing on substrate work, modelling how to use the assistant to do the substrate work itself, and developing the champions toward independence.

Leadership reviews progress at phase end but does not drive day-to-day execution.

## The work

Five workstreams. **No team will fully complete all five.** Each team picks the two or three with the biggest payoff based on their Phase 1 inventory.

### 1. Polish the context docs

Phase 1 produced rough versions. Phase 2 makes them durable.

- Assistant instruction file (for example `CLAUDE.md`): refined based on what was actually useful in Phase 1 sessions, not on what *should* be useful in theory
- `ARCHITECTURE.md`: services, data flow, key abstractions — written or refined where Phase 1 sessions showed gaps
- Glossary: domain terms the assistant kept misunderstanding
- "How this fits": relationship to adjacent systems and shared platforms

Use the assistant to draft. Humans verify. Anything that wasn't referenced in real Phase 1 sessions gets cut, not polished.

### 2. Test coverage assessment and selective backfill

- Where coverage is thin in agent-touchy areas
- Minimum smoke tests that prove core behaviour is intact after a change
- Targeted backfill where Phase 1 showed the assistant editing risky code without enough safety net
- Output: the agent-safe vs. human-led map from Phase 1, now committed to the repo and treated as authoritative

### 3. Linting, typechecking, formatting

Close the mechanical feedback loop so the assistant receives fast, deterministic signals.

- Linting runs quickly on changed files
- Typechecking is incremental where possible
- Formatter is deterministic — no "two valid styles" debates
- All checks are wired into assistant hooks so the assistant gets the same feedback the engineer does

### 4. Deployment and rollback

- Blast radius of a bad merge — quantified, not hand-waved
- Whether rollback is reliable and simple
- Whether preview environments are available so the assistant (or its reviewer) can validate against a real environment
- Feature flags or kill switches for risky paths

### 5. Hook scaffolding

- Pre-commit checks
- Post-edit lint and format
- Test runners in the session loop
- Additional hooks that convert repeated human feedback into automated checks

The Phase 1 pain point inventory is the source list — anywhere a human said "the assistant kept doing X wrong" is a candidate for a hook.

## Working pattern

- Phase begins with each team converting its Phase 1 pain inventory into a prioritised substrate backlog
- Daily standup includes "what's still slowing us down"
- Substrate work is itself done with the assistant where possible — modelling for the team that infrastructure work can be agentic too
- Engineers continue session journals (one good, one bad, weekly)
- Cross-team demo at end of phase: each team shows the substrate gap they fixed and how it changed session quality

## Stage gate to Phase 3

Advisory. Triggers were agreed in [Phase 0](phase-0-leadership-bootcamp.md#explicit-decisions-to-make-in-phase-0).

- [ ] Assistant instruction file is current and was *referenced in actual sessions* during the phase (not written and abandoned)
- [ ] Lint/typecheck/format feedback runs within a team-agreed threshold and is wired as hooks
- [ ] Agent-safe vs. human-led map is committed to each repo and treated as authoritative
- [ ] First-pass risk register exists per archetype
- [ ] At least one preview/rollback path is in place (or explicitly documented as out of scope)
- [ ] Each team can name two specific gaps that Phase 2 closed and what changed in session quality as a result
- [ ] **End-of-phase communication** sent org-wide — substrate fixes that paid off, ready for first supervised features
- [ ] Phase 2 stop-the-line triggers reviewed in retro — none currently active, or active ones have a documented mitigation

## Marketplace contributions from this phase

- Reusable hook templates (pre-commit, post-edit, test-on-save)
- Lint/format/typecheck configurations
- Instruction-file fragments by stack/language
- Skills such as coverage audit, architecture-draft-from-code, glossary generation
- Per-archetype starter packs (now grounded in real substrate work, not theory)

## Risks specific to this phase

- **Documentation theatre.** Docs look good but are not used in sessions. The "was it referenced?" gate exists for a reason.
- **Doing all five workstreams shallowly instead of two well.** Pick the gaps the Phase 1 inventory said matter most. Depth over breadth.
- **Scope drift into refactoring.** Guardrails work gets replaced by opportunistic rewrites of code that wasn't in the inventory.
- **Overbearing hooks.** Safety checks that slow engineers down more than they help. Tune them.
- **Treating substrate work as homework before "real" features.** This *is* real work. Phase 3 features only land cleanly because of what gets built here.
- **Ignoring the Phase 1 inventory.** If Phase 2 work doesn't trace back to the inventory, the team is reinventing problems instead of solving the real ones.
