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

# Core Idea

- Multiple input types map into a shared representation space
- The model can attend across text, audio cues, and visual structure
- Pipelines may be **native multimodal** or **composed** (ASR → LLM → TTS)
- Latency, cost, and privacy differ sharply by modality

---

# Native vs Composed (Earnings-Call Path)

| Dimension | Native multimodal | Composed (ASR → LLM → …) |
| :--- | :--- | :--- |
| Joint reasoning | Stronger cross-modal in one pass | Weaker unless you stitch carefully |
| Control points | Fewer intermediate audits | Clear gates after each stage |
| Latency / cost | Often higher per call | Tunable per stage; ASR can be cheaper |
| Privacy | Full media to one vendor | Can isolate ASR or keep audio on-prem |

> [!NOTE]
> Choose for control and audit needs — not only demo elegance.

---

<!-- layout: 2-column -->
# Architecture Choices

### Native multimodal
- One model accepts mixed inputs
- Strong joint reasoning
- Vendor capability varies by task

### Composed pipeline
- Best-of-breed per step
- Clearer control points
- More integration work

---

<!-- layout: navigation -->
# Chapter 7

- How Multimodal Architectures Work
- **Speech, Vision, and Video Models in Finance**
- Synthesizing Multi-Modal Market Intelligence

---

<!-- layout: 3-column -->
# Speech, Vision, Video in Finance

### Speech
- Earnings calls, investor days
- ASR quality drives everything
- Diarization: who said what
- Sentiment = signal, not proof

### Vision
- Charts from decks and filings
- Tables from scanned PDFs
- Competitive imagery sets
- Verify numbers in source text

### Video
- Emphasis beyond transcript
- Slide vs speech alignment
- Chunk long runtimes
- Retain deliberately

---

<!-- layout: 3-column -->
# Modality Failure Cases

### Speech
- Bad ASR on accents/tickers
- Diarization swap (CEO ↔ analyst)
- Sentiment treated as strategy

### Vision
- OCR "1.8" → "18" on leverage
- Axis/unit misread
- Table merge mistakes

### Video
- Slide says X, CEO says Y missed
- Selective clip bias
- Retention / rights risk

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

<!-- layout: stacked -->
# Fusion Workflow

1. Ingest media under access policy
2. Transcribe / extract with timestamps
3. Align transcript to slides or exhibits
4. Retrieve related filings for grounding
5. Synthesize: themes, deltas, risks, quotes
6. Produce text brief + optional audio summary

![Multimodal architecture](images/ch07-multimodal.svg)

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

| Artifact | Purpose |
| :--- | :--- |
| Theme map | Strategy shifts vs prior call |
| Alignment deltas | Slide vs speech conflicts |
| Claim ledger | Claim → quote → timestamp → filing check |
| Risk flags | Guidance language, hedges |
| Exec podcast | TTS summary for commute review (gated) |

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

> [!CAUTION]
> Confirm rights and retention before ingest.

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

**What is the core idea behind multimodal AI architectures?**

- A. Only text models can participate in finance workflows
- B. Multiple input types map into a shared representation for joint reasoning (native or composed pipelines)
- C. Video models eliminate the need for transcripts and citations
- D. Multimodal systems remove privacy and retention concerns

---

# Quiz 1 — Answer

**What is the core idea behind multimodal AI architectures?**

**Correct: B.** Multiple input types map into a shared representation for joint reasoning (native or composed pipelines)

- Native multimodal vs composed (e.g., ASR → LLM → TTS) are both valid
- Latency, cost, and privacy differ by modality and architecture choice
- Transcripts and citations still matter for verifiable claims
- Rights and retention must be confirmed for audio/video artifacts

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
- Retention and rights still apply

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
- Claim ledger and client-facing podcast need strict review; internal theme maps less so
- Confirm recording rights, retention, and sharing before ingest
- Cross-check guidance with the published release; chase misalignment deltas

### Watch For
- Equating tone shifts with certain strategic pivots
- Skipping timestamps/citations
- Uploading client or unlicensed media without clearance

---

# Questions and Answers

Questions?
