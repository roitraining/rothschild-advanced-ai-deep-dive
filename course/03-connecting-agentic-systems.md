<!-- course-title: Advanced AI Deep-Dive: Rothschild and Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild and Co

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
  "name": "get_loan_terms",
  "arguments": {
    "deal_id": "DA-2026-0142",
    "fields": ["loan_conditions", "maturity", "agent_bank"]
  }
}
```

- Name + typed arguments → deterministic system execution
- Model chooses **when**; your platform enforces **whether**

---

<!-- layout: 3-column -->
# Custom API vs MCP vs Host Plugin

### Custom API (direct)
- Tight control for one agent runtime
- Best when CRM/DMS contracts are firm-owned
- You own clients, auth, and versioning

### MCP server
- Portable tools/resources across hosts
- Wins when multiple copilots need the same CRM/DMS surface
- Still needs IAM at the service layer

### Host plugin
- Fastest for one vendor surface
- Fine for productivity SKUs
- Watch lock-in and opaque permissions

> [!TIP]
> Same CRM data, three packaging choices—pick for **reuse and control**, not fashion.

---

# Multi-Step Trace: Preliminary Client Briefing

| Step | Tool / action | Result into context |
| :--- | :--- | :--- |
| 1 | `search_news` | Flagged restructuring headlines |
| 2 | `get_filing_chunk` | Relevant annual-report / RNS excerpts |
| 3 | `get_crm_account` | Client-team owner, prior touches |
| 4 | Draft client briefing | Model synthesizes with citations |
| 5 | HITL gate | Advisor approves before share |

> [!IMPORTANT]
> If any step lacks an allow-listed tool, the agent should stop—not improvise with prose.

---

# Teachable Moment: Tool-Enabled Exfiltration

- Attacker (or poisoned doc) tricks the model into **calling** `send_email` or a broad CRM read
- The model “helps”—the blast radius is your allow-list, not the prose tone
- Narrow tools + HITL on send/write beat clever prompts alone
- Log every tool call: name, actor, resource, outcome

> [!CAUTION]
> Exfiltration often looks like a successful agent turn. Design tools as if the model will be tricked.

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
# Finance-Concrete API Patterns

### Sync lookup (watch latency)
- Loan-condition field or CRM owner in the agent turn
- Market-data spikes can **kill the turn**—budget timeouts
- Prefer cached/approved snapshots when live feed is slow

### Async research pack
- Long client-briefing packs: queue job, poll or webhook
- Needs **status UX** (“gathering company reports…”) and timeouts
- Do not block the advisor on a 10-minute silent wait

---

# API Design for Agents

- Prefer **narrow, intention-revealing** endpoints over god-queries
- Return machine-readable fields + human labels; stable IDs for citations
- Fail with clear errors the model can recover from—or escalate
- Separate read paths (research) from write/send paths (HITL)

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
- Portable discovery of tools and resources
- Capability definitions near the data service
- Less one-off plugin sprawl per host app

### Does not give you
- IAM / row-level security by magic
- Tenancy across secure deal folders
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
- Acts as the advisor
- Inherits secure deal-folder ACL
- Auditable to a person

### Service account
- Shared bot identity
- Easy to over-privilege
- Cross-deal blast radius if mis-scoped

> [!WARNING]
> A CRM read as “ai-bot-prod” with firm-wide scope is how confidential client-team data leaks.

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

# Mini Skill Skeleton (Preliminary Client Briefing)

```text
name: preliminary-client-briefing
trigger: "draft client briefing" / Debt Advisor intake
tools: [search_news, get_filing_chunk, get_crm_account]
forbidden: [send_email, crm_write]
inputs: company, jurisdiction, asking_team
output: briefing.md + sources[] + gaps[]
non_goals: no client outreach; no investment recommendation
done_when: citations present OR explicit "insufficient sources"
escalate_to: client-team advisor
```

---

<!-- layout: 2-column -->
# Bad Skill Anti-Example

### Vague and unsafe
- Trigger: “help with deals” (always on)
- Tools: whatever the host exposes
- No forbidden list, no non-goals
- Done when: “looks good”

### What breaks
- Loads on every chat; over-privileged
- Silent CRM writes or external send
- No escalate path when sources are thin
- Lab blueprints fail review for this shape

> [!WARNING]
> A skill without **forbidden** and **non_goals** is a privilege leak with a friendly name.

---

# Lab Bridge: Fill the Blueprint Skeleton

- Treat the lab like a **mini skill**: tools, forbidden, done_when, escalate
- Name inputs/outputs and non-goals before you debate model brands
- If a step needs a side effect, it needs an allow-listed tool—or it is out of scope
- Peer-review each other’s blueprints for vague triggers and missing gates

> [!TIP]
> Copy the preliminary-client-briefing skeleton shape—swap in your team’s workflow.

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
A peer team’s blueprint allows `crm_read_all`, `crm_write`, and `send_email`, with trigger “assist on any deal question” and no forbidden list.

### Discuss
- What over-privilege and exfiltration paths do you see?
- How would you rewrite tools, forbidden, done_when, and escalate?
- Where must HITL sit before anything leaves the firm?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**A peer team’s over-privileged “assist on any deal” blueprint.**

### Strong Answers Mention
- Broad CRM read + write + send is classic tool-enabled exfiltration
- Narrow intention-revealing tools; separate read vs write/send
- Add forbidden, non_goals, cite-or-refuse done_when, escalate_to
- HITL before external send and before CRM writes

### Watch For
- “MCP / host plugin will fix permissions” without IAM
- Vague triggers that load the skill on every chat
- Cloning the lab client-briefing scenario without critiquing privilege

---

# Questions and Answers

Questions?
