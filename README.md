
# SoundSense + ReviewRAG (MVP) - **work in progress**

This repository contains the SoundSense companion project for the Community Docs RAG project: a tiny starter implementation and Product Requirements Document (PRD) for inferring acoustic accessibility signals from public reviews and explaining them transparently.

## General Framing

This project pair explores two complementary NLP capabilities applied to public reviews:

- Inferring probabilistic accessibility signals (SoundSense)
- Answering user questions with grounded, review-based evidence (Community Docs RAG)

## Product Name

SoundSense (MVP)

## Problem Statement

Neurodivergent people and others with sensory sensitivities often struggle to choose cafés and restaurants where they can comfortably converse or focus. Existing platforms (e.g. Google Maps) contain relevant information in reviews, but it is unstructured, inconsistent, and difficult to interpret.

## Goals

- Help users assess whether a café/restaurant is likely to be acoustically comfortable
- Provide evidence-backed explanations rather than opaque scores
- Surface uncertainty honestly

## Non-Goals

- Real-time sound measurement
- Google Maps integration
- Definitive or authoritative ratings
- City-wide completeness

This is an assistive decision-support MVP.

## Target Users

- Neurodivergent individuals with sound sensitivity
- People seeking calm meeting spaces
- Accessibility advocates
- Researchers and NGOs exploring sensory accessibility

## User Needs

Users want to:

- Quickly understand if a café/restaurant is likely to be noisy
- Ask specific questions (e.g. “Is it loud in the evening?”)
- See why the system says something
- Understand uncertainty and limitations

## Core Features

- **Feature 1 — Sound Profile (SoundSense):** For each venue provide a natural-language summary, time-of-day sound levels when supported, confidence scores, key contributing factors, and limitations.
- **Feature 2 — Ask Reviews (ReviewRAG):** For each venue provide natural-language Q&A grounded in review text with explicit citations and "insufficient evidence" handling.

## Data Sources

- Public review datasets (e.g. Yelp Open Dataset)
- Synthetic or sampled subsets for MVP

## Technical Approach (High Level)

- **SoundSense:** Weak supervision (rules + LLM assistance), review-level inference, venue-level aggregation with uncertainty.
- **Community Docs RAG:** Embedding-based retrieval over review chunks, LLM answer generation with strict citation enforcement, and refusal when evidence is insufficient.

## Success Metrics (MVP)

- Retrieval relevance (manual spot checks)
- Citation correctness
- Schema validity rate
- Qualitative plausibility of sound profiles

## Future Extensions (Out of Scope for MVP)

- User-submitted sound ratings
- Real-time sensing
- Map-based UI
- Multilingual expansion

## Related Project

See the `communitydocs-rag` project for the companion ReviewRAG README and implementation. The two repos share the same review data and venue IDs; `communitydocs-rag` focuses on grounded Q&A while `soundsense-nlp` focuses on inferring sound/sensory profiles with uncertainty.

## Installation & Next Steps

This is an early-stage project scaffold. TBD:

```bash
git clone <repo-url>
cd soundsense-nlp
python -m venv venv
source venv/bin/activate
pip install -e .
```

Add tests in `tests/` and expand `src/soundsense/` modules as needed.

---

**Status:** Early development / PRD stage

