---
name: teach
description: Build a stateful, source-grounded learning path when the user wants to master a topic, tool, framework, or codebase over multiple sessions. Use for continuing learning, not a one-off explanation.
metadata:
  short-description: Teach a topic across sessions
---

# Teach

Use this skill when the user's goal is sustained learning. Start by establishing why they want to learn, what they already know, how they prefer to learn, and what they want to be able to do. A single question or explanation can be answered directly without creating a teaching workspace.

## Establish a learning workspace

Use a dedicated user-approved directory for one learning mission. Keep it separate from production code unless the user specifically wants learning materials in that repository. Explain where the workspace will be created before writing if the destination is unclear.

Maintain a small set of durable learning records, adapting to the topic:

- **Mission:** purpose, learner goals, prerequisites, constraints, and target capability.
- **Sources:** trusted source list with provenance; prioritize primary documentation and materials appropriate to the topic.
- **Lessons:** short, self-contained sessions, each teaching one useful capability with examples and practice.
- **References:** concise material the learner will revisit, such as a glossary, checklist, or worked example.
- **Learning record:** what the learner has demonstrated, misunderstandings to revisit, and a justified next step.
- **Preferences:** requested format, pacing, accessibility needs, and feedback style.

Keep the learner's durable progress distinct from guesses about their ability. Update records from observed answers or work, not from praise or completion alone.

## Design the next lesson

1. Read the mission, sources, preferences, prior lessons, and learning record before choosing content.
2. Identify one outcome the learner can demonstrate by the end.
3. Use the learner's stated background and demonstrated work to choose an appropriate challenge: demanding enough to require thought, small enough to be achievable with support.
4. Ground factual claims in trusted sources and cite them in the lesson. Mark uncertainty and distinguish sourced facts from teaching analogies or recommendations.
5. Teach in a focused sequence: explain the concept, show an example, let the learner retrieve or apply it, and give specific feedback.
6. Use a quiz or exercise to check understanding. Reveal answers only after the learner has had a chance to attempt them, unless they ask otherwise.
7. End with a practical transfer task and a clear success criterion.

Use HTML when interactivity, diagrams, or guided practice meaningfully help. Use Markdown or another simple format when it is clearer. Reuse shared styles or components across lessons instead of making every lesson a separate design system.

## Adapt from evidence

After the learner responds, identify what they understood, where their reasoning broke down, and what support helped. Update the learning record concisely. Choose the next lesson based on that evidence:

- Revisit prerequisites when a gap blocks progress.
- Change the explanation or example when the concept was presented unclearly.
- Increase complexity when the learner demonstrates reliable understanding.
- Use spaced retrieval to revisit important skills after an interval.
- For questions that depend on professional judgment or lived experience, explain what sources establish and point to an appropriate human community or expert when needed.

Do not repeat lessons the learner has demonstrated, claim mastery from passive reading, or make progress feel like a formality. Let the user pause, skip, or change the learning goal.

## Finish each session

Record the lesson's outcome, the learner's demonstrated evidence, remaining uncertainty, and a suggested next step. Keep learning notes separate from project decisions: if the learner approves a technical or product choice for a real project, transfer that decision into its own project artifact with its rationale and status.

## Sources and adaptation

- Source video: [YouTube](https://youtu.be/s5T5oQJcJ6U).
- This skill is an independently written practical synthesis of the source's workflow ideas. It does not reproduce the video transcript.
