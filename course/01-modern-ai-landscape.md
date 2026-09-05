<!-- course-title: Advanced AI Deep-Dive: Rothschild & Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild & Co

# Chapter 1: The Modern AI Landscape

---

# Chapter 1: Objectives

- Describe the generative AI stack from models to agents
- Compare open-weight and closed models for enterprise fit
- Explain the shift from chatbots to agentic systems
- Separate marketing hype from technical capability claims

---

<!-- layout: navigation -->
# Chapter 1

- **The Generative AI Stack**
- Open Weight vs. Closed Models
- From Chatbots to Agentic Systems
- Separating Hype from Technical Reality

---

<!-- layout: title-image -->
# The Generative AI Stack

![Generative AI stack](images/ch01-genai-stack.svg)

---

<!-- layout: stacked -->
# Stack Layers That Matter

- **Applications & agents** — what users see and run
- **Orchestration & tools** — APIs, MCP, RAG, skills, guardrails
- **Model layer** — frontier, open-weight, specialized, multimodal
- **Data & infrastructure** — embeddings, warehouses, permissions
- **Foundation** — identity, network, audit, vendor trust

> [!IMPORTANT]
> Vendor demos often start at the app layer. Your diligence must reach data and controls.

---

# Finance Lens on the Stack

- A deal briefing copilot is an **application**, not “the model”
- Quality depends on **which data** it can retrieve and **which tools** it may call
- Model choice is one decision among many (latency, residency, cost, evals)
- Architecture conversations should name each layer explicitly

---

<!-- layout: navigation -->
# Chapter 1

- The Generative AI Stack
- **Open Weight vs. Closed Models**
- From Chatbots to Agentic Systems
- Separating Hype from Technical Reality

---

<!-- layout: title-image -->
# Open Weight vs. Closed Models

![Open vs closed models](images/ch01-open-vs-closed.svg)

---

<!-- layout: 2-column -->
# Decision Criteria

### Capability & cadence
- Closed APIs often lead on frontier reasoning
- Open-weight catches up unevenly by task
- Eval on **your** finance prompts, not leaderboards alone

### Control & operations
- Open-weight: stronger data-path control, you run ops
- Closed: contract, DPA, and tenant controls matter
- Hybrid is common: productivity vs. sensitive workloads

---

# What “Open” Does Not Mean

- **Open-weight ≠ free for any use** — licenses still constrain redistribution and commercial use
- **Self-hosted ≠ automatically safer** — misconfigured access still leaks data
- **Closed ≠ unusable in regulated settings** — enterprise offerings may meet residency and audit needs
- Ask: *Where do prompts, documents, and logs live?*

---

<!-- layout: navigation -->
# Chapter 1

- The Generative AI Stack
- Open Weight vs. Closed Models
- **From Chatbots to Agentic Systems**
- Separating Hype from Technical Reality

---

<!-- layout: stacked -->
# From Chatbots to Agentic Systems

- A chatbot answers one prompt at a time—you drive every step
- An agent pursues a goal: it plans, acts, checks results, and keeps going
- The shift is giving the model a loop, tools, and permission to act

![From chatbots to agents](images/chatbots-to-agents.png)

---

# Autonomy Spectrum (Finance)

| Mode | Example | Human role |
| :--- | :--- | :--- |
| Assist | Draft client email from notes | Edit every word |
| Copilot | Summarize CIM sections on demand | Steer each request |
| Agent | Monitor news → flag opportunities → draft dossier | Approve gates |
| Multi-agent | Specialist agents + orchestrator | Own policy & outcomes |

> [!TIP]
> Buy for the autonomy level you can supervise—not the autonomy level in the pitch deck.

---

<!-- layout: navigation -->
# Chapter 1

- The Generative AI Stack
- Open Weight vs. Closed Models
- From Chatbots to Agentic Systems
- **Separating Hype from Technical Reality**

---

# Hype Patterns to Spot

- **“Our model understands your firm”** — usually retrieval + prompts, not magic memory
- **“Fully autonomous banking AI”** — missing failure modes and approval design
- **“Trained on all market data”** — ask provenance, freshness, and licenses
- **“Guaranteed accuracy”** — probabilistic systems need grounding and review

---

<!-- layout: 3-column -->
# Diligence Questions

### Model
- Task benchmarks?
- Context limits?
- Reasoning mode?

### Data
- What is indexed?
- Who can access?
- Retention policy?

### Control
- Tool permissions?
- Audit logs?
- Human gates?

---

<!-- layout: 2-column -->
# Technical Reality Check

### What models do
- Predict useful continuations
- Do not “know” your deal room
- Amplify productivity and blast radius

### What you must demand
- Connections + controls, not chat alone
- Architectures explainable to risk and IT
- Clear autonomy you can supervise

---

# Lab 1: Model Face-Off

**Time:** 25 minutes

**Lab guide:** [Lab 1 instructions](labs/lab-01-model-face-off.md)

---

# What You Learned

- Described the generative AI stack from models to agents
- Compared open-weight and closed models for enterprise fit
- Explained the shift from chatbots to agentic systems
- Separated marketing hype from technical capability claims

---

# Quiz 1 of 3

**In the generative AI stack, which layer is where APIs, MCP, RAG, skills, and guardrails typically live?**

- A. Foundation (identity and network only)
- B. Model layer
- C. Orchestration and tools
- D. Applications and agents only

---

# Quiz 1 — Answer

**In the generative AI stack, which layer is where APIs, MCP, RAG, skills, and guardrails typically live?**

**Correct: C.** Orchestration and tools

- Orchestration is where enterprise data and controls attach to the model
- Applications are what users see; models are one capability choice among many
- Foundation covers identity, network, audit, and trust boundaries—not tool wiring
- Diligence must reach below the demo UI into this layer

---

# Quiz 2 of 3

**A vendor says their “fully autonomous banking AI” needs no human review. What is the strongest technical response?**

- A. Agree—frontier models eliminated hallucination
- B. Autonomy is a spectrum; agentic systems amplify blast radius and still need gates
- C. Open-weight models never require review
- D. Autonomy only matters during the coding phase of a project

---

# Quiz 2 — Answer

**A vendor says their “fully autonomous banking AI” needs no human review. What is the strongest technical response?**

**Correct: B.** Autonomy is a spectrum; agentic systems amplify blast radius and still need gates

- Chatbots answer one prompt; agents pursue goals with tools and permission to act
- More autonomy without controls increases risk, not just productivity
- Open vs closed is about control and ops—not a substitute for human gates
- Buy for the autonomy level you can supervise

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
Pick one Rothschild workflow (for example: research brief, deal dossier, or client email draft).

### Discuss
- At which stack layer does most of the risk actually live for that workflow?
- Would you prefer open-weight, closed/API, or hybrid—and why?
- What hype claim would you challenge first in a vendor meeting?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Pick one Rothschild workflow (for example: research brief, deal dossier, or client email draft).**

### Strong Answers Mention
- Risk often sits in data access, tools, and controls—not the model brand
- Hybrid is common: productivity suites vs sensitive workloads
- Ask where prompts, docs, and logs live; demand architecture with trust boundaries
- Match autonomy to supervision capacity

### Watch For
- Treating the chatbot UI as “the architecture”
- “Open means automatically safer”
- Accepting “fully autonomous” with no failure modes

---

# Q&A

Questions?
