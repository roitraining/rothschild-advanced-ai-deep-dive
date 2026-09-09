<!-- course-title: Advanced AI Deep-Dive: Rothschild and Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild and Co

# Chapter 7: Multi-Modal AI

---

# Chapter 7: Objectives

- Explain how multimodal architectures combine modalities
- Identify speech, vision, and video use cases in finance
- Describe synthesis of multimodal market intelligence
- Outline an earnings-call autopsy workflow with controls

---

<!-- layout: navigation -->
# Chapter 7

- **How Multimodal Architectures Work**
- Speech, Vision, and Video Models in Finance
- Synthesizing Multi-Modal Market Intelligence

---

<!-- layout: title-image -->
# Multimodal Inputs → One Reasoning Surface

![Multimodal architecture](images/ch07-multimodal.svg)

---

# Native vs Composed (Earnings-Call Path)

| Dimension | Native multimodal | Composed (ASR → LLM → …) |
| :--- | :--- | :--- |
| Joint reasoning | Stronger cross-modal in one pass | Weaker unless you stitch carefully |
| Control points | Fewer intermediate audits | Clear gates after each stage |
| Latency / cost | Often higher per call | Tunable per stage; ASR can be cheaper |
| Privacy | Full media to one vendor | Can isolate ASR or keep audio on-prem |

> [!NOTE]
> Choose for control and audit needs — not only demo elegance. Pipelines may be native or composed; latency, cost, and privacy differ sharply by modality.

---

<!-- layout: navigation -->
# Chapter 7

- How Multimodal Architectures Work
- **Speech, Vision, and Video Models in Finance**
- Synthesizing Multi-Modal Market Intelligence

---

<!-- layout: 3-column -->
# Speech, Vision, Video in IB Artifacts

### Speech
- Earnings calls, investor days
- ASR quality drives everything
- Diarization: who said what
- Sentiment = signal, not proof

### Vision
- Pitch-book / IC charts and axes
- Scanned CIM tables (OCR)
- Competitive imagery sets
- Verify numbers in source text

### Video
- Emphasis beyond transcript
- Slide vs speech alignment
- Chunk long runtimes
- Retain deliberately

---

<!-- layout: 3-column -->
# Modality Failure Cases (IB)

### Speech
- Bad ASR on accents/tickers
- Diarization swap (CEO ↔ analyst)
- Sentiment treated as strategy

### Vision
- OCR "1.8" → "18" on CIM leverage
- Pitch-book axis/unit misread
- Table merge mistakes across pages

### Video
- Slide says X, CEO says Y missed
- Selective clip bias
- Retention / rights risk

> [!WARNING]
> Scanned CIM unit traps and misread pitch-book axes become “facts” in fluent briefs—recompute from the filing or source PDF.

---

<!-- layout: navigation -->
# Chapter 7

- How Multimodal Architectures Work
- Speech, Vision, and Video Models in Finance
- **Synthesizing Multi-Modal Market Intelligence**

---

# Misalignment Is the Analytic Prize

- Slide says X; CEO says Y — that delta is often the insight
- Do not collapse modalities into one sentiment score
- Treat alignment checks as a first-class output
- Separate **observation** from **inference** in the brief

> [!IMPORTANT]
> Sentiment theater is cheap. Claim-level alignment with filings is bankable.

---

# Timeline Alignment Sketch

| Slide claim (deck) | Transcript (who / time) | Filing check | Status |
| :--- | :--- | :--- | :--- |
| “Net leverage below 3.0x through FY” | CEO 00:42:18: “comfortable below three turns” | Q2 release: 2.7x; no formal guidance | Soft language — not hard guidance |
| “Europe +12% organic” | CFO 00:18:05 cites reported growth | 10-Q: reported includes FX and M&A | Reframe — not organic |
| Chart: margin expansion | No verbal mention | Footnote: one-time credit | Flag slide–speech–filing gap |

---

# Sample Claim Ledger Row

| Field | Example |
| :--- | :--- |
| Claim | "Net leverage will stay below 3.0x through FY" |
| Quote | "…comfortable below three turns…" |
| Timestamp | 00:42:18 (CEO) |
| Filing cross-check | Q2 release: net leverage 2.7x; no formal guidance |
| Status | Soft language — do not treat as hard guidance |

---

# Earnings Call Autopsy — Outputs

| Artifact | Purpose | Gate |
| :--- | :--- | :--- |
| Theme map | Strategy shifts vs prior call | Internal OK with review |
| Alignment deltas | Slide vs speech conflicts | Human confirm material deltas |
| Claim ledger | Claim → quote → timestamp → filing | **Required** before client use |
| Risk flags | Guidance language, hedges | Legal/compliance as needed |
| Exec podcast | TTS commute summary | **Last**: rights + ledger first |

> [!CAUTION]
> Exec podcast is an artifact of a cleared claim ledger—not a substitute for it. Confirm rights and retention before any TTS packaging.

---

<!-- layout: 2-column -->
# Hard Rules and Quality Bars

### What not to upload
- Client recordings without rights/retention approval
- Unlicensed or paywalled audio/video
- Deal-room materials into consumer apps
- PII-rich media without Legal clearance

### Quality bars
- Timestamped citations for quotable claims
- Observation vs inference separated
- Cross-check guidance with the release
- Human sign-off before client use

---

# Lab Bridge: Autopsy Path

1. **Ingest** media only after rights / retention clearance
2. Transcribe / extract; fill one **claim ledger** row for a material claim
3. **Human verify** quote, timestamp, and filing cross-check
4. Only then draft the brief (and optional podcast)—never reverse the order

> [!TIP]
> If the ledger row cannot be verified, the claim does not leave the room—podcast or not.

---

# Lab 7: Earnings Call Autopsy

**Time:** 30 minutes

**Lab guide:** [Lab 7 instructions](labs/lab-07-earnings-call-autopsy.md)

---

# What You Learned

- Explained how multimodal architectures combine modalities
- Identified speech, vision, and video use cases in finance
- Described synthesis of multimodal market intelligence
- Outlined an earnings-call autopsy workflow with controls

---

# Quiz 1 of 3

**A coverage team must autopsy earnings calls with audit gates after ASR, before synthesis, and before any TTS summary. When does a composed pipeline beat native multimodal?**

- A. Never—native always wins on control
- B. When intermediate control points, per-stage vendor isolation, or tunable cost/latency matter more than single-pass joint reasoning
- C. Only when the team wants to skip claim ledgers
- D. When uploading client audio to consumer apps is allowed

---

# Quiz 1 — Answer

**A coverage team must autopsy earnings calls with audit gates after ASR, before synthesis, and before any TTS summary. When does a composed pipeline beat native multimodal?**

**Correct: B.** When intermediate control points, per-stage vendor isolation, or tunable cost/latency matter more than single-pass joint reasoning

- Composed (ASR → LLM → …) exposes clear gates after each stage
- Native may be stronger at joint reasoning but fewer audit hooks
- Claim ledgers and rights still apply either way
- Architecture choice is about control and privacy—not skipping diligence

---

# Quiz 2 of 3

**In an earnings-call autopsy, which practice is mandatory for material claims?**

- A. Treat sentiment scores as proof of a strategic pivot
- B. Timestamped citations, observation vs inference separation, and cross-check of guidance figures
- C. Discard the published release once video analysis finishes
- D. Auto-send the TTS podcast to clients without review

---

# Quiz 2 — Answer

**In an earnings-call autopsy, which practice is mandatory for material claims?**

**Correct: B.** Timestamped citations, observation vs inference separation, and cross-check of guidance figures

- Prosody/sentiment are signals — not proof of strategy
- Claim ledgers and human sign-off precede client or investment use
- Alignment deltas (slide vs speech) are often the real analytic prize
- Retention and rights still apply; podcast comes after the ledger

---

<!-- layout: 2-column -->
# Quiz 3 of 3 — Discussion

### Prompt
Design an earnings-call autopsy for a coverage team.

### Discuss
- Native multimodal vs composed pipeline — what would you choose and why?
- Which outputs (theme map, claim ledger, podcast) need the strictest gates?
- What personal-data or rights issues must Legal/Compliance clear first?

---

<!-- layout: 2-column -->
# Quiz 3 — Discussion Points

**Design an earnings-call autopsy for a coverage team.**

### Strong Answers Mention
- Composed pipelines offer clearer control points; native may simplify joint reasoning
- Rights and claim ledger first; exec podcast last and optional
- Confirm recording rights, retention, and sharing before ingest
- Cross-check guidance with the published release; chase misalignment deltas

### Watch For
- Equating tone shifts with certain strategic pivots
- Skipping timestamps/citations
- Packaging TTS before ledger verification or rights clearance

---

# Questions and Answers

Questions?
