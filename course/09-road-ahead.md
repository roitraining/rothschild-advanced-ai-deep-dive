<!-- course-title: Advanced AI Deep-Dive: Rothschild and Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild and Co

# Chapter 9: The Road Ahead – Trends, Vendors, and Tools

---

# Chapter 9: Objectives

- Identify near-term shifts in AI capability and product shape
- Use a shared technical vocabulary with engineers and vendors
- Evaluate AI vendors and products with structured criteria
- Defend a stack recommendation using evidence from this course

---

<!-- layout: navigation -->
# Chapter 9

- **What's Next in AI**
- The Technical Vocabulary Cheat Sheet
- Evaluating AI Vendors and Products

---

# Decision-Relevant Shifts

| Shift | Why it matters for Rothschild |
| :--- | :--- |
| Computer-using / deep tool agents | Higher blast radius; need allow-lists and HITL |
| Long-context economics | More docs in-prompt — still not a substitute for ACL-aware RAG |
| On-prem / open-weight revival | Stronger data-path control; you own ops and evals |
| Governed agent platforms | Audit, identity, and policy become buying criteria |

---

<!-- layout: 2-column -->
# Signals vs Noise

### Watch
- Eval transparency
- Enterprise data controls
- Agent auditability
- Total cost at scale

### Discount
- Leaderboard-only claims
- "Fully autonomous" banking
- Vague "proprietary brain"
- One-demo architecture

---

<!-- layout: navigation -->
# Chapter 9

- What's Next in AI
- **The Technical Vocabulary Cheat Sheet**
- Evaluating AI Vendors and Products

---

<!-- layout: 2-column -->
# Vocabulary Cheat Sheet

### Must-fluent
- Token, context window, embedding
- RAG, tool/function call, MCP
- HITL, hallucination

### Nice-to-know
- Inference, fine-tune, skill
- Test-time compute, A2A
- Trajectory eval

---

# Must-Fluent Definitions

| Term | One-line meaning |
| :--- | :--- |
| Token | Model text unit; drives limits and cost |
| Context window | Working memory for one run |
| Embedding | Meaning vector for search / RAG |
| RAG | Retrieve firm data, then generate |
| Tool / function call | Structured action the runtime executes |
| MCP | Standard for tools/resources to hosts |
| HITL | Human approval in the loop |
| Hallucination | Fluent output without reliable grounding |

---

# Phrases That Change Vendor Meetings

- "Show me the **tool permission model** and audit log."
- "How is **ACL-aware retrieval** enforced across deal rooms?"
- "What happens on **low-confidence** retrieval?"
- "Which parts are **model, orchestration, and data platform**?"

> [!TIP]
> Ask for an architecture diagram with trust boundaries — not only a feature list.

---

<!-- layout: navigation -->
# Chapter 9

- What's Next in AI
- The Technical Vocabulary Cheat Sheet
- **Evaluating AI Vendors and Products**

---

# Evaluation Scorecard

| Criterion | Probe |
| :--- | :--- |
| Task fit | Your prompts, your docs, your metrics |
| Grounding | Citations, freshness, ACL |
| Agency | Tools, skills, step limits |
| Security | Identity, DLP, residency, retention |
| Operability | Logs, evals, versioning, support |
| Economics | Unit cost × expected volume |

---

# Partial Scorecard: Copilot vs Cursor

**Workflow:** Draft an internal deal dossier from approved sources

| Criterion | Microsoft Copilot (enterprise) | Cursor |
| :--- | :--- | :--- |
| Task fit | Strong in Office / M365 surface | Strong for code + repo context |
| Grounding | Tenant Graph / ACL-aware when configured | Repo + connected docs; firm ACL varies |
| Agency | Copilot Studio / agents — check gates | Agent mode in IDE — local blast radius |
| Security | Enterprise tenant controls | Org policy + what you connect |
| Fit call | Prefer for banker document workflows | Prefer for prototype / vibe-coding loops |

> [!NOTE]
> Scores are illustrative — re-run on *your* prompts and policy constraints.

---

<!-- layout: 3-column -->
# Compare Deliberately

### Model providers
- OpenAI
- Anthropic
- Google

### Work surfaces
- Copilot
- Claude Code
- Cursor

### Questions
- Where does data go?
- What can it act on?
- How do we evaluate?

---

<!-- layout: 2-column -->
# Anti-Portfolio and TCO

### Will not buy this year
- Ungated "fully autonomous" client send
- Consumer multimodal for deal-room media
- Leaderboard wins with no audit story
- Duplicate copilots that fragment identity

### TCO lines to count
- Seats / licenses
- Tokens × volume × retries
- Retrieval infra + ACL sync
- Human review time + evals ops

> [!IMPORTANT]
> A strong stack recommendation includes an explicit **no** list.

---

# Build-Your-Stack Logic

1. Rank workflows by value and risk
2. Choose autonomy level you can supervise
3. Separate productivity suite vs sensitive agent runtimes
4. Demand MCP/API strategy for systems of record
5. Pilot with eval harness + human gates
6. Decide buy/build **per layer** — not as one monolith

---

<!-- layout: stacked -->
# After This Course

- [ ] Name your top 3 workflows by value × risk
- [ ] Map each to model / data / tools / controls
- [ ] Draft one agent or RAG one-pager (non-goals included)
- [ ] Fill a vendor scorecard on a live RFP or renewal
- [ ] Write an anti-portfolio for the next 12 months
- [ ] Bring one concrete question to office hours

![ROI Logo](images/roi-logo-with-name.png)

---

# Lab 9: The Build-Your-Stack Challenge

**Time:** 30 minutes

**Lab guide:** [Lab 9 instructions](labs/lab-09-build-your-stack.md)

---

# What You Learned

- Identified near-term shifts in AI capability and product shape
- Used a shared technical vocabulary with engineers and vendors
- Evaluated AI vendors and products with structured criteria
- Defended a stack recommendation using evidence from this course

---

# Quiz 1 of 3

**Which diligence question best pressure-tests an AI vendor's enterprise readiness?**

- A. "Are you on the leaderboard this month?"
- B. "Show the tool permission model, ACL-aware retrieval, and audit logs"
- C. "Can you promise fully autonomous banking with zero errors?"
- D. "Do you have a proprietary brain we cannot inspect?"

---

# Quiz 1 — Answer

**Which diligence question best pressure-tests an AI vendor's enterprise readiness?**

**Correct: B.** "Show the tool permission model, ACL-aware retrieval, and audit logs"

- Scorecard: task fit, grounding, agency, security, operability, economics
- Prefer architecture with trust boundaries over feature lists
- Leaderboards and vague autonomy claims are weak signals
- Ask what happens on low-confidence retrieval

---

# Quiz 2 of 3

**In the technical vocabulary cheat sheet, what does RAG mean?**

- A. Replace all governance with generation
- B. Retrieve firm data, then generate grounded answers
- C. Run agents without tools
- D. Randomly assign GPU capacity

---

# Quiz 2 — Answer

**In the technical vocabulary cheat sheet, what does RAG mean?**

**Correct: B.** Retrieve firm data, then generate grounded answers

- Pair with tokens, embeddings, context window, MCP, skills, HITL in vendor conversations
- Inference is running the model; fine-tune specializes weights — not live truth
- Hallucination = fluent output without reliable grounding
- Must-fluent terms keep meetings precise; nice-to-know terms deepen diligence

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
Run a build-your-stack challenge for your team (model providers vs work surfaces such as Copilot and Cursor).

### Discuss
- Which workflows are high-value vs high-risk?
- What belongs in the anti-portfolio this year?
- How will you pilot with evals, HITL, and a TCO sketch before scaling?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Run a build-your-stack challenge for your team (model providers vs work surfaces such as Copilot and Cursor).**

### Strong Answers Mention
- Rank workflows by value/risk; separate productivity vs sensitive runtimes
- Demand MCP/API strategy for systems of record; scorecard in action
- Anti-portfolio: no ungated autonomous client send; no consumer multimodal for deal rooms
- Pilot with eval harness + gates; count seats, tokens, retrieval, and review time

### Watch For
- One-demo architecture decisions
- "Fully autonomous" without operability/security evidence
- Ignoring total cost at expected volume
- Maximalist buy lists with no explicit nos

---

# Questions and Answers

Questions?
