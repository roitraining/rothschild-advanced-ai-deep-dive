<!-- course-title: Advanced AI Deep-Dive: Rothschild and Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild and Co

# Chapter 6: Advanced AI Use Cases

---

# Chapter 6: Objectives

- Structure deep market and competitor research with AI
- Accelerate data analysis and portfolio trend exploration
- Apply vibe coding for dashboards and prototypes safely
- Connect prompts to pitch-ready outputs with human review

---

<!-- layout: navigation -->
# Chapter 6

- **Deep Market and Competitor Research**
- Rapid Data Analysis and Portfolio Trends
- Vibe Coding: Dashboards and Prototypes

---

> [!TIP]
> **Instructor — Day 1 fatigue:** If short on time, keep research + analysis + vibe-coding gates; treat the pitch-spine table and lab bridge as **lab-only** (skip lecture slides; run them inside Lab 6). Bankable language fragment stays—short and high value.

---

# Research Agent Pattern (Advisory)

- Break the question into **sources, angles, and deliverable** (client note, deal teaser, debt restructuring update)
- Separate **collection** from **synthesis** to reduce mixed-up citations
- Prefer primary sources: public filings, earnings transcripts, deal announcements, approved vendor feeds
- Maintain a running **claims vs evidence** table until sign-off

> [!IMPORTANT]
> AI accelerates mapping and drafting. Source trust and client framing stay human.

---

<!-- layout: 2-column -->
# Collection vs Synthesis on the Day 1 Stack

### Collection (approved paths)
- Firm RAG over secure deal folders / research corpora
- MCP/tools for CRM, positions, vendor APIs
- Download or query—then log what you retrieved

### Synthesis (chat / draft)
- Claims table → narrative → slide outline
- No new “facts” that were never collected
- Contradictions named explicitly before polish

> [!NOTE]
> Same architecture as Ch3–4: retrieve and tool first; chat second. Do not paste the open web into a client memo and call it diligence.

---

<!-- layout: 2-column -->
# Primary Sources by Desk

### Client team / mergers
- Annual report / quarterly report / foreign issuer report; proxy / circular
- Earnings transcripts; investor decks
- Announced deal terms; press from parties

### Debt restructuring / special situations
- Court dockets; restructuring support agreements
- Creditor presentations; liquidity updates
- Loan docs and amendment history (ACL-bound)

---

<!-- layout: 2-column -->
# Competitor Tear-Sheet Workflow

### AI accelerates
- Landscape mapping
- Theme clustering
- First-draft narratives
- Slide outlines

### Humans own
- Source trust
- Strategic judgment
- Client framing
- Final numbers

---

# Claims vs Evidence (Filled Example)

| Claim | Evidence | Status |
| :--- | :--- | :--- |
| A peer gained share in EU mid-sized deals | Peer annual report, p. 42: segment revenue vs last year | Verified |
| Peer Y "dominates" restructuring fees | Trade press ranking; no fee disclosure | Weak — reframe |
| Market consolidating via bolt-ons | 3 announced deals in window; deal DB count | Partial — size TBD |

> [!TIP]
> Force every material claim into a row before it reaches a client slide.

---

<!-- layout: 2-column -->
# Contradiction Drill

### What went wrong
- Same metric in presentation vs quarterly-report footnote
- Model merged both into one fluent paragraph
- Conflict never surfaced to the reader

### Bankable fix
- Collection pass lists both figures
- Synthesis names the conflict explicitly
- Output: "Sources disagree on X; we use Y because…"

> [!WARNING]
> Speed without source discipline creates elegant misinformation.

---

# Anti-Patterns in AI Research

- Single-prompt "write a full industry report"
- Treating vendor blogs as peers to company reports / public filings
- No distinction between **retrieved** and **recalled** facts
- Skipping contradiction checks across sources

---

<!-- layout: navigation -->
# Chapter 6

- Deep Market and Competitor Research
- **Rapid Data Analysis and Portfolio Trends**
- Vibe Coding: Dashboards and Prototypes

---

# Analysis Copilot vs Analytics Platform

- LLMs excel at framing questions, explaining, and drafting commentary
- Systems of record and BI remain authoritative for aggregates
- Pattern: export or query → verify → narrate with AI
- Ask the model to show steps; recompute critical figures yourself

---

<!-- layout: 3-column -->
# LLM-as-Analyst Hazards

### Units
- Thousands vs millions
- Local currency vs USD
- Period mismatches

### Joins
- Wrong entity keys
- Partial portfolio extracts
- Silent row drops

### Invented math
- Fluent year-over-year with no series
- Chart titles as "facts"
- **Recompute or it did not happen**

> [!CAUTION]
> Chat over a CSV is not an audit trail. Prefer sandboxed analysis with logged steps.

---

# Portfolio Trends Playbook

1. Define the question and time window
2. Pull data via approved tools or files
3. Profile: missingness, outliers, units
4. Chart candidates; validate joins and filters
5. Draft insight bullets with explicit caveats

> [!TIP]
> Have the model propose hypotheses, then require SQL or spreadsheet evidence.

---

<!-- layout: 2-column -->
# Sandbox vs Freeform Chat

### Prefer
- Code interpreter / sandbox with logged transforms
- Explicit schema and unit assumptions
- Export of intermediate tables

### Avoid
- Pasting confidential portfolios into consumer chat
- Accepting chart titles as verified metrics
- One mega-prompt that "analyzes everything"

---

<!-- layout: navigation -->
# Chapter 6

- Deep Market and Competitor Research
- Rapid Data Analysis and Portfolio Trends
- **Vibe Coding: Dashboards and Prototypes**

---

# What Vibe Coding Is

- Iterative natural-language building of small apps and visuals
- Ideal for **internal prototypes**, demos, and exploration
- Not a bypass of engineering standards for production systems
- Works best with clear acceptance checks each iteration

---

<!-- layout: 2-column -->
# If the IDE Is Unavailable

### Still teach the gate
- Critique a **mock** dashboard screenshot or stub
- Score: mock data only? units labeled? version pin?
- Rewrite hype titles into bankable captions

### Do not require generate
- Generating code is optional when tooling is blocked
- Judgment on prototype vs production still counts
- Lab can use provided mock UI instead of live codegen

---

<!-- layout: stacked -->
# From Prompt to Dashboard

- Describe audience, metrics, and interactivity constraints
- Generate → run → critique → refine in tight loops
- Pin versions when sharing with stakeholders
- Separate mock data from anything confidential

<!-- TODO IMAGE: Screenshot of an AI coding assistant generating a portfolio dashboard with mock metrics -->
![Vibe coding dashboard placeholder](images/ch06-vibe-coding-dashboard-screenshot.svg)

---

<!-- layout: 2-column -->
# Prototype vs Production Gates

### Prototype path
- Mock or anonymized data
- Local or personal tenant
- Demo audience only
- Version pinned for the meeting

### Production path
- AuthN / AuthZ and audit
- Data residency and retention
- Change control and owners
- Eval and monitoring hooks

---

<!-- layout: 2-column -->
# Worked Fragment: Hype → Bankable

### Reject (hype)
- "AI proves the sector is pivoting to software"
- "Guaranteed alpha from this screen"
- "The model understands our book better than the client team"

### Prefer (bankable)
- "Based on verified company reports through 30 Jun: peer EU mid-sized segment rev +8% vs last year (annual report p.42)"
- "Hypothesis: share gain. Evidence: peer comparison table. Caveat: FX and deal mix not isolated"
- "Draft for advisor review — not client-ready"

---

# Pitch Deck Acceleration

| Slide | Purpose |
| :--- | :--- |
| 1 | Situation / ask |
| 2 | Portfolio snapshot |
| 3 | Drivers and trends |
| 4 | Risks and sensitivities |
| 5 | Recommended next steps |

- Use AI only on **verified** metrics; one source table of truth
- Speaker notes separate from slide text; brand review still required

---

# Start Your Vendor Question Bank

Carry these forward into Ch8–9 (add your own):

- Where does collection happen — approved RAG/MCP, or the chat box alone?
- Can every client-facing number be recomputed or cited to a primary source?
- What is blocked until a human signs (outreach, send, trade, client deck)?
- Show me the audit trail for a rejected claim that looked fluent

> [!TIP]
> Ch8 expands this bank for agents; Ch9 scores vendors against it.

---

# Lab Bridge: From Prompt to Pitch

- Use a **mock** portfolio only — no live client books
- Dashboard first (or critique mock UI), then compress into the 5-slide spine
- Every slide number must trace to your evidence table
- Instructor checks: mock data, recompute rule, bankable wording

---

# Lab 6: From Prompt to Pitch Deck

**Time:** 30 minutes

**Lab guide:** [Lab 6 instructions](labs/lab-06-prompt-to-pitch.md)

---

# What You Learned

- Structured deep market and competitor research with AI
- Accelerated data analysis and portfolio trend exploration
- Applied vibe coding for dashboards and prototypes safely
- Connected prompts to pitch-ready outputs with human review

---

# Quiz 1 of 3

**A claims table marks Peer Y "dominates restructuring fees" as Weak (trade press only; no fee disclosure). The associate wants that line on tomorrow’s client slide.**

- A. Keep the wording—trade press is good enough for a headline
- B. Block the client slide until the claim is verified, reframed, or dropped; Weak status is a hard gate
- C. Ask the model to rewrite it more confidently so it sounds bankable
- D. Move it to speaker notes so it never needs evidence

---

# Quiz 1 — Answer

**A claims table marks Peer Y "dominates restructuring fees" as Weak (trade press only; no fee disclosure). The associate wants that line on tomorrow’s client slide.**

**Correct: B.** Block the client slide until the claim is verified, reframed, or dropped; Weak status is a hard gate

- Material claims need Verified (or explicit Partial with caveats)—not fluent Weak
- Reframe to what the source supports, or remove the line
- Confidence polish without evidence is the anti-pattern
- Collection via RAG/tools first; synthesis never invents fee dominance

---

# Quiz 2 of 3

**Sandbox analysis fails mid-run (timeout / join error) while drafting portfolio commentary for an investment committee update. What is the right next move?**

- A. Paste the portfolio into consumer chat and ask for the same commentary
- B. Escalate: fix or re-run the sandbox / approved tool path; do not ship commentary on unverified aggregates
- C. Accept the last partial chart title as the year-over-year figure
- D. Skip verification because the narrative already sounds right

---

# Quiz 2 — Answer

**Sandbox analysis fails mid-run (timeout / join error) while drafting portfolio commentary for an investment committee update. What is the right next move?**

**Correct: B.** Escalate: fix or re-run the sandbox / approved tool path; do not ship commentary on unverified aggregates

- Systems of record and logged transforms remain authoritative
- Freeform consumer chat and chart-title “facts” fail the recompute rule
- Partial failure → refuse or escalate, same spirit as weak RAG
- Vibe-coding prototypes still need mock data and acceptance checks—not silent fallbacks

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
You will turn a mock portfolio into a dashboard and a 5-slide pitch spine with AI.

### Discuss
- Which steps must stay tied to systems of record or recomputation?
- What belongs on each of the five slides vs in speaker notes?
- Where do humans own narrative and brand — even if AI drafts fast?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**You will turn a mock portfolio into a dashboard and a 5-slide pitch spine with AI.**

### Strong Answers Mention
- Export/query → verify → narrate; recompute critical figures
- Spine: situation/ask, snapshot, drivers, risks, next steps
- One metrics table of truth; design/brand review still required
- Prototype vs production gates before any live data

### Watch For
- Letting the model invent portfolio numbers
- Collapsing research into one uncited mega-prompt
- Shipping prototypes as production analytics

---

# Questions and Answers

Questions?
