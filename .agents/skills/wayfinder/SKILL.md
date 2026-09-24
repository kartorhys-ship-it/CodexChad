---
name: wayfinder
description: Map and resolve decisions for a large, ambiguous project whose destination is known but whose route is not yet clear. Use when the work exceeds a single focused planning session; stop at a usable specification and implementation plan.
metadata:
  short-description: Map decisions for complex work
---

# Wayfinder

Use this workflow to turn a foggy, multi-session effort into a set of explicit decisions and a buildable next step. This is a planning workflow; do not drift into implementing production features while resolving the map.

## Confirm the destination and scope

Write the desired outcome in plain language and confirm it with the user. Bound the effort to a coherent project slice or epic. Inspect the repository and existing project decisions so the map starts from known facts.

Separate:

- **Known:** supported by the user or inspected project evidence.
- **Decided:** an explicit choice that constrains later work.
- **Open:** a question whose answer could change scope, architecture, or acceptance.
- **Assumed:** a provisional premise that still needs confirmation.

Do not create a broad map when the route is already clear. Move directly to a concise spec and implementation plan for small, well-understood work.

## Create a decision map

Represent unresolved work as questions to answer, not implementation tickets disguised as questions. For each item record:

- The question and why it matters to the destination.
- Evidence or dependencies needed before it can be answered.
- The kind of work that can answer it: research, user decision/interview, prototype, or a concrete prerequisite task.
- Blocking relationships and what becomes actionable after it is resolved.
- The expected decision artifact or proof.

Keep the map small and adaptive. Resolve high-impact dependencies early; do not speculate in detail about distant work whose assumptions may change. For parallel work, verify that the items are actually independent and that separate agents will not need to answer the same user question.

## Resolve the frontier

Work through actionable questions one at a time by default. For each:

1. Read its context, evidence, and dependencies.
2. Do only the research, interview, prototype, or prerequisite task needed to settle it.
3. Distinguish observed evidence from recommendation and remaining uncertainty.
4. Record the decision and its rationale in the map or linked durable project artifact.
5. Update affected open items when the answer changes their assumptions.

Ask the user to make consequential product choices. If a prototype is the best way to resolve a question, use the `prototype` skill when available and carry its answer back into the map. Keep implementation outside this planning loop unless an explicitly scoped prerequisite task is required to unblock a decision.

## Close the map

The map is ready to close when the important decisions needed to define the next buildable scope are settled or explicitly accepted as assumptions. Then:

1. Synthesize the decisions into a readable feature or project specification.
2. Turn that specification into a bounded implementation plan or tickets, including acceptance and validation criteria.
3. Preserve links to research, prototypes, and decision records without copying their full contents into multiple places.
4. Name unresolved risks and the next human decision owner.

Stop after handoff to the specification and implementation workflow. A cleared decision map is not itself a code change, a release plan, or permission to start a broader build.

## Quality checks

- Each open map item asks a question whose answer changes what should be built or how it should be built.
- Each decision has an evidence basis, an owner, or an explicit provisional status.
- The destination stays bounded and understandable as new facts arrive.
- Later items are revised when earlier decisions invalidate their assumptions.
- The final spec retains user intent, tradeoffs, scope, and proof criteria without treating the whole map as permanent truth.

## Sources and adaptation

- Source video: [YouTube](https://youtu.be/F3lL98Pj90o).
- This skill is an independently written practical synthesis of the source's workflow ideas. It does not reproduce the video transcript.
