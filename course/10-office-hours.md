<!-- course-title: Advanced AI Deep-Dive: Rothschild and Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild and Co

# Chapter 10: Instructor Office Hours and Questions and Answers

---

# Chapter 10: Objectives

- Bring work-specific questions to a structured open forum
- Map each question to model / data / tools / controls
- Leave with clearer next steps on concepts and potential projects

---

<!-- layout: navigation -->
# Chapter 10

- **Open Forum**
- Question Shapes and Intake
- Triage Live

---

# Facilitator Run-of-Show

| Block | Timebox | What happens |
| :--- | :--- | :--- |
| Intake | 5–8 min | Capture scenarios on the persistent intake slide |
| Triage | 5 min | Rank by risk × urgency; park the rest |
| Deep-dives | bulk of block | Map each to Model / Data / Tools / Controls |
| Parking lot | ongoing | Owner + next step for anything that leaves unfinished |
| Close | 5 min | Exit checks + confirm follow-ups that leave the room |

> [!TIP]
> Prefer fewer deep scenarios over a long shallow queue.

---

# How Office Hours Work

- Open queue: deal, research, ops, risk, and vendor questions welcome
- Prefer **concrete scenarios** over abstract debates
- We map every question to: **Model / Data / Tools / Controls**
- Parking lot for items that need follow-up materials — with a named owner

---

# Persistent Intake (Write Before / During Day)

Keep one row ready all day — fill it early so office hours are not cold-start.

| Field | Your note |
| :--- | :--- |
| Workflow | |
| Data involved | |
| Risk if wrong | |
| Constraint (residency / tool / policy) | |
| Decision needed | |
| Killer question for vendor / eng | |

> [!IMPORTANT]
> Blank intake = slower triage. Capture something — even a half-formed claim to teardown.

---

<!-- layout: navigation -->
# Chapter 10

- Open Forum
- **Question Shapes and Intake**
- Triage Live

---

<!-- layout: 2-column -->
# Good Question Shapes

### Strong
- "We have X data and Y risk — what architecture fits?"
- "How would you gate tool Y before client send?"
- "Where does this claim fail: model, data, or controls?"

### Weaker
- "Is AI good for banking?"
- "Which model is best forever?"
- "Can we automate everything next quarter?"

---

# Seeded Fallback Scenarios

If the room brings nothing, facilitate from these (Debt Advisory dossier spine):

| Scenario | Focus |
| :--- | :--- |
| **Dossier agent overreach** | Agent drafts *and* wants to email clients — non-goals, HITL, tool allow-list |
| **RAG wrong-deal** | Retrieved chunks from Mandate B into Mandate A brief — ACL, cite-or-refuse, memory |
| **Vendor pitch teardown** | "Fully autonomous dossier" claim through scorecard + claim → source → check → human gate |

> [!NOTE]
> Use fallbacks after a real intake pass — not instead of asking for participant scenarios.

---

<!-- layout: navigation -->
# Chapter 10

- Open Forum
- Question Shapes and Intake
- **Triage Live**

---

<!-- layout: 3-column -->
# Live Triage Rubric

### Model
- Task fit?
- Reasoning needed?
- Eval evidence?

### Data
- Corpus / ACL?
- Freshness?
- Citations?

### Tools / Controls
- Allow-list?
- Identity?
- HITL gate?

---

# Popular Deep-Dive Themes

- MCP vs custom APIs for internal systems
- RAG design for deal rooms and research corpora
- Multi-agent blueprints for coverage teams
- Eval strategies for hallucination and policy breaches
- Copilot / IDE / agent runtime boundaries

---

# Parking Lot: Ownership

Nothing useful leaves as "we should talk later" without a name.

| Item | Owner (in room) | What leaves the room |
| :--- | :--- | :--- |
| Architecture sketch | | One-pager or follow-up email |
| Vendor diligence | | Scorecard + 3 killer questions |
| Policy / residency | | Named contact + next meeting |
| Eval / HITL design | | Gate list for the workflow |

> [!WARNING]
> Unowned parking-lot items die after class. Assign before you close.

---

# Exit Checks

Can you leave able to do these — not just "having heard" them?

- [ ] **Teardown a pitch** — map a claim to model / data / tools / controls and demand evidence
- [ ] **Blueprint a safer agent** — non-goals, MCP/RAG callbacks, HITL gates before tools sprawl
- [ ] **Ask residency / HITL questions** — where data sits, who approves irreversible or client-visible acts
- [ ] **Run claim → source → check → human gate** on multimodal or agent outputs
- [ ] **Own one follow-up** from the parking lot (or know who does)

---

# Questions and Answers

Questions?
