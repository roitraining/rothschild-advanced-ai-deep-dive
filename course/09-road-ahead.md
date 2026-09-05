<!-- course-title: Advanced AI Deep-Dive: Rothschild & Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild & Co

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

- **What’s Next in AI**
- The Technical Vocabulary Cheat Sheet
- Evaluating AI Vendors and Products

---

<!-- layout: stacked -->
# What’s Next (Practical Horizon)

- Stronger **reasoning** and longer, cheaper context
- **Computer-using** and deeper tool ecosystems
- **MCP-like** standards for enterprise context portability
- Multimodal becoming default in productivity suites
- Tighter **governance** features as table stakes

---

# Decision-Relevant Shifts (Next 12–24 Months)

| Shift | Why it changes your buying |
| :--- | :--- |
| Computer-use / deeper tools | Agents can click and act—blast radius rises |
| Long-context economics | More “stuff in prompt” ≠ better tenancy design |
| Open-weight revival | Sensitive workloads may leave pure API paths |
| Governed agent platforms | HITL, audit, eval become product features |
| MCP-like portability | Fewer one-off plugins; still need IAM |

---

<!-- layout: 2-column -->
# Signals vs. Noise

### Watch
- Eval transparency
- Enterprise data controls
- Agent auditability
- Total cost at scale

### Discount
- Leaderboard-only claims
- “Fully autonomous” banking
- Vague “proprietary brain”
- One-demo architecture

---

<!-- layout: navigation -->
# Chapter 9

- What’s Next in AI
- **The Technical Vocabulary Cheat Sheet**
- Evaluating AI Vendors and Products

---

# Vocabulary You Can Deploy Tomorrow

| Term | One-line meaning |
| :--- | :--- |
| Token | Model’s text unit; drives limits & cost |
| Context window | Working memory for one run |
| Embedding | Meaning vector for search/RAG |
| Inference | Running the model on a prompt |
| Fine-tune | Specialize weights; not live truth |
| RAG | Retrieve firm data, then generate |
| Tool / function call | Structured action the runtime executes |
| MCP | Standard for tools/resources to hosts |
| Skill | Packaged procedure for an agent |
| HITL | Human approval in the loop |
| Test-time compute | Extra inference effort for harder tasks |
| Hallucination | Fluent output without reliable grounding |

---

<!-- layout: 2-column -->
# Must-Fluent vs Nice-to-Know

### Must-fluent Monday
- Token, context, RAG, tool call
- MCP, skill, HITL, hallucination
- Grounding vs training cutoff

### Nice-to-know
- LoRA / SFT flavors
- Rerankers / hybrid search
- Test-time compute dials
- A2A protocol branding

---

# Phrases That Change Vendor Meetings

- “Show me the **tool permission model** and audit log.”
- “How is **ACL-aware retrieval** enforced across deal rooms?”
- “What happens on **low-confidence** retrieval?”
- “Which parts are **model, orchestration, and data platform**?”

> [!TIP]
> Ask for an architecture diagram with trust boundaries—not only a feature list.

---

<!-- layout: navigation -->
# Chapter 9

- What’s Next in AI
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

# Partial Scorecard Example (Dossier Drafting)

| Criterion | Copilot-class surface | IDE / agent runtime (e.g. Cursor) |
| :--- | :--- | :--- |
| Task fit | Strong on docs/email | Strong on skills + tools |
| Grounding | Tenant search / files | Explicit RAG/MCP you wire |
| Agency | Often draft-first | Higher autonomy if configured |
| Security | Enterprise tenant controls | Depends on your allow-lists |
| Operability | IT-managed | Team-owned evals/versioning |
| Economics | Seat-led | Seat + tokens + infra |

> [!TIP]
> Fill this for *one workflow*—not for “AI in general.”

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

<!-- layout: stacked -->
# Build-Your-Stack Logic

1. Rank workflows by value and risk
2. Choose autonomy level you can supervise
3. Separate productivity suite vs. sensitive agent runtimes
4. Demand MCP/API strategy for systems of record
5. Pilot with eval harness + human gates
6. Decide buy/build per layer—not as one monolith

---

<!-- layout: 2-column -->
# Anti-Portfolio (What We Will Not Buy)

### Good “not this year” examples
- Fully autonomous client outreach
- Unbounded production write tools
- Mystery “proprietary brain” with no evals
- One-demo architecture replacements

### Why write an anti-portfolio
- Stops maximalist shopping
- Aligns risk and IT early
- Makes Lab 9 recommendations sharper

---

# TCO Sketch (Finance-Friendly)

| Cost leg | Questions |
| :--- | :--- |
| Seats / SKUs | Who needs which surface? |
| Tokens / inference | Volume × reasoning mode |
| Retrieval infra | Indexing, storage, rerank |
| Integration | APIs, MCP servers, IAM |
| Human review | Minutes per artifact × volume |
| Incident / compliance | Logging, DLP, audit prep |

> [!IMPORTANT]
> Cheap tokens with expensive review (or expensive incidents) is not cheap.

---

# After This Course

- Reuse the vocabulary cheat sheet in vendor meetings
- Convert one workflow into a skill + tool allow-list draft
- Stand up a tiny eval set for your top prompts
- Schedule the human gates before the autonomy
- Name an owner for each pilot

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

**Which diligence question best pressure-tests an AI vendor’s enterprise readiness?**

- A. “Are you on the leaderboard this month?”
- B. “Show the tool permission model, ACL-aware retrieval, and audit logs”
- C. “Can you promise fully autonomous banking with zero errors?”
- D. “Do you have a proprietary brain we cannot inspect?”

---

# Quiz 1 — Answer

**Which diligence question best pressure-tests an AI vendor’s enterprise readiness?**

**Correct: B.** “Show the tool permission model, ACL-aware retrieval, and audit logs”

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
- Inference is running the model; fine-tune specializes weights—not live truth
- Hallucination = fluent output without reliable grounding
- Use the shared vocabulary to keep meetings precise

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
Run a build-your-stack challenge: model providers vs work surfaces (e.g., OpenAI/Anthropic/Google; Copilot/Claude Code/Cursor).

### Discuss
- Which workflows are high-value vs high-risk for your team?
- Where would you invest first—and what autonomy level can you supervise?
- How will you pilot with evals and human gates before scaling?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Run a build-your-stack challenge: model providers vs work surfaces (e.g., OpenAI/Anthropic/Google; Copilot/Claude Code/Cursor).**

### Strong Answers Mention
- Rank workflows by value/risk; separate productivity vs sensitive runtimes
- Demand MCP/API strategy for systems of record
- Pilot with eval harness + gates; decide buy/build per layer
- Defend with criteria from the course—not brand preference alone

### Watch For
- One-demo architecture decisions
- “Fully autonomous” without operability/security evidence
- Ignoring total cost at expected volume

---

# Questions and Answers

Questions?
