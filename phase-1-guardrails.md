# Phase 1 - Guardrails and Context Reverse-Engineering

**Weeks 3-4** · [← Phase 0](phase-0-leadership-bootcamp.md) · [README](README.md) · [Phase 2 →](phase-2-first-features.md)

## Objective

Make each lighthouse team's codebase **legible to an agent** and **safe to act on**. Use this setup work as practical training for the team.

## Premise

You cannot move quickly with an assistant in a codebase it cannot navigate and that humans do not trust. Before pushing feature velocity, fix the engineering substrate. This substrate work is the training.

## Who

The three lighthouse teams. Each team prioritises the workstreams most relevant to its archetype.

The two **Agentic Engineers** (see [README](README.md#the-agentic-engineer-role)) embed across the three teams from this phase onwards. They pair in real sessions, model practices, and help each team develop a durable champion.

Leadership reviews progress at phase end but does not drive day-to-day execution.

## The work

Five workstreams. No team will fully complete all five in this phase.

### 1. Context reverse-engineering

Generate and validate the docs the agent (and humans) need to navigate the codebase:

- Assistant instruction file (for example `CLAUDE.md`): project purpose, conventions, boundaries, and risk areas
- `ARCHITECTURE.md`: services, data flow, and key abstractions
- Glossary: domain terms, acronyms, internal language
- "How this fits": relationship to adjacent systems and shared platforms

Use the assistant to draft. Humans verify.

### 2. Test coverage assessment

- Where coverage is thin
- Which areas are safe for agent edits vs. human-led only
- Minimum smoke tests that prove core behaviour is intact after change
- Whether test feedback loops are fast enough for practical assistant sessions

Output: a documented "agent-safe vs. human-led" map of the codebase.

### 3. Linting, typechecking, formatting

Close the mechanical feedback loop so the agent receives fast, deterministic signals.

- Linting runs quickly on changed files
- Typechecking is incremental where possible
- Formatter is deterministic
- All checks are wired into assistant hooks

### 4. Deployment and rollback

- Blast radius of a bad merge
- Whether rollback is reliable and simple
- Whether preview environments are available
- Whether feature flags and kill switches exist for risky paths

### 5. Hook scaffolding

- Pre-commit checks
- Post-edit lint and format
- Test runners in the session loop
- Additional hooks that convert repeated human feedback into automated checks

## Working pattern

- Daily team standup includes "what is the assistant doing for us today"
- Each engineer logs one good session and one bad session per week
- Pair sessions encouraged: two engineers, one assistant
- Weekly cross-team demo: one win and one miss per team

## Stage gate to Phase 2

Advisory.

- [ ] Assistant instruction file exists, is current, and was used in real sessions
- [ ] Lint/typecheck/format feedback runs within a team-agreed threshold and is wired as hooks
- [ ] Team can name "agent-safe" and "human-led" code areas
- [ ] First-pass risk register exists per archetype
- [ ] At least one preview/rollback path is in place (or explicitly out of scope)
- [ ] Each engineer has logged at least three session journals
- [ ] End-of-phase communication sent org-wide by the comms owner

**Stop-the-line triggers:**
- Feedback loops are too slow to make assistant sessions workable
- Instruction files were written but are not used in real sessions
- No engineer on a team reports a single good session in two weeks

## Marketplace contributions from this phase

- Reusable hook templates (pre-commit, post-edit, test-on-save)
- Lint/format/typecheck configurations
- Instruction-file fragments by stack/language
- Skills such as coverage audit, architecture-draft-from-code, and glossary generation
- Per-archetype starter packs

## Risks specific to this phase

- **Documentation theatre.** Docs look good but are not used in sessions.
- **Scope drift into refactoring.** Guardrails work gets replaced by opportunistic rewrites.
- **Overbearing hooks.** Safety checks slow engineers down too much.
- **Treating this as pre-work only.** This is core delivery work, not homework.
