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

# Day 2 Evidence Spine

For multimodal outputs and agent buying decisions, keep one chain visible:

**claim → source → check → human gate**

| Step | Question |
| :--- | :--- |
| Claim | What assertion enters a dossier, pitch, or buy decision? |
| Source | Which doc, chunk, tool result, or transcript backs it? |
| Check | Did a human or eval verify freshness, ACL, and fit? |
| Human gate | Who may release, buy, or act — and under what policy? |

> [!IMPORTANT]
> Fluent demos skip the spine. Bankable workflows do not.

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
# Computer-Use / Browser Agents: Blast Radius

### What expands
- Credentials in the session (SSO, saved logins, API keys)
- Screens and pages the agent can see (PII, deal rooms)
- Irreversible clicks: send, approve, wire, delete, publish
- Audit gaps if actions are not logged like API tools

### Hard requirements
- Allow-list domains and actions; default deny
- Separate identities — never personal banker SSO
- HITL before irreversible or client-visible steps
- Immutable audit of screens/actions or do not buy

> [!CAUTION]
> A browser agent with mailbox and CRM access is not "just another chat." Treat it as privileged ops.

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

# Vendor-Talk Vocabulary (Keep Thin)

Terms you need in diligence meetings — not a glossary dump.

| Term | One-line meaning |
| :--- | :--- |
| Token / context window | Text unit and working memory; drives limits and cost |
| Embedding / RAG | Meaning vectors + retrieve firm data, then generate |
| Tool call / MCP | Structured actions; standard host↔tool wiring |
| HITL | Human approval before high-risk acts |
| Hallucination | Fluent output without reliable grounding |

> [!NOTE]
> Optional deeper terms (inference, fine-tune, test-time compute, A2A, trajectory eval) live in Ch2–8 — bring them only when the conversation needs them.

---

# Phrases That Change Vendor Meetings

- "Show me the **tool permission model** and audit log."
- "How is **ACL-aware retrieval** enforced across deal rooms?"
- "What happens on **low-confidence** retrieval?"
- "Which parts are **model, orchestration, and data platform**?"
- "Where is the **HITL gate** — and can operators bypass it?"

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

# Scorecard: Two Offerings vs Dossier Workflow

**Workflow:** Draft an internal Debt Advisory dossier from approved sources — then banker gate before any wider share.

| Criterion | Offering A: Enterprise document copilot | Offering B: IDE / agent coding surface |
| :--- | :--- | :--- |
| Task fit | Strong for banker docs and M365-shaped drafts | Strong for prototype / vibe-coding loops |
| Grounding | Tenant Graph / ACL when configured — verify deal rooms | Repo + connected docs; firm ACL often weaker |
| Agency | Studio/agents — demand HITL and step limits | Agent mode — local blast radius; gate exports |
| Security | Enterprise tenant, residency, retention levers | Org policy + whatever you connect |
| Fit call | Prefer for dossier drafting near banker workflow | Prefer for building internal tools — not client dossier path |

> [!NOTE]
> Re-score on *your* prompts, corpora, and policy. Names matter less than dossier criteria.

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

# Micro-Demo: Pitch Claim Through the Scorecard

Facilitator walks **one** vendor pitch claim live (2–4 minutes) before Lab 9:

1. Restate the claim in one sentence
2. Map it to scorecard rows (task fit → economics)
3. Force **claim → source → check → human gate**
4. Decide: pilot, park, or anti-portfolio

**Example claim to critique:** "Our agent drafts and sends client-ready dossiers with full autonomy."

> [!TIP]
> Participants should steal this ritual for every RFP and renewal.

---

<!-- layout: stacked -->
# After This Course → Office Hours Intake

Carry these into **Chapter 10** (write on the intake slide before or during the day):

- [ ] Name your top 3 workflows by value × risk
- [ ] Map each to model / data / tools / controls
- [ ] Draft one agent or RAG one-pager (non-goals included)
- [ ] Fill a vendor scorecard on a live RFP or renewal
- [ ] Write an anti-portfolio for the next 12 months
- [ ] Bring **one concrete scenario** to office hours (workflow, claim, or constraint)

![ROI Logo](images/roi-logo-with-name.png)

---

<!-- layout: 2-column -->
# Day 2 Must-Run vs If-Time

### Protect
- Ch8 failure modes + HITL
- Lab 9 scorecard / stack choice
- Chapter 10 office hours intake

### Cut first if short
- Deep multi-agent / A2A variants
- Extra vendor taxonomy slides
- Nice-to-know vocabulary expansion

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
- Ask what happens on low-confidence retrieval and where HITL sits

---

# Quiz 2 of 3

**A vendor demos a computer-use agent that opens the browser, reads a deal room, and can click "Send." For Debt Advisory dossiers, which scorecard weight should dominate your buy decision?**

- A. Leaderboard rank of the underlying model
- B. Agency + security: allow-lists, identity separation, irreversible-click HITL, and audit of actions
- C. How pretty the demo UI looks in the pitch deck
- D. Whether the vendor says "fully autonomous" in marketing

---

# Quiz 2 — Answer

**A vendor demos a computer-use agent that opens the browser, reads a deal room, and can click "Send." For Debt Advisory dossiers, which scorecard weight should dominate your buy decision?**

**Correct: B.** Agency + security: allow-lists, identity separation, irreversible-click HITL, and audit of actions

- Computer-use expands credentials, screens, and irreversible clicks
- Task fit alone does not justify ungated send from a deal room
- Prefer document copilots with banker gates for dossier share paths
- Put ungated browser send on the anti-portfolio until controls exist

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
Run a build-your-stack challenge for your team (model providers vs work surfaces). Pair two offerings against the dossier workflow scorecard.

### Discuss
- Which workflows are high-value vs high-risk?
- What belongs in the anti-portfolio this year?
- How will you pilot with evals, HITL, and a TCO sketch before scaling?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Run a build-your-stack challenge for your team (model providers vs work surfaces). Pair two offerings against the dossier workflow scorecard.**

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
