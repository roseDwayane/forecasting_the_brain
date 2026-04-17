---
citation_key: "Chakraborty2026"
paper_id: "paper_282"
title: "Project Hermes: A Model-Agnostic Validation Layer for Wearable Health Prediction Systems"
authors: "Richik Chakraborty"
year: 2026
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2602.18643"
tier: 2
composite: 4.2
---

# Project Hermes: A Model-Agnostic Validation Layer for Wearable Health Prediction Systems

**Citation:** `Chakraborty2026` · **Tier:** 2 · **Composite:** 4.2

- **arXiv**: [2602.18643](https://arxiv.org/abs/2602.18643)
- **URL**: [http://arxiv.org/abs/2602.18643v1](http://arxiv.org/abs/2602.18643v1)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

The deployment of wearable-based health prediction systems has accelerated rapidly, yet these systems face a fundamental challenge: they generate alerts under substantial uncertainty without principled mechanisms for user-specific validation. While large language models (LLMs) have been increasingly applied to healthcare tasks, existing work focuses predominantly on diagnosis generation and risk prediction rather than post-prediction validation of detected signals. We introduce Project Hermes, a model-agnostic validation layer that treats signal confirmation as a sequential decision problem. Hermes operates downstream of arbitrary upstream predictors, using LLM-generated contextual queries to elicit targeted user feedback and performing Bayesian confidence updates to distinguish true positives from false alarms. In a 60-day longitudinal case study of migraine prediction, Hermes achieved a 34% reduction in false positive rate (from 61.7% to 12.5%) while maintaining 89% sensitivity, with mean lead time of 4.2 hours before symptom onset. Critically, Hermes does not perform diagnosis or make novel predictions; it validates whether signals detected by upstream models are clinically meaningful for specific individuals at specific times. This work establishes validation as a first-class computational problem distinct from prediction, with implications for trustworthy deployment of consumer health AI systems.
