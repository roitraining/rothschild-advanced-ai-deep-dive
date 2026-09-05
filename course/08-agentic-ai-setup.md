<!-- course-title: Advanced AI Deep-Dive: Rothschild & Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild & Co

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

<!-- layout: stacked -->
# Five Parts You Must Name

- **Goal / instructions / policy** — what “good” means and what is forbidden
- **Reasoning loop** — plan → act → observe → update
- **Memory** — session vs. durable institutional context
- **Tools & skills** — capabilities and procedures
- **Guardrails** — authZ, HITL, evals, logging

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
| Model | Speed vs. reasoning depth? |
| Temperature / decoding | Creative draft vs. precise extract? |
| Tool allow-list | Minimum viable actions? |
| Knowledge | RAG corpora + live APIs? |
| Memory | What persists across sessions? |
| Limits | Max steps, spend, runtime? |

---

<!-- layout: stacked -->
# Setup Checklist (Debt Advisory Example)

- Mission: monitor → flag restructuring signals → draft dossier
- Inputs: news MCP, filings RAG, internal CRM read tool
- Outputs: structured dossier + source list
- Non-goals: no client outreach, no trading instructions
- Approver: coverage banker before distribution

> [!IMPORTANT]
> Write non-goals. Agents expand to fill ambiguity.

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

# Handoff Contracts

- Explicit artifacts between agents (JSON/markdown schemas)
- Ownership of each stage (who can mark “ready for human”)
- Shared tracing IDs across tool calls
- Stop conditions when confidence or data quality is low

---

<!-- layout: navigation -->
# Chapter 8

- Anatomy of an Agent
- Agent Setup and Configuration
- Orchestration and Multi-Agent (A2A) Patterns
- **Failure Modes and Human-in-the-Loop**

---

<!-- layout: stacked -->
# Failure Modes to Design For

- **Looping** — retries without new information
- **Tool misuse** — wrong API, wrong deal_id
- **Prompt injection** — malicious content in retrieved docs
- **Silent omission** — skipped sources that change the view
- **Overconfidence** — polished dossiers with thin evidence

---

<!-- layout: 2-column -->
# Human-in-the-Loop Patterns

### Gates
- Approve tool classes (send, write)
- Approve external publish
- Approve high-risk retrieval scopes

### Oversight
- Sampling & eval sets
- Escalation on low confidence
- Post-hoc audit reviews

---

<!-- layout: stacked -->
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

# Q&A

Questions?
