# ⚡ How to Build Codex Skills Better Than 99% of People

> **A masterclass framework for designing, verifying, benchmarking, and continuously evolving production-grade agent skills in Codex and Claude Code.**  
> *Based on the methodology by Nate Herk (AI Automation).*

---

## 🌐 Interactive Visual Presentation

An interactive HTML dashboard is included in this repository:
* **Live / Local File:** [`index.html`](./index.html) or [`how_to_build_codex_skills.html`](./how_to_build_codex_skills.html)
* **Features:**
  * 🎨 Dark & Light Mode toggle
  * 📑 Interactive 6-step framework tabs
  * 📊 Multi-model benchmark matrix (Luna vs Terra vs Soul vs Astra)
  * 📋 Copy-ready production `SKILL.md` & "Bike Method" feedback templates
  * ✅ Interactive self-audit scoring checklist

---

## 🧠 Core Mental Models

### 1. The Chocolate Chip Pancake Analogy
* **The Chef's Pancake:** The end deliverable (the Definition of Done / DoD).
* **The Recipe:** The `SKILL.md` file (exact ingredients, sequence, temperature, measurements).
* **The AI Agent:** Replicates world-class pancakes consistently because it follows the recipe instead of guessing your preferences.

Without a skill, an agent improvises blindly. With a skill, the agent replicates world-class execution every single time.

### 2. Anatomy of a `SKILL.md` File
A skill is a pure CommonMark Markdown file split into two distinct tiers:
1. **YAML Frontmatter (Metadata Header):**
   ```yaml
   ---
   name: video-to-x-article
   description: Use this skill whenever the user asks to turn a YouTube video into a long-form X (Twitter) article.
   argument_hint: [YouTube URL or Video File Path]
   ---
   ```
   *Parsed by the agent orchestrator without loading the whole file to determine whether to invoke the skill.*
2. **Instruction Body (The Meat):**
   The step-by-step logic, heuristics, tool calling guidelines, formatting constraints, and mandatory verification gates.

### 3. File Locations & Portability
* **Codex:** `.agents/skills/<skill-name>/SKILL.md`
* **Claude Code:** `.claude/skills/<skill-name>/SKILL.md`
* **Global Scope:** User-level configuration directory across all projects.
* **Portability:** Skills are 100% portable Markdown between Codex, Claude Code, and agentic harnesses.

---

## 🚀 The 6-Step Skill Building Framework

```
  [1. Reverse Engineer] ──► [2. One Job, One Trigger] ──► [3. Choose Freedom Level]
                                                                   │
  [6. The Bike Method]  ◄── [5. Walk Down Models]    ◄── [4. Build Verification Loops]
```

### Step 1: Reverse Engineer the Output ("The Chicken Parm Principle")
* **The Trap:** Asking an agent for general "chicken" produces chicken salad, boiled thighs, or sandwiches when you actually wanted *Chicken Parmesan on pasta*.
* **The Solution:** Start with a golden, finalized deliverable (a polished spreadsheet, report, or article). Feed it to the agent and prompt it backwards:
  * *“What raw data was pulled to produce this?”*
  * *“What calculations and filters were applied?”*
  * *“What layout and voice rules were followed?”*
* Codify those answers into your skill's first version.

### Step 2: One Specific Job, One Specific Trigger ("The Job Tree")
* Do not write 30-page monolithic skills that attempt to "run marketing".
* Break your work into the **Job Tree** (from *Becoming AI Native*):
  * **Trunk:** Functional domain (e.g., Content Strategy).
  * **Branches:** Workflows (e.g., Video Repurposing).
  * **Leaves:** Atomic tasks (e.g., Turn YouTube Video into an X Article).
* **Turn leaves into skills.** This enables crisp YAML descriptions for automatic triggering and easy chaining.

### Step 3: Choose the Freedom Level (Deterministic vs. Non-Deterministic)
* **Deterministic (Hard Logic / Low Freedom):**
  * Data syncs, calculation tables, CRM mappings.
  * Write explicit, numbered steps: *"Step 1: Check if value > 10. Step 2: Write to column C."*
* **Non-Deterministic (High Judgment / High Freedom):**
  * Video summarization, screenshot curation, commentary writing.
  * Provide heuristics, criteria of "good", and boundary rules. Do not hardcode rigid timestamps like *"screenshot at 2:00"*.

### Step 4: Build Verification Loops (Objective vs. Subjective QA)
* **Never accept the agent's Version 1 draft.**
* Use subagents or self-critique to iterate to **V7 or V16** before presenting to the human.
* **Objective Checks:** Binary rules (e.g., minimum 7 H2 sections, 10 inline images, zero empty blocks, citations verified).
* **Subjective Checks ("LLM-as-a-Judge"):** Multimodal review (e.g., Are screenshots caught mid-transition? Are sensitive receipts black-box redacted? Does the voice sound authentic?).
* **Required Proof Artifacts:**
  1. QA Verification Report
  2. Visual Plan
  3. Selected Frames / Assets

### Step 5: Walk Down the Models & Effort Level
1. Prototype and establish the baseline on frontier models (e.g., **Astra** / Opus-class).
2. "Walk down" the ladder: Test on **Soul** (Sonnet-class), **Terra** (Haiku-class), and **Luna** (Flash-class).
3. Find the cheapest, lightest model that passes your verification gates.
4. Walk down the reasoning effort level (High $\rightarrow$ Medium $\rightarrow$ Low / Fast Mode).

### Step 6: The Bike Method (Continuous Evolution)
* **A skill is never finished.**
* Like teaching a child to ride a bike: Start with hands on handlebars, provide immediate feedback, remove training wheels, remove elbow pads, but **never remove the helmet (guardrails)**.
* **The Golden Operational Rule:**
  > *After every single run, give positive and negative feedback and command the agent:*  
  > **"Analyze this feedback, explain why the failure occurred, and update `SKILL.md` so you never repeat this mistake again."**

---

## 📊 Live Multi-Model Benchmark: "X Article" Skill

Tested on turning a YouTube video into a published long-form X article with inline screenshots:

| Model Tier | Runtime | Visual & Cognitive Strengths | Failure Modes & Breakdowns | Nate's Verdict |
| :--- | :---: | :--- | :--- | :--- |
| **Luna** *(Lightweight)* | 28m 33s | • Clean image matching<br>• Spotlight effect on pricing table<br>• Good tone alignment | • Duplicate title in opening sentence<br>• Minor spacing glitch<br>• Missed 1 report screenshot | **Surprising value**; beat Terra in layout. |
| **Terra** *(Mid-Fast)* | **26m 00s** *(Fastest)* | • Zoomed in on eval score progression (88 $\rightarrow$ 94)<br>• Solid black-box redactions | • First 2 screenshots poorly cropped<br>• Captured frame mid-animation<br>• **Stacked 4 images consecutively at bottom** | **Disappointing**; verification loop broke. |
| **Soul** *(High-Tier)* | 38m 00s | • High visual intelligence: zoomed into table columns<br>• Redacted internal source IDs & receipts<br>• Spotlights on revenue stats | • Highlighted pass/fail count instead of score 88<br>• High latency on browser steps | **Very strong visual reasoning and detail capture.** |
| **Astra** *(Flagship)* | Fast Mode / Low Effort | • Flawless browser navigation<br>• Precise spotlighting & clean cropping<br>• 100% QA pass rate | • Highest per-token cost tier | **Nate's default choice** for production publishing. |

---

## 🛠️ Production Reference Skill

A complete, ready-to-run sample skill is included in this repo at:
📁 [`.agents/skills/video-to-x-article/SKILL.md`](./.agents/skills/video-to-x-article/SKILL.md)

---

## 🔁 The "Bike Method" Feedback Prompt

Copy and paste this prompt to train your agent after any run:

```markdown
[Agent Name], here is my operational critique on your latest run:

WHAT WORKED WELL:
- [Praise specific element: e.g., "The spotlight on the pricing chart was sharp and accurate."]
- [Praise specific tone: e.g., "The opening hook was concise and punchy."]

WHAT FAILED / REQUIRES CORRECTION:
- [Specify error 1: e.g., "In Section 2, the screenshot was taken mid-animation and looks blurry."]
- [Specify error 2: e.g., "You stacked 4 images at the end of the post without descriptive text."]
- [Specify error 3: e.g., "The opening title was duplicated into the first body paragraph."]

MANDATORY ACTION:
1. Analyze this critique and explain WHY this breakdown occurred.
2. Update your `SKILL.md` file permanently so that:
   - Specific guardrails prevent these exact failure modes.
   - The verification checklist is updated to catch this automatically.
3. Show me the diff of `SKILL.md` before proceeding.
```

---

## 📜 License & Credits

* Knowledge synthesized from the tutorial by **Nate Herk** ([YouTube](https://www.youtube.com/watch?v=9KOtMsZ9I28)).
* Repository maintained by [@kartorhys-ship-it](https://github.com/kartorhys-ship-it).
