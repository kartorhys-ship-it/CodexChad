---
name: spec-driven-development-with-coding-agents
description: Guide coding-agent work with durable project intent, feature specifications, reviewed plans, independent validation, and evidence-driven replanning. Use when a task spans multiple steps or sessions, has meaningful product or architectural tradeoffs, or the user asks for spec-driven development; keep simple low-risk edits lightweight.
metadata:
  short-description: Run a spec-driven coding workflow
---

# Spec-Driven Development with Coding Agents

Use this skill to keep a coding agent's work aligned with project intent across planning, implementation, validation, and later sessions. The user owns product goals and consequential tradeoffs. The agent may inspect, propose, plan, implement, and report, but must surface consequential uncertainty instead of silently deciding it.

## Choose the right amount of process

- Use durable project and feature artifacts when work is multi-step, high-impact, likely to span sessions, or needs coordination and review.
- Keep a tiny, low-risk change lightweight. Do not create a constitution, roadmap, branch, or multiple documents just to follow ceremony.
- Preserve the project's existing conventions and artifact locations. Introduce new files only when they solve a real continuity or review problem.
- A specification improves fidelity to stated intent; it does not prove that the intent is correct or make generated code reliable by itself.

## Workflow

### 1. Establish the intent and inspect the project

For a new project, ask or infer the intended users, problem, desired outcome, constraints, and success criteria. For an existing project, inspect relevant code, tests, configuration, documentation, and history before proposing a design.

Record important unknowns as questions. Separate observed facts from assumptions and recommendations. Do not present inferred architecture or roadmap items as confirmed decisions.

### 2. Record project-level decisions

Create or update a concise project constitution only when decisions should guide multiple features. It can capture:

- Mission: intended users, problem, boundaries, and success.
- Technical direction: stack, conventions, constraints, and rationale.
- Roadmap: small outcomes and dependencies, treated as revisable priorities rather than promises.

Distinguish hard requirements, current choices, and open questions. Keep the constitution consistent with the actual repository. On legacy projects, derive a draft from inspected artifacts and ask the owner to resolve consequential gaps.

### 3. Define one feature's outcome

Select a useful slice that can be implemented and validated. Write feature requirements that state:

- Expected behavior and acceptance criteria.
- Relevant context and decisions.
- In-scope and explicitly out-of-scope behavior.
- Important edge cases, dependencies, and unresolved questions.

Requirements define the result and boundaries; they do not prescribe every implementation step. Resolve high-impact product, data, security, compatibility, or architecture choices with the user before proceeding.

### 4. Plan before substantial implementation

Ask the coding agent to inspect relevant patterns and produce a bounded plan. Review it for consistency with project decisions, requirements, exclusions, dependencies, and validation. Adjust the plan before a large change if it expands scope, adds avoidable dependencies, or assumes an unresolved decision.

Use a branch or another isolated change boundary when it fits the repository and review needs. Keep changes small enough for a person to understand. Do not impose branching on trivial edits.

### 5. Implement with visible state and permissions

Give the agent only the context and tools needed for the feature. Make action boundaries clear: what it may read, edit, run, or publish, and which actions need human approval. Ask it to report meaningful deviations, files changed, decisions made, and remaining uncertainty.

Keep project-wide decisions in project-level artifacts and feature-specific detail with the feature. Do not treat the chat transcript as the only durable record when later work depends on those decisions.

### 6. Validate independently against the requirements

Define observable proof before implementation when practical. Run the relevant checks, such as tests, type checks, builds, route or UI checks, and manual review. Report actual results; do not say a check passed unless it was run and its result is known.

Compare behavior and the diff to the requirements. Treat tests as evidence for exercised behavior, not proof of all product, visual, security, or operational properties. Add human review when the consequence or uncertainty warrants it.

### 7. Replan and update the right artifacts

Classify each mismatch before changing documents:

- Implementation defect: fix the code and rerun relevant checks.
- Missing, ambiguous, or mistaken requirement: revise the feature specification, then align the code and validation.
- Changed project-level decision: update the constitution and affected feature specs.
- New capability or dependency: evaluate it as roadmap work instead of quietly broadening the current feature.

When the feature is complete, update the roadmap, changelog, or other project record used by the repository, then review and merge using the project's normal process. Begin the next feature from the resulting current state.

## Reusable workflows and agent portability

After a procedure has proved stable and repeats often, consider capturing it as an agent skill or workflow. Automate repeatable steps, not unresolved user decisions. Keep important project knowledge in inspectable files and ordinary repository practices so it can be used by another session or agent. Tool-specific instructions and protocols remain specific to the environment; do not assume prompts behave identically across agents.

## MVPs as a stress test

Treat a larger MVP build as a deliberate stress test only when the project constitution and completed feature specifications are trustworthy and there is enough review capacity to evaluate the result. For each deviation, determine whether it exposes a specification gap, an implementation defect, or new roadmap work. Use that evidence during replanning rather than treating a successful build as proof that the planning system is complete.

## Useful artifacts

Adapt these names to repository conventions; they are roles, not mandatory filenames:

| Artifact role | Captures |
| --- | --- |
| Project mission | Users, problem, boundaries, success |
| Technical direction | Stack, conventions, constraints, rationale |
| Roadmap | Ordered small outcomes and dependencies |
| Feature requirements | Behavior, decisions, edge cases, scope, exclusions |
| Feature plan | Tasks, dependencies, and expected intermediate results |
| Validation plan | Repeatable checks and human review criteria |
| Change record | What changed and why, using the project's existing convention |

## Completion standard

Before calling a meaningful feature complete, be able to point to:

1. The agreed outcome and scope.
2. The project and feature context used to guide the work.
3. The change made and any material deviation from the plan.
4. The verification performed and its actual result.
5. The updated project state or the explicit reason no durable artifact needed changing.

If any item is missing, state the gap clearly and identify the next action or owner.

