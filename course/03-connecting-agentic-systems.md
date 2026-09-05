<!-- course-title: Advanced AI Deep-Dive: Rothschild & Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild & Co

# Chapter 3: Connecting Agentic Systems to Enterprise Tools and Data

---

# Chapter 3: Objectives

- Explain advanced tool use and function calling
- Describe API patterns for enterprise connectivity
- Position MCP as a standard for enterprise context
- Outline live data connections and custom agent skills

---

<!-- layout: navigation -->
# Chapter 3

- **Advanced Tool Use and Function Calling**
- Using APIs for Enterprise Connectivity
- MCP: The Model Context Protocol
- Connecting to Live Enterprise Data Sources
- Writing Custom Agent Skills

---

<!-- layout: stacked -->
# Tools Turn Language into Action

- Without tools, the model can only produce text
- **Function calling**: model proposes a structured tool call; runtime executes it
- Results return to the model for the next step
- This is the core of agentic behavior

> [!IMPORTANT]
> Every tool is a privilege. Design allow-lists as carefully as you design prompts.

---

# Anatomy of a Tool Call

```json
{
  "name": "get_facility_terms",
  "arguments": {
    "deal_id": "DA-2026-0142",
    "fields": ["covenants", "maturity", "agent_bank"]
  }
}
```

- Name + typed arguments → deterministic system execution
- Model chooses **when**; your platform enforces **whether**

---

# Multi-Step Trace: Preliminary Dossier

| Step | Tool / action | Result into context |
| :--- | :--- | :--- |
| 1 | `search_news` | Flagged restructuring headlines |
| 2 | `get_filing_chunk` | Relevant 10-K / RNS excerpts |
| 3 | `get_crm_account` | Coverage owner, prior touches |
| 4 | Draft dossier | Model synthesizes with citations |
| 5 | HITL gate | Banker approves before share |

> [!IMPORTANT]
> If any step lacks an allow-listed tool, the agent should stop—not improvise with prose.

---

<!-- layout: 2-column -->
# Tool Design Anti-Patterns

### Dangerous
- God-query “run any SQL”
- Silent writes to CRM
- Tools that return secrets/PII raw
- One tool that emails externally

### Better
- Narrow, intention-revealing APIs
- Read vs write separated
- Redact before prompt/logs
- Explicit send tool + HITL

---

<!-- layout: navigation -->
# Chapter 3

- Advanced Tool Use and Function Calling
- **Using APIs for Enterprise Connectivity**
- MCP: The Model Context Protocol
- Connecting to Live Enterprise Data Sources
- Writing Custom Agent Skills

---

# APIs Are the Enterprise Nervous System

- CRM, DMS, market data, HRIS, data warehouse—all speak HTTP/APIs
- Agents should call **approved APIs**, not scrape internal UIs
- Auth: OAuth, service accounts, short-lived tokens, mTLS where required
- Observability: log tool name, actor, resource, and outcome

---

<!-- layout: 2-column -->
# Integration Patterns

### Synchronous
- Request/response in the agent turn
- Good for lookups and validation
- Watch latency budgets

### Asynchronous
- Queue jobs, poll or webhook
- Good for long research packs
- Needs status UX and timeouts

---

# API Design for Agents

- Prefer **narrow, intention-revealing** endpoints over god-queries
- Return machine-readable fields + human labels
- Include stable IDs for citations (`doc_id`, `clause_id`)
- Fail with clear errors the model can recover from—or escalate

---

<!-- layout: navigation -->
# Chapter 3

- Advanced Tool Use and Function Calling
- Using APIs for Enterprise Connectivity
- **MCP: The Model Context Protocol**
- Connecting to Live Enterprise Data Sources
- Writing Custom Agent Skills

---

<!-- layout: title-image -->
# MCP: Model Context Protocol

![MCP architecture](images/ch03-mcp-architecture.svg)

---

# Why MCP Matters

- Standard way for hosts (IDEs, copilots, agents) to discover **tools** and **resources**
- Reduces one-off plugins for every client application
- Keeps capability definitions close to the data service
- Improves portability across agent runtimes

> [!NOTE]
> MCP is plumbing and product strategy—not a model. It does not replace IAM.

---

# MCP Building Blocks

| Concept | Role |
| :--- | :--- |
| Host | App that runs the agent (e.g., IDE, copilot) |
| Client | Connector inside the host |
| Server | Exposes tools/resources for a domain system |
| Tools | Actions the model may invoke |
| Resources | Readable context (files, records, schemas) |

---

<!-- layout: 2-column -->
# MCP Gives You / Does Not Give You

### Gives you
- Portable discovery of tools & resources
- Capability definitions near the data service
- Less one-off plugin sprawl per host app

### Does not give you
- IAM / row-level security by magic
- Tenancy across deal rooms
- Safe defaults for write/send
- Immunity to prompt injection

---

<!-- layout: navigation -->
# Chapter 3

- Advanced Tool Use and Function Calling
- Using APIs for Enterprise Connectivity
- MCP: The Model Context Protocol
- **Connecting to Live Enterprise Data Sources**
- Writing Custom Agent Skills

---

# Live Data: Databases and Beyond

- Pattern: agent → tool/MCP → **service layer** → database
- Avoid giving the model raw SQL superpowers on production
- Use parameterized queries, views, and row-level security
- Separate read paths (research) from write paths (updates)

---

<!-- layout: stacked -->
# Secure Live Connectivity

- Authenticate the **user or service**, not “the LLM”
- Enforce least privilege per tool
- Redact secrets and PII before they enter prompts/logs
- Cache carefully—stale positions and caps are risk events

<!-- TODO IMAGE: Screenshot of an enterprise API gateway policy for an AI tool identity -->
![API gateway policy placeholder](images/ch03-api-gateway-policy-screenshot.svg)

---

<!-- layout: 2-column -->
# Identity Propagation Matters

### User token
- Acts as the banker
- Inherits deal-room ACL
- Auditable to a person

### Service account
- Shared bot identity
- Easy to over-privilege
- Cross-deal blast radius if mis-scoped

> [!WARNING]
> A CRM read as “ai-bot-prod” with firm-wide scope is how confidential coverage leaks.

---

<!-- layout: navigation -->
# Chapter 3

- Advanced Tool Use and Function Calling
- Using APIs for Enterprise Connectivity
- MCP: The Model Context Protocol
- Connecting to Live Enterprise Data Sources
- **Writing Custom Agent Skills**

---

# What Is a Skill?

- Packaged instructions + optional scripts/references for a recurring job
- Teaches the agent **how your firm does the work**
- Complements tools: skills guide procedure; tools execute side effects
- Versioned like code: owners, reviews, rollback

---

<!-- layout: 2-column -->
# Skill Design Checklist

### Specify
- Trigger: when should this skill load?
- Inputs/outputs and definition of done
- Examples of good and bad runs

### Constrain
- Allowed tools and forbidden actions
- Escalation path to a human
- Start with one high-value workflow first

---

# Mini Skill Skeleton (Preliminary Dossier)

```text
name: preliminary-dossier
trigger: "draft dossier" / Debt Advisory intake
tools: [search_news, get_filing_chunk, get_crm_account]
forbidden: [send_email, crm_write]
inputs: company, jurisdiction, asking_team
output: dossier.md + sources[] + gaps[]
non_goals: no client outreach; no investment recommendation
done_when: citations present OR explicit "insufficient sources"
escalate_to: coverage banker
```

---

# Lab 3: Blueprinting a Custom Agent

**Time:** 30 minutes

**Lab guide:** [Lab 3 instructions](labs/lab-03-agent-blueprint.md)

---

# What You Learned

- Explained advanced tool use and function calling
- Described API patterns for enterprise connectivity
- Positioned MCP as a standard for enterprise context
- Outlined live data connections and custom agent skills

---

# Quiz 1 of 3

**In function calling, what does the model actually do versus the runtime?**

- A. The model directly executes SQL on production with no intermediary
- B. The model proposes a structured tool call; the runtime executes and returns results
- C. The runtime invents tool arguments; the model only formats prose
- D. Function calling removes the need for authentication

---

# Quiz 1 — Answer

**In function calling, what does the model actually do versus the runtime?**

**Correct: B.** The model proposes a structured tool call; the runtime executes and returns results

- Tools turn language into action; execution stays in your controlled runtime
- The model chooses *when*; the platform enforces *whether*
- Every tool is a privilege—design allow-lists carefully
- Auth still binds to user/service identity, not “the LLM”

---

# Quiz 2 of 3

**What is the best characterization of MCP (Model Context Protocol) for enterprise use?**

- A. A replacement for IAM and row-level security
- B. A new frontier model trained on your CRM
- C. A standard for hosts to discover tools/resources from servers near data systems
- D. A guarantee that prompts cannot be injected

---

# Quiz 2 — Answer

**What is the best characterization of MCP (Model Context Protocol) for enterprise use?**

**Correct: C.** A standard for hosts to discover tools/resources from servers near data systems

- MCP is plumbing/product strategy—portable tool and resource discovery
- It does not replace IAM, DLP, or approval design
- Value: fewer one-off plugins; permissions stay with the data service
- Prompt injection remains a threat to design for

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
Blueprint an agent that drafts a preliminary dossier using CRM fields and a document store.

### Discuss
- Which capabilities should be tools/APIs vs packaged as a skill?
- How should live database access be mediated (what must the agent *not* get)?
- Where do human approval gates belong before anything is shared?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Blueprint an agent that drafts a preliminary dossier using CRM fields and a document store.**

### Strong Answers Mention
- Skills guide procedure; tools execute side effects
- Agent → service layer → DB; no raw production SQL superpowers
- Least privilege, redaction, audit of tool calls
- Approve before client-visible distribution

### Watch For
- God-query tools with write access “for convenience”
- Skills without non-goals or escalation paths
- Assuming MCP alone makes the design secure

---

# Questions and Answers

![Questions and Answers](images/qa.png)
