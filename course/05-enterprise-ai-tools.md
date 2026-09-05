<!-- course-title: Advanced AI Deep-Dive: Rothschild & Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild & Co

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

---

# What “Copilot” Usually Means

- A **host application** with identity, UI, and policy
- One or more **models** selected by task/SKU
- **Grounding** to files, email, chat, or tenant search
- Optional **plugins/tools** for actions beyond text

> [!NOTE]
> Product names change; the architecture pattern stays: host + model + grounding + tools + controls.

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

<!-- layout: navigation -->
# Chapter 5

- The Enterprise AI Toolset Under the Hood
- Advanced Prompting Techniques
- **AI Inside Daily Office Applications**

---

# Where AI Shows Up in the Workday

- **Documents**: summarize, rewrite, structure decks
- **Email/calendar**: draft, triage, meeting prep
- **Spreadsheets**: explain formulas, draft analyses (verify math)
- **Meetings**: transcripts, actions, follow-ups
- **Teams chat**: catch-up summaries with permission boundaries

---

<!-- layout: 3-column -->
# Trust Calibration

### High assist
- Formatting
- Tone polish
- Agenda drafts

### Verify always
- Figures & covenants
- Legal language
- Client emails

### Prefer tools/RAG
- Live positions
- Policy truth
- Deal facts

---

<!-- layout: stacked -->
# From Feature to Workflow

- One-off prompts help; **repeatable playbooks** scale
- Save winning prompts as team skills or templates
- Pair office AI with corpus RAG for institutional knowledge
- Measure time saved **and** error types introduced

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
Walk through a 5-minute deal briefing workflow in Copilot (report → risks → client email).

### Discuss
- At each step, what is the tool doing technically (prompt assembly, retrieval, inference)?
- Which outputs are “high assist” vs “verify always”?
- How would you turn a winning prompt into a team playbook or skill?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Walk through a 5-minute deal briefing workflow in Copilot (report → risks → client email).**

### Strong Answers Mention
- Host assembles prompt + policy; may ground on allowed files; model infers; filters/logs apply
- Formatting/tone = high assist; figures, legal, client email = verify always
- Save prompts as templates/skills; measure time saved and error types
- Pair office AI with corpus RAG for institutional knowledge

### Watch For
- Treating the chat pane as magic with no ACL questions
- Sending client email without human edit
- One-off prompts that never become repeatable

---

# Q&A

Questions?
