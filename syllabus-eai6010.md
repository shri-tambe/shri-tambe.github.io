---
layout: default
title: "EAI 6010: Applications of Artificial Intelligence — Syllabus"
---

# EAI 6010: Applications of Artificial Intelligence

**Graduate — 3 Quarter Hours**
**Instructor:** Shrikant Tambe \| [ORCID](https://orcid.org/0009-0003-3432-3852)

A practitioner-focused course on applying modern AI/ML techniques to real business problems. Students move from understanding foundation models to deploying AI solutions in healthcare, finance, operations, and knowledge work — with emphasis on the 2024–2026 paradigm shift from training models to orchestrating them.

**Prerequisites:** EAI 6000 (Fundamentals of AI) or equivalent. Python proficiency.

**Grading:** 45% Labs (8, including vendor evaluation) \| 15% Project Proposal (Week 7) \| 30% Capstone Project \| 10% Participation

---

## Course Philosophy

The AI market moves faster than any curriculum can follow. This course teaches students *how to evaluate and apply* emerging AI capabilities — not just today's tools, but the decision framework for tomorrow's. Every module pairs a technique with a business domain and a failure mode, so students learn what works, where it breaks, and how to know the difference.

---

## Schedule (10 Weeks)

| Week | Topic | Domain Application | Lab |
|------|-------|-------------------|-----|
| 1 | **The New AI Stack & Prompt Engineering:** Foundation models landscape. Prompt design patterns (few-shot, chain-of-thought, role prompting). Structured outputs. When prompting is enough vs. when you need more. | Overview | Solve the same business task 5 ways: zero-shot, few-shot, chain-of-thought, structured output, and RAG. Measure quality/cost tradeoffs. |
| 2 | **Retrieval-Augmented Generation:** When your AI needs facts. Chunking strategies, embedding models, retrieval evaluation. Hallucination measurement. | Knowledge Management | Build a RAG system over company docs; measure hallucination rate at different chunk sizes and retrieval configs. |
| 3 | **Classification & Extraction at Scale:** From regex to NER to LLMs. Structured data extraction from unstructured text. Confidence scoring and human-in-the-loop for low-confidence predictions. | Healthcare / Pharma | Extract structured data from clinical notes; compare regex vs. NER vs. LLM extraction on accuracy, cost, and latency. |
| 4 | **Recommendation & Personalization:** Embeddings, similarity search, reranking. Cold-start problem. Combining collaborative filtering with semantic understanding. | E-Commerce / HR | Build a job-candidate matching system using embeddings + reranking. Evaluate with precision@k and diversity metrics. |
| 5 | **Data Analysis with AI:** LLM-powered data exploration (natural language → SQL/pandas). Tabular ML + LLM hybrid approaches. Automated insight generation from datasets. | Finance / Analytics | Build a natural-language data analyst: user asks questions in English, system generates pandas code, executes it, and explains findings. Test on a loan dataset. |
| 6 | **Multimodal AI: Vision + Language** Using vision APIs (GPT-4V, Claude Vision) for business tasks. Document understanding, image classification, visual QA. Confidence thresholds and fallback to human review. | Manufacturing / Retail | Build a product defect classifier using vision APIs. Implement confidence-based routing: auto-approve high confidence, flag low confidence for human review. |
| 7 | **Project Proposal & Vendor Evaluation Lab:** Submit capstone project proposal (problem, approach, evaluation plan). In-class lab: evaluate a real AI vendor proposal — identify risks, gaps, hidden costs, missing evaluation criteria. | Deliverable: 2-page project proposal + vendor evaluation worksheet (graded as lab). |
| 8 | **AI Agents as Business Automation:** When to use agents vs. pipelines vs. simple API calls. Designing agent workflows for operations. Error handling and escalation. | Operations | Build an agent that triages support tickets, routes to teams, and escalates when uncertain. Measure accuracy vs. a rule-based baseline. |
| 9 | **Evaluation, Bias, and Responsible Deployment:** Red-teaming AI systems. Fairness metrics. A/B testing AI features. Monitoring for drift and degradation post-deployment. | Cross-domain | Red-team a deployed model; measure fairness metrics across demographic groups; design a monitoring dashboard for production. |
| 10 | **Capstone Presentations** — Deploy an AI solution to a real business problem | | |

---

## Key Themes Across All Modules

- **Build vs. Buy:** When to use off-the-shelf APIs vs. custom models vs. open-source
- **Evaluation Beyond Accuracy:** Precision/recall tradeoffs, cost per prediction, latency budgets, fairness constraints
- **Failure Modes:** Hallucination, distribution shift, adversarial inputs, cost blowups, silent degradation
- **The Human Loop:** When AI assists vs. decides vs. recommends — designing appropriate autonomy levels

---

## Capstone Project

Individual or pairs. Identify a real business problem (from your workplace or a provided dataset), design an AI solution, implement a working prototype, deploy it (cloud API or local demo), and present:

1. **Problem framing** — Why AI? What's the baseline without AI?
2. **Approach selection** — Why this technique over alternatives? (decision matrix required)
3. **Implementation** — Working prototype with evaluation metrics
4. **Failure analysis** — What breaks? Edge cases tested. Bias audit conducted.
5. **Business case** — ROI estimate, deployment plan, monitoring strategy

---

## Required Tools & Platforms

- Python 3.10+, Jupyter/Colab
- OpenAI or Anthropic API (free tier sufficient)
- Hugging Face Transformers (open-source models)
- scikit-learn, XGBoost (tabular ML)
- Vector database (Pinecone free tier or ChromaDB local)

---

## How This Course Differs from EAI 6000 and EAI 6020

| | EAI 6000 (Fundamentals) | **EAI 6010 (This Course)** | EAI 6020 (System Technologies) |
|---|---|---|---|
| Focus | What AI is, how it works | How to apply AI to solve business problems | How to build and operate AI infrastructure |
| Outcome | Understand algorithms | Deploy AI solutions with evaluation | Architect production AI systems |
| Audience | New to AI | Practitioners applying AI at work | Engineers building AI platforms |

---

## Instructor Background

Shrikant Tambe is a Senior SDE at AWS with 8 years building production AI and distributed systems. He created the CloudWatch MCP Server (274K+ monthly downloads), designed LLM extraction pipelines processing 30K+ documents, built multi-agent AI platforms on AWS Bedrock, and authored research on AI system reliability (D-AER, Cognitive SLOs). His work spans the full AI application lifecycle from prototype through production at scale.

## Recommended Readings & References

No required textbook. Weekly readings are provided on Canvas — a mix of tutorials, documentation, and accessible papers. The goal is practical understanding, not literature review.

**Foundational Readings:**
- Anthropic, "Building Effective Agents" (2024) — https://docs.anthropic.com/en/docs/build-with-claude/agent
- OpenAI, "Best Practices for Prompt Engineering" — https://platform.openai.com/docs/guides/prompt-engineering
- Lewis et al., "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks" (2020) — Week 2
- Wei et al., "Chain-of-Thought Prompting Elicits Reasoning in LLMs" (2022) — Week 1
- Reimers & Gurevych, "Sentence-BERT: Sentence Embeddings using Siamese Networks" (2019) — Week 4

**Applied AI & Business:**
- Chip Huyen, *Designing Machine Learning Systems* (O'Reilly, 2022) — Chapters 1, 2, 9
- Chip Huyen, *AI Engineering* (O'Reilly, 2025) — Chapters on RAG, evaluation, deployment
- Google, "People + AI Guidebook" — https://pair.withgoogle.com/guidebook/ — Week 9
- NIST AI Risk Management Framework (AI RMF 1.0) — Week 9
- McKinsey, "The State of AI in 2025" — Week 1 context

**Technical Documentation (used in labs):**
- OpenAI API Documentation — https://platform.openai.com/docs
- Anthropic Claude API — https://docs.anthropic.com
- Hugging Face Transformers — https://huggingface.co/docs/transformers
- LangChain Documentation — https://python.langchain.com/docs
- ChromaDB / Pinecone documentation — Week 2
- scikit-learn User Guide — Week 5

**Evaluation & Responsible AI:**
- Mitchell et al., "Model Cards for Model Reporting" (2019) — Week 9
- Gebru et al., "Datasheets for Datasets" (2021) — Week 9
- Liang et al., "Holistic Evaluation of Language Models (HELM)" (2023) — Week 9
- Perez et al., "Red Teaming Language Models with Language Models" (2022) — Week 9
- EU AI Act Summary — https://artificialintelligenceact.eu/ — Week 9

**Industry Case Studies (discussed in class):**
- Zillow's AI home-buying failure ($500M loss) — Week 1
- GitHub Copilot's evolution and business model — Week 8
- Healthcare AI: Epic's ambient clinical documentation — Week 3
- JPMorgan's LLM-powered contract analysis — Week 5

**Optional Deep Dives:**
- Vaswani et al., "Attention Is All You Need" (2017) — for students wanting transformer internals
- Brown et al., "Language Models are Few-Shot Learners" (GPT-3, 2020) — foundational context
- Bommasani et al., "On the Opportunities and Risks of Foundation Models" (2021) — big picture

[← Back to home](/)
