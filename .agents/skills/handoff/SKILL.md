---
name: handoff
description: Prepare a focused handoff when coding work must move to a fresh session, another agent, directory, or prototype. Summarize live state and next steps while pointing to existing project artifacts instead of duplicating them.
metadata:
  short-description: Hand work to another session
---

# Handoff

Create a handoff only when the work needs to travel to another session, agent, workspace, or side task. If the same session can continue cleanly, continue there; a handoff file adds value through portability.

## Prepare the handoff

Write a concise Markdown document tailored to the next session's purpose. Include:

- **Next task:** what the receiving agent should do first and what is out of scope.
- **Current state:** what has been completed and what is still in progress.
- **Why:** the relevant user intent and decisions that explain the current approach.
- **Verified facts:** evidence-backed findings, command results, and current state.
- **Unverified assumptions:** label them as assumptions; do not turn guesses into premises.
- **Blockers and decisions:** what is waiting, who must decide, and what question to ask.
- **Pointers:** repository paths or URLs for specs, plans, ADRs, tickets, commits, diffs, and logs.
- **Suggested skills/tools:** the workflow the next agent should use, if applicable.
- **First action:** a concrete starting step that can be done without re-asking for known context.

Do not copy whole specs, plans, or conversation histories into the handoff. Point to their current source of truth. Keep the handoff focused on live context that is not already recorded elsewhere. Remove credentials, tokens, passwords, private personal data, and unrelated sensitive details.

## Store and transfer

Use a temporary file when the handoff is short-lived and only needs to cross sessions on this machine. Use a user-approved workspace or shared location when the receiving person or environment needs durable access. Choose a clear filename and tell the user where it was saved.

Before passing it on, read the document as a fresh agent would. Check that it names the intended next task, that pointers resolve to the right artifacts, and that unverified beliefs are labeled. The receiving agent must re-check volatile or consequential claims before acting on them.

## Completion

Report the handoff path or link and one-sentence next step. Do not claim the receiving session has completed work unless its result has been observed.

## Sources and adaptation

- Source video: [YouTube](https://youtu.be/dtAJ2dOd3ko).
- This skill is an independently written practical synthesis of the source's workflow ideas. It does not reproduce the video transcript.
