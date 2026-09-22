---
name: video-to-x-article
description: Use this skill whenever the user asks to turn a YouTube video into a long-form X (Twitter) article.
argument_hint: [YouTube URL or Video File Path]
---

# Video to X Article Transformation Skill

## 1. Goal & Definition of Done
Transform the provided video into an engaging, publication-ready X article following Nate Herk's voice and visual standards.
The output is considered DONE only when:
1. The article is drafted in a conversational, direct, punchy cadence.
2. 8-12 clean screenshots are cropped, spotlighted, and embedded.
3. Sensitive customer details, internal receipts, and tokens are redacted.
4. The mandatory QA Verification Report is generated and passes all criteria.

## 2. Freedom Level & Operating Mode
- **Operating Mode:** Semi-Deterministic (High reasoning & creative judgment for content; strict deterministic rules for privacy, redaction, and image limits).
- **Tone & Style:** Adopt the conversational, direct, punchy style from the YouTube and LinkedIn style guides. Avoid generic AI fluff.

## 3. Workflow Steps

### Step 1: Transcribe & Outline
1. Extract transcript and video chapters.
2. Identify the 3-5 core narrative pillars.
3. Formulate an irresistible opening hook and TL;DR section.

### Step 2: Drafting Narrative
1. Write clear, engaging H2 headers.
2. Keep text blocks punchy (1-3 sentences per paragraph).
3. Ensure technical terminology and framework steps are accurately articulated.

### Step 3: Visual Extraction (Browser & Tool Use)
1. Identify pivotal visual moments across key timestamps.
2. **Strict Guardrail:** Do NOT capture frames mid-transition or during animations.
3. Crop tightly to relevant UI elements; apply spotlight callouts to key numbers, tables, or graphs.
4. **Privacy Guardrail:** Redact all sensitive customer data, account receipts, API keys, or internal IDs using solid black overlay boxes (`sensitive details redacted`).

### Step 4: Layout & Placement
1. Embed screenshots directly beneath the corresponding narrative explanation.
2. **Strict Layout Rule:** Never stack multiple images consecutively without explanatory text in between.

## 4. Verification Loop (Mandatory QA Audit)
Before presenting the draft or marking the task complete, execute this self-audit and output the **QA Verification Report**:

```markdown
### QA Verification Report
- [ ] Title verified (distinct from opening line)
- [ ] Non-empty text blocks: [count >= 50]
- [ ] Inline screenshots embedded: [count between 8 and 12]
- [ ] H2 headings: [count >= 5]
- [ ] Privacy & Redaction Review: Passed (0 exposed private data)
- [ ] Visual Layout Review: Passed (No stacked images, no mid-animation frames)
- [ ] Editorial Flow: Passed (Matches style guide)
```

If any check fails, resolve it immediately before reporting completion.
