<!-- course-title: Advanced AI Deep-Dive: Rothschild and Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild and Co

# Chapter 8: Agentic AI – Setup and Orchestration

---

# Chapter 8: Objectives

- Describe the anatomy of an AI agent
- Configure goals, tools, memory, and policies deliberately
- Compare orchestration and multi-agent (A2A) patterns
- Anticipate failure modes and design human-in-the-loop controls

---

<!-- layout: navigation -->
# Chapter 8

- **Anatomy of an Agent**
- Agent Setup and Configuration
- Orchestration and Multi-Agent (A2A) Patterns
- Failure Modes and Human-in-the-Loop

---

<!-- layout: title-image -->
# Anatomy of an Agent

![Agent anatomy](images/ch08-agent-anatomy.svg)

---

# Five Parts You Must Name

- **Goal / instructions / policy** — what "good" means and what is forbidden
- **Reasoning loop** — plan → act → observe → update
- **Memory** — session vs durable institutional context
- **Tools and skills** — capabilities and procedures
- **Guardrails** — authZ, HITL, evals, logging

> [!IMPORTANT]
> Name all five or the system invents the missing ones.

---

<!-- layout: 2-column -->
# Tools vs Skills

### Tools = capabilities
- APIs and actions the runtime can call
- Often exposed via MCP / function calls
- Examples: CRM read, filings search, calendar
- Scope with allow-lists and schemas

### Skills = packaged playbooks
- Named procedures with triggers and steps
- Explicit **non-goals** and stop conditions
- Example: "Draft Debt Advisory dossier"
- Version, eval, and roll back like code

> [!TIP]
> A tool is *what* the agent can touch. A skill is *how* it should work a job end-to-end.

---

<!-- layout: navigation -->
# Chapter 8

- Anatomy of an Agent
- **Agent Setup and Configuration**
- Orchestration and Multi-Agent (A2A) Patterns
- Failure Modes and Human-in-the-Loop

---

# Configuration Levers

| Lever | Questions |
| :--- | :--- |
| Model | Speed vs reasoning depth? |
| Temperature / decoding | Creative draft vs precise extract? |
| Tool allow-list | Minimum viable actions? |
| Knowledge | RAG corpora + live APIs? |
| Memory | What persists across sessions? |
| Limits | Max steps, spend, runtime? |

---

# One-Page Agent Spec (Debt Advisory)

| Spec field | Debt Advisory example |
| :--- | :--- |
| Mission | Monitor → flag restructuring signals → draft dossier |
| Inputs | News MCP, filings RAG, CRM read tool |
| Outputs | Structured dossier + source list |
| Tools (via MCP) | Read-mostly MCP servers; no send/trade |
| Facts (via RAG) | ACL-aware deal room + approved filings corpus |
| Non-goals | No client outreach; no trading instructions |
| Memory | Session only; no cross-deal durable notes |
| Evals | Citation rate; tool-call correctness; false-flag rate |
| HITL | Coverage banker approves before distribution |

> [!IMPORTANT]
> Write non-goals. Agents expand to fill ambiguity.

---

<!-- layout: 2-column -->
# Spec Callbacks: MCP and RAG

### Tools via MCP
- Bind each allow-listed action to an MCP server / tool
- Identity, scopes, and audit travel with the call
- Prefer read tools first; gate writes and sends
- Ask vendors: permission model + immutable logs

### Facts via RAG
- Material claims come from retrieved chunks — not memory fluff
- Enforce ACL at retrieval time (deal room / mandate)
- Cite-or-refuse on thin or conflicting sources
- Ask vendors: freshness, filters, low-confidence path

> [!NOTE]
> Spec without MCP and RAG callbacks is abstract config — not an operable agent.

---

# Memory Risks

- Durable memory can **leak context across deals or clients**
- "Helpful" recall may surface the wrong mandate or counterparty
- Prefer session memory plus explicit RAG with ACL
- If durable memory exists: tenant, deal-room, and purge rules are mandatory

> [!CAUTION]
> Institutional memory without ACL is a confidentiality incident waiting to happen.

---

<!-- layout: navigation -->
# Chapter 8

- Anatomy of an Agent
- Agent Setup and Configuration
- **Orchestration and Multi-Agent (A2A) Patterns**
- Failure Modes and Human-in-the-Loop

---

<!-- layout: title-image -->
# Multi-Agent (A2A) Patterns

![Multi-agent deal sourcing](images/ch08-multi-agent.svg)

---

# Walkthrough: Debt Advisory Roles

Map the diagram boxes to dossier jobs — same workflow, named ownership.

| Diagram box | Dossier job | What it owns |
| :--- | :--- | :--- |
| News Monitor + Restructuring Scout | **Research** | Signals, sources, flags |
| Dossier Compiler | **Draft** | Structured brief + citations |
| Critic hop (add if multi-agent) | **Critic** | Challenge thin claims; cite-or-refuse |
| Human approval bar | **Compliance HITL** | Banker gate before distribution |
| Orchestrator | Routes stages; owns stop conditions | Trace IDs and handoff contracts |

> [!TIP]
> If you cannot name who owns research, draft, critic, and HITL, do not ship multi-agent yet.

---

<!-- layout: 3-column -->
# Common Topologies

### Single agent
- One loop, many tools
- Simpler ops
- Can get overloaded

### Supervisor
- Orchestrator delegates
- Clear specialization
- Needs handoff contracts

### Peer / swarm
- Agents collaborate
- Flexible, harder to audit
- Use sparingly

---

<!-- layout: 2-column -->
# Multi-Agent: When and When Not

### Prefer single agent
- One workflow, one artifact
- Clear, small tool set
- Audit story must stay simple
- Split only when overload is proven

### Prefer multi-agent
- Clean specialist handoffs
- Parallel research lanes
- Shared schemas and traces ready
- Supervisor owns stop conditions

---

<!-- layout: 2-column -->
# A2A Honesty and Handoffs

### A2A reality
- Interoperability ambition; products still evolving
- Most banks ship supervisor + specialists today
- Ask: standardized vs proprietary messaging?
- Buy the topology you can operate this year

### Handoff contracts
- Explicit JSON/markdown artifacts
- Named owner per stage
- Shared tracing IDs
- Stop on low confidence / bad data

> [!NOTE]
> Design for auditable handoffs — not logo diagrams.

---

<!-- layout: navigation -->
# Chapter 8

- Anatomy of an Agent
- Agent Setup and Configuration
- Orchestration and Multi-Agent (A2A) Patterns
- **Failure Modes and Human-in-the-Loop**

---

# Failure → Control Pairings

| Failure mode | Control |
| :--- | :--- |
| Looping / retries with no new info | Step budget + kill switch |
| Tool misuse (wrong API / deal_id) | Allow-list + schema validation |
| Prompt injection via retrieved docs | Instruction hierarchy + retrieval filters |
| Silent omission of key sources | Required source checklist / cite-or-refuse |
| Overconfident thin dossiers | HITL gate + evidence-density eval |

---

<!-- layout: 2-column -->
# Human-in-the-Loop Patterns

### Gates
- Approve tool classes (send, write)
- Approve external publish
- Approve high-risk retrieval scopes

### Oversight
- Sampling and eval sets
- Escalation on low confidence
- Post-hoc audit reviews

---

<!-- layout: 3-column -->
# Agent Evals (Beyond Final Answers)

### Trajectory
- Did the plan make sense?
- Unnecessary loops?
- Recovery after errors?

### Tool calls
- Right tool?
- Right args / deal_id?
- Right order?

### Policy
- Inside non-goals?
- Allow-list respected?
- HITL gates hit?

> [!TIP]
> A pretty answer from a bad trajectory is still a bad agent.

---

# Practical Control Board

- Step budget and kill switch
- Dual control for anything client-visible
- Immutable logs for model, tools, and retrieved chunks
- Rollback: pin skill/model versions that misbehaved

---

<!-- layout: 2-column -->
# Day 2 Pace and Vendor Questions

### Must-run if time slips
- Failure modes + HITL pairings
- Lab 8 blueprint (non-goals first)
- Cut deep multi-agent / A2A variants first

### Killer vendor questions (bank)
- Show tool permission model and audit log
- How is ACL-aware retrieval enforced?
- What happens on low-confidence retrieval?
- Where are HITL gates — and can they be bypassed?
- Max steps, spend, and kill switch — who owns them?

> [!IMPORTANT]
> Protect failure modes, HITL, and the lab. Fancy topology slides are optional.

---

# Lab Bridge: Spec Order Matters

Before you list tools in Lab 8, lock the guardrails:

1. **Non-goals** — what the agent must never do (outreach, trade, cross-deal memory)
2. **HITL gates** — who approves what before distribution or write/send
3. **Then** tools / MCP allow-list and RAG corpora
4. Only then consider multi-agent splits

> [!WARNING]
> Tools-first specs drift into maximalist agents. Non-goals and gates first keep the blueprint bankable.

---

# Lab 8: Designing a Deal-Sourcing Agent

**Time:** 30 minutes

**Lab guide:** [Lab 8 instructions](labs/lab-08-deal-sourcing-agent.md)

---

# What You Learned

- Described the anatomy of an AI agent
- Configured goals, tools, memory, and policies deliberately
- Compared orchestration and multi-agent (A2A) patterns
- Anticipated failure modes and designed human-in-the-loop controls

---

# Quiz 1 of 3

**Your Debt Advisory dossier is one artifact, a small read-mostly tool set, and a simple audit story. When should you *not* go multi-agent?**

- A. Never — multi-agent is always better for banking
- B. Prefer single-agent until specialization or overload is proven
- C. Immediately add a peer swarm for "flexibility"
- D. Split only to avoid writing non-goals and HITL gates

---

# Quiz 1 — Answer

**Your Debt Advisory dossier is one artifact, a small read-mostly tool set, and a simple audit story. When should you *not* go multi-agent?**

**Correct: B.** Prefer single-agent until specialization or overload is proven

- Multi-agent needs handoff contracts, shared traces, and named owners per stage
- Extra agents without proven overload add blast radius and audit cost
- Research / draft / critic / HITL can be roles inside one loop first
- Topology follows the job — not the vendor diagram

---

# Quiz 2 of 3

**A dossier agent starts looping on thin news, then mis-calls CRM with the wrong deal_id. Which failure mode do you fix *first* before expanding tools?**

- A. Remove HITL so the loop can "finish faster"
- B. Step budget / kill switch and tool schema validation — then reassess
- C. Add durable cross-deal memory so it "remembers" the right id
- D. Grant write/send tools so it can correct CRM itself

---

# Quiz 2 — Answer

**A dossier agent starts looping on thin news, then mis-calls CRM with the wrong deal_id. Which failure mode do you fix *first* before expanding tools?**

**Correct: B.** Step budget / kill switch and tool schema validation — then reassess

- Pair failures with controls before adding capability
- Looping without new info burns spend and hides bad trajectories
- Wrong deal_id is allow-list + schema validation — not more memory
- Expanding tools or skipping HITL amplifies the same failure

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
Design a system that monitors news, flags restructuring opportunities, and drafts dossiers.

### Discuss
- Single agent vs multi-agent — which and why?
- What artifact schema do you pass between stages?
- Where must a human approve — and what are hard non-goals?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Design a system that monitors news, flags restructuring opportunities, and drafts dossiers.**

### Strong Answers Mention
- Start single-agent unless specialization is proven; supervisor + specialists if split
- Explicit JSON/markdown handoffs; stop on low confidence/data quality
- Read-mostly tools via MCP; facts via RAG; no outreach/trading as non-goals
- Dual control for client-visible outputs; full audit trail; session-scoped memory

### Watch For
- Swarm designs with no audit story
- Tools list before non-goals and HITL
- Durable memory leaking across deals
- Polished dossiers with thin evidence and no gate

---

# Questions and Answers

Questions?
