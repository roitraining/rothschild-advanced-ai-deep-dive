<!-- course-title: Advanced AI Deep-Dive: Rothschild & Co -->
<!-- layout: title -->
![ROI Logo](images/roi-logo-with-name.png)

Advanced AI Deep-Dive: Rothschild & Co

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

<!-- layout: stacked -->
# Core Idea

- Multiple input types map into a shared representation space
- The model can attend across text, audio cues, and visual structure
- Pipelines may be **native multimodal** or **composed** (ASR → LLM → TTS)
- Latency, cost, and privacy differ sharply by modality

---

<!-- layout: 2-column -->
# Architecture Choices

### Native multimodal
- One model accepts mixed inputs
- Strong joint reasoning
- Vendor capability varies

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
# Modalities in Finance

### Speech
- Earnings calls
- Diarization matters
- Sentiment ≠ strategy

### Vision
- Charts and tables
- Scanned PDFs
- Verify key figures

### Video
- Delivery beyond text
- Chunk long runtime
- Watch retention rights

---

# Rights, Privacy, and Retention

- Multimodal artifacts often include personal data and third-party content
- Confirm recording rights, retention, and sharing policy before analysis

> [!CAUTION]
> Multimodal artifacts can contain personal data and third-party copyrighted content—confirm rights and retention.

---

<!-- layout: navigation -->
# Chapter 7

- How Multimodal Architectures Work
- Speech, Vision, and Video Models in Finance
- **Synthesizing Multi-Modal Market Intelligence**

---

<!-- layout: stacked -->
# Fusion Workflow

1. Ingest media under access policy
2. Transcribe / extract with timestamps
3. Align transcript to slides or exhibits
4. Retrieve related filings for grounding
5. Synthesize: themes, deltas, risks, quotes
6. Produce text brief + optional audio summary

---

# Earnings Call Autopsy — Outputs

| Artifact | Purpose |
| :--- | :--- |
| Theme map | Strategy shifts vs. prior call |
| Sentiment track | Tone by segment (with caveats) |
| Claim ledger | Claim → quote → timestamp |
| Risk flags | Guidance language, hedges |
| Exec podcast | TTS summary for commute review |

---

<!-- layout: 2-column -->
# Quality Bars

### Evidence
- Timestamped citations
- Cross-check guidance figures
- Claim ledger before narrative

### Judgment
- Observation ≠ inference
- Human sign-off required
- Client-ready only after review

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

# Q&A

Questions?
