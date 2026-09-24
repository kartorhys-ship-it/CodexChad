---
name: prototype
description: Build a bounded, throwaway prototype to resolve one concrete product, UI, or logic question that discussion alone cannot settle. Use before finalizing a spec when seeing or exercising the behavior will produce better evidence.
metadata:
  short-description: Prototype to answer one question
---

# Prototype

Use a prototype to learn something specific before committing to production behavior. The prototype is an experiment, not an unapproved production implementation.

## Decide whether to prototype

First state the unresolved question in one sentence. Examples:

- “Can a user understand this navigation when the screen is narrow?”
- “Does this state transition handle retry and cancellation correctly?”

If the uncertainty can be resolved by inspecting the code, consulting a source, or asking the user, do that instead. Prototype when interaction, visual comparison, or exercising edge cases will give better evidence than more discussion.

Choose the smallest artifact that can answer the question:

- For UI uncertainty, build a few structurally distinct alternatives that can be compared in the real page context where practical.
- For logic or state uncertainty, build a small interactive harness that exposes the state and lets someone exercise the important transitions.

## Build the experiment

1. Record the question, the relevant assumptions, and what observation would count as an answer.
2. Inspect the existing project and use its vocabulary and conventions where useful. Keep the experiment isolated from production behavior.
3. Build only what is needed to test the question. Avoid production-level persistence, abstractions, error handling, and broad feature scope unless one of those is the question being tested.
4. Make it easy for the intended reviewer to exercise or compare the alternatives. Label states and scenarios clearly.
5. Show the artifact to the user or decision owner. Ask them to choose or describe what they learned; do not select a preferred UI on their behalf when their judgment is needed.

## Capture the result

Summarize:

- The question the prototype tested.
- What was observed and what decision follows.
- Remaining uncertainty or evidence limits.
- Which requirement, acceptance criterion, domain model, or technical decision should change.

Carry the decision—not the prototype's incidental implementation—into the durable project or feature specification. Keep the prototype separate from production code and link to it when it is useful evidence. Do not merge or ship the prototype unless the user explicitly asks for that and it has been brought up to production standards.

## Stop when

The decision owner can answer the original question from the prototype and the result is recorded where implementation planning can find it. If the experiment exposes a larger question, state it and propose a smaller next experiment rather than expanding this one without bounds.

