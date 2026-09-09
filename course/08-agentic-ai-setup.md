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
| Tools | Read-mostly; no send/trade |
| Non-goals | No client outreach; no trading instructions |
| Memory | Session only; no cross-deal durable notes |
| Evals | Citation rate; tool-call correctness; false-flag rate |
| HITL | Coverage banker approves before distribution |

> [!IMPORTANT]
> Write non-goals. Agents expand to fill ambiguity.

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

**Which set best captures the anatomy of an agent?**

- A. UI theme, font size, and color palette only
- B. Goal/policy, reasoning loop, memory, tools/skills, and guardrails
- C. A single prompt with no tools and no stop conditions
- D. Unlimited credentials plus a larger context window

---

# Quiz 1 — Answer

**Which set best captures the anatomy of an agent?**

**Correct: B.** Goal/policy, reasoning loop, memory, tools/skills, and guardrails

- Name all five parts or the system invents the missing ones
- Configuration levers: model, decoding, allow-lists, knowledge, memory, step/spend limits
- Write non-goals; agents expand to fill ambiguity
- Guardrails include authZ, HITL, evals, and logging

---

# Quiz 2 of 3

**For a multi-agent deal-sourcing system, which failure mode design is most important?**

- A. Remove all human gates to maximize throughput
- B. Ignore prompt injection because retrieval is internal
- C. Plan for looping, tool misuse, injection, silent omission, and overconfidence — with HITL gates
- D. Give every agent identical broad write permissions

---

# Quiz 2 — Answer

**For a multi-agent deal-sourcing system, which failure mode design is most important?**

**Correct: C.** Plan for looping, tool misuse, injection, silent omission, and overconfidence — with HITL gates

- Pair each failure with a control (step budget, allow-lists, filters, cite-or-refuse)
- Supervisor topologies need handoff contracts and shared trace IDs
- Dual control for client-visible outputs; no outreach without banker approval
- Eval trajectories and tool calls — not only final dossiers

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
- Read-mostly tools; no outreach/trading instructions as non-goals
- Dual control for client-visible outputs; full audit trail; session-scoped memory

### Watch For
- Swarm designs with no audit story
- Unbounded steps/spend
- Durable memory leaking across deals
- Polished dossiers with thin evidence and no gate

---

# Questions and Answers

Questions?
