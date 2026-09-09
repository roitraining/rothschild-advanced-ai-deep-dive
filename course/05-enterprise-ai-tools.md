<!-- course-title: Advanced AI Deep-Dive: Rothschild and Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild and Co

# Chapter 5: Hands-On with Enterprise AI Tools

---

# Chapter 5: Objectives

- Explain what sits under enterprise AI toolsets
- Apply advanced prompting techniques with intent
- Map AI features inside daily office applications
- Deconstruct a hands-on deal-briefing workflow technically

---

<!-- layout: navigation -->
# Chapter 5

- **The Enterprise AI Toolset Under the Hood**
- Advanced Prompting Techniques
- AI Inside Daily Office Applications
- Deal Briefing: Technical Unpack

---

# Apply Chapters 1–4 to the Suite You Already Use

- Same stack vocabulary: host app, model, grounding/RAG, tools/MCP, controls
- Today: map those ideas onto Copilot / Workspace / firm AI—not a new product tour
- Ask: what is grounded, what can act, what is logged, what a human must still own
- Lab later: watch those layers fire during a 5-minute deal briefing

> [!NOTE]
> Product names change; the diligence questions stay: identity, ACL, action vs draft, retention.

---

# What “Copilot” Usually Means

- A **host application** with identity, UI, and policy
- One or more **models** selected by task/SKU
- **Grounding** to files, email, chat, or tenant search
- Optional **plugins/tools** for actions beyond text

---

<!-- layout: 2-column -->
# Under the Hood

### What you see
- Chat pane / inline rewrite
- “Summarize this doc”
- Suggested email draft
- Meeting recap

### What is happening
- Prompt assembly + system policy
- Retrieval from permitted content
- Model inference (maybe reasoning)
- Safety filters and logging

---

<!-- layout: stacked -->
# Prompt Assembly (What Products Actually Do)

1. **System / tenant policy** — what the assistant may say or do
2. **Grounding hits** — files, mail, or search snippets the user is allowed to see
3. **User prompt** — the visible request
4. **Tool results** (optional) — calendar, CRM, plugins
5. **Model inference** — possibly a reasoning pass
6. **Filters + logs** — safety, DLP, audit

> [!NOTE]
> The chat box is the tip of the iceberg. Diligence questions target steps 1–2 and 4–6.

---

# Grounding Failure Modes (Office Suites)

- **Wrong ACL**: summary includes a file the asker should not see—or omits the one that matters
- **Stale content**: old OneDrive/SharePoint version treated as current
- **Over-broad Graph scope**: “search my tenant” becomes accidental discovery
- **Draft vs send confusion**: model proposes an email; product settings may allow send

---

# Enterprise Tool Selection Criteria

| Criterion | What to demand |
| :--- | :--- |
| Tenant grounding | Retrieval scoped to permitted tenant content—not the open web by default |
| ACL fidelity | Same permissions as the source system; no “helpful” over-share |
| Action vs draft | Explicit: send / write / delete vs draft-only |
| Log retention | Where prompts and outputs live; how long; who can access |
| Model by SKU | Which model powers which feature; reasoning vs fast tier |

---

# Questions to Ask Your Tooling Team

- Which model(s) power which features?
- What tenant data can be retrieved, and how is ACL enforced?
- Are prompts used to train foundation models?
- Where are logs stored, and for how long?
- What can the assistant **do** (send, write, delete) vs. only draft?

---

<!-- layout: navigation -->
# Chapter 5

- The Enterprise AI Toolset Under the Hood
- **Advanced Prompting Techniques**
- AI Inside Daily Office Applications
- Deal Briefing: Technical Unpack

---

<!-- layout: 2-column -->
# Prompting Beyond “Write me a summary”

### Steer
- Role + audience + stakes
- Output contract (sections, length, tone)

### Constrain
- Source limits and quote rules
- Verification asks and refusal criteria

---

# Advanced Patterns

| Pattern | Use |
| :--- | :--- |
| Skeleton first | Outline → fill → tighten |
| Critique pass | “Attack this memo as risk” |
| Compare modes | Bull / base / bear cases |
| Extract then synthesize | Facts table → narrative |
| Refusal criteria | “If covenants unclear, say so” |

---

<!-- layout: 2-column -->
# Weak vs Strong Prompt

### Weak
- “Summarize this target report and list the risks.”
- No source rule
- No output schema
- No refusal criteria

### Strong
- ONLY the attached report
- Table: Risk | Evidence quote | Page
- Rank top 5 for Debt Advisory
- List gaps; no invented figures

---

# Example: Risk Extraction Prompt

```text
Using ONLY the attached target report:
1) Extract key risk factors as a table: Risk | Evidence quote | Page
2) Rank top 5 for a Debt Advisory first look
3) List data gaps that block a view on leverage capacity
Do not invent figures. If unknown, write "Not in source".
```

> [!TIP]
> Put evaluation criteria in the prompt when the task is high-stakes.

---

<!-- layout: 3-column -->
# More Advanced Techniques

### Structured outputs
- Tables / JSON schemas
- Force fields the reviewer needs
- Easier automated checks

### Critique-and-revise
- Draft → attack as risk
- Revise against the critique
- Keeps optimism in check

### Adversarial reviewer
- Separate pass: “find missing risks”
- Different role than the drafter
- High value before client send

---

<!-- layout: stacked -->
# Winning Prompts Become Chapter 3 Skills

- A strong one-off prompt is a prototype—not a team capability
- Promote winners into **skills / templates**: role, output contract, refusal rules, non-goals
- Version them with the workflow (same idea as pinning prompts + indexes in Ch4)
- Office AI + firm skills + corpus RAG beats reinventing the prompt each Monday

> [!TIP]
> If two bankers need the same risk table, it belongs in a shared skill—not two chat histories.

---

<!-- layout: navigation -->
# Chapter 5

- The Enterprise AI Toolset Under the Hood
- Advanced Prompting Techniques
- **AI Inside Daily Office Applications**
- Deal Briefing: Technical Unpack

---

<!-- layout: 2-column -->
# Workflow Deep-Dive: Email Draft vs Send

### Assist well
- Triage and outline from permitted thread
- Tone polish; agenda bullets
- Flag missing attachments or unclear asks

### Gate hard
- Confirm draft-only vs auto-send settings
- Client-facing language = human edit required
- Never let “helpful send” bypass review

> [!WARNING]
> Draft and send are different products. Know which SKU you are in before the model finishes the sentence.

---

<!-- layout: 2-column -->
# Workflow Deep-Dive: Spreadsheet Verify-Math

### Assist well
- Explain a formula in plain language
- Propose structure for a sensitivity table
- Spot unit or period mismatches in labels

### Gate hard
- Recompute material figures yourself or via tools
- Do not treat chart titles as verified metrics
- Export intermediate tables when stakes are high

---

<!-- layout: 2-column -->
# Workflow Deep-Dive: Meeting Notes and ACL

### Assist well
- Summarize for attendees who already had access
- Extract actions with owners and dates
- Draft follow-ups from the transcript

### Gate hard
- Recap must not invent attendees or leak other rooms
- Same ACL as the meeting artifact—no “tenant search” stretch
- Sensitive deals: confirm retention before long-term storage

---

<!-- layout: 3-column -->
# Trust Calibration

### High assist
- Formatting
- Tone polish
- Agenda drafts

### Verify always
- Figures and covenants
- Legal language
- Client emails

### Prefer tools/RAG
- Live positions
- Policy truth
- Deal facts

---

<!-- layout: navigation -->
# Chapter 5

- The Enterprise AI Toolset Under the Hood
- Advanced Prompting Techniques
- AI Inside Daily Office Applications
- **Deal Briefing: Technical Unpack**

---

# Deal Briefing: What You Will Watch

- Short path: attach report → extract risks → rank for DA → draft client email
- Pause after each step and name the technical layer firing
- Goal: leave with a checklist you can reuse on any office AI feature
- Lab runs the workflow; this section names the machinery

---

# Technical Unpack Checklist

| Step | What happened technically? |
| :--- | :--- |
| Open / attach report | Grounding scope + ACL |
| Extract risks | Prompt assembly + inference |
| Rank for DA | Output contract / rubric in prompt |
| Draft client email | Draft vs send; human edit required |
| Verify figures | Tools/RAG or manual recompute—not vibes |

---

<!-- layout: stacked -->
# After the Unpack: Make It Repeatable

- Save the winning risk-extraction prompt as a team skill (Ch3 pattern)
- Pair office grounding with firm RAG when institutional memos matter
- Measure time saved **and** error types introduced
- Escalate when grounding is thin—same refuse rule as Ch4

---

# Lab 5: The 5-Minute Deal Briefing

**Time:** 25 minutes

**Lab guide:** [Lab 5 instructions](labs/lab-05-deal-briefing.md)

---

# What You Learned

- Explained what sits under enterprise AI toolsets
- Applied advanced prompting techniques with intent
- Mapped AI features inside daily office applications
- Deconstructed a hands-on deal-briefing workflow technically

---

# Quiz 1 of 3

**What does an enterprise “Copilot” usually include under the hood?**

- A. Only a standalone model with no identity or policy
- B. A host app with identity/policy, model(s), grounding to permitted content, optional tools
- C. Guaranteed training of the foundation model on your prompts
- D. Unrestricted write actions across email and files by default

---

# Quiz 1 — Answer

**What does an enterprise “Copilot” usually include under the hood?**

**Correct: B.** A host app with identity/policy, model(s), grounding to permitted content, optional tools

- Product names change; the pattern is host + model + grounding + tools + controls
- Ask which data can be retrieved, how ACLs work, log retention, and action vs draft
- Training-on-prompts is a contract/config question—not assumed
- Permissions for send/write/delete must be explicit

---

# Quiz 2 of 3

**Which prompting pattern best fits extracting key risks from a target company report for Debt Advisory?**

- A. “Summarize this” with no source constraints
- B. Extract evidence-quoted risks as a table, rank for the use case, and list data gaps; forbid invented figures
- C. Ask for a bullish narrative only
- D. Raise creativity and omit refusal criteria

---

# Quiz 2 — Answer

**Which prompting pattern best fits extracting key risks from a target company report for Debt Advisory?**

**Correct: B.** Extract evidence-quoted risks as a table, rank for the use case, and list data gaps; forbid invented figures

- Advanced prompting: role/audience, source constraints, output contract, verification asks
- Extract-then-synthesize beats a single vague summary for high-stakes work
- Put evaluation criteria in the prompt when stakes are high
- Figures and client language remain verify-always

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
Office AI proposes a spreadsheet “insight”: YoY EBITDA margin rose 180 bps. The figure must go into a client email.

### Discuss
- What do you recompute or re-query before trusting the number?
- Draft vs send: who owns the last click, and why?
- When would you refuse the insight and escalate instead of polishing the email?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Office AI proposes a spreadsheet “insight”: YoY EBITDA margin rose 180 bps. The figure must go into a client email.**

### Strong Answers Mention
- Recompute from source cells or approved tools; check units and periods
- Client email = verify always; draft-only until a human sends
- Thin or conflicting inputs → refuse / escalate; do not invent polish
- Promote a verified calc checklist into a team skill for next time

### Watch For
- Accepting chart titles or chat prose as the metric
- Auto-send or “helpful” send without review
- Treating the deal-briefing lab walkthrough as the only diligence pattern

---

# Questions and Answers

Questions?
