---
layout: default
title: "CS 6950: Applied AI Agent Systems — Syllabus"
---

# CS 6950: Applied AI Agent Systems

**Graduate — 3 Quarter Hours**
**Instructor:** Shrikant Tambe \| [ORCID](https://orcid.org/0009-0003-3432-3852)

Production AI systems increasingly rely on autonomous agents — software that reasons, uses tools, and coordinates with other agents to accomplish complex tasks. This course teaches students to build, deploy, observe, and harden AI agent systems using patterns drawn from real production deployments. Students progress from single-agent tool use through multi-agent orchestration to production reliability engineering.

**Prerequisites:** Graduate-level programming (Python). Familiarity with distributed systems concepts (RPC, consensus, fault tolerance) or concurrent programming. Prior exposure to LLM APIs (EAI 6010 or equivalent).

**Grading:** 50% Labs (8) \| 10% Architecture Review (Week 6) \| 40% Final Project

---

## Schedule (10 Weeks)

| Week | Topic | Lab |
|------|-------|-----|
| 1 | **Agent Architectures & Internals:** ReAct, plan-and-execute, tree-of-thought. How LLM inference works (attention, KV cache, sampling). Token generation as a systems problem. Latency breakdown of an agent call. | Implement a ReAct agent from scratch (no framework): prompt construction, JSON parsing, tool dispatch loop, stop conditions. Profile where time is spent. |
| 2 | **Tool Integration Protocols:** MCP specification deep-dive (transport, capability negotiation, resource/tool/prompt primitives). OpenAI function calling internals. Schema design for reliable tool use. Error propagation. | Build an MCP server exposing a database + REST API. Build a client agent that discovers tools dynamically, handles schema validation errors, and retries with corrected parameters. |
| 3 | **Memory Architectures:** Context window mechanics (positional encoding limits, attention degradation). Vector store internals (HNSW, IVF, quantization tradeoffs). Hybrid retrieval (sparse + dense). Memory compaction algorithms. | Implement 3 memory strategies for the same agent task: sliding window, RAG with reranking, and summarization-based compression. Benchmark recall accuracy vs. token cost at 10K, 50K, 100K context lengths. |
| 4 | **Multi-Agent Coordination:** Distributed systems parallels — consensus, partial failure, ordering. Topologies (DAG, hierarchical, mesh). Message passing vs. shared state. Deadlock detection. Conflict resolution strategies (voting, confidence-weighted, debate). | Build a 4-agent system with explicit message passing (no shared memory). Implement leader election, handle agent crashes mid-task, and resolve conflicting outputs using confidence-weighted voting. |
| 5 | **Distributed Tracing for Agents:** OpenTelemetry architecture (spans, contexts, propagation). Designing span hierarchies for agent workflows. Causal ordering in async agent systems. Trace sampling strategies for high-volume agent traffic. Custom semantic conventions for reasoning quality. | Instrument the Week 4 system with OTel: custom span attributes for reasoning depth, tool call success rate, and confidence scores. Build a Jaeger dashboard with agent-specific views. Implement tail-based sampling that keeps traces with failures or high latency. |
| 6 | **Project Milestone: Architecture Review.** Teams present their system design (architecture diagram, tool interfaces, failure modes identified, observability plan). Peer feedback session. Instructor approval required before implementation begins. | Submit: architecture doc + 5-min presentation. Receive: peer feedback + instructor go/no-go. |
| 7 | **Failure Engineering:** Formal failure taxonomy (loops, hallucinated actions, cascade amplification, semantic drift, zombie agents). Circuit breaker patterns adapted for non-deterministic systems. Chaos engineering methodology: fault injection, blast radius, steady-state hypothesis. | Implement a chaos testing framework: inject 5 failure types (model timeout, hallucinated tool call, infinite delegation loop, context overflow, conflicting verdicts). Measure MTTD (mean time to detect) and MTTR (mean time to recover) for each. |
| 8 | **Performance Engineering:** Token economics and cost modeling. Model routing algorithms (confidence-based cascading, task classification). Semantic caching (embedding similarity thresholds, cache invalidation). Batching and parallelism strategies. Quantization tradeoffs for self-hosted models. | Build a model router: classify incoming requests → route to appropriate model (fast/cheap vs. slow/capable). Implement semantic cache with TTL and similarity threshold tuning. Measure cost reduction vs. quality degradation curves. |
| 9 | **Security & Governance:** Prompt injection attack vectors (direct, indirect, tool-mediated). Sandboxing agent actions (capability-based security). Permission models for tool access. Audit trail design for compliance. Formal verification of agent action bounds. | Red-team the multi-agent system: craft 5 prompt injection attacks (direct injection, tool-result poisoning, cross-agent manipulation, privilege escalation via tool chaining, data exfiltration). Implement defenses for each. |
| 10 | **Final Project Presentations** | |

---

## Key Themes Across All Modules

- **Agents are software systems first:** They need the same engineering rigor as any production service — monitoring, error handling, testing, cost management
- **Observability is not optional:** If you can't trace why an agent made a decision, you can't debug it, improve it, or trust it
- **Failure is the default:** Agents fail in novel ways (loops, hallucinations, cascades). Design for failure, not just success
- **Cost is a first-class constraint:** Every agent call costs money. Architecture decisions are cost decisions.

---

## Final Project

Teams of 2-3. Design, build, and deploy an agent system that solves a real problem. Requirements:

1. **Functional:** Agent(s) perform a useful task with tool use (not just chat)
2. **Observable:** Instrumented with tracing — you can show the decision path for any request
3. **Reliable:** Handles at least 3 failure modes gracefully (documented with tests)
4. **Governed:** Includes cost tracking, at least one safety guardrail, and an audit trail
5. **Evaluated:** Quantitative metrics showing how well the system works (not just "it demos well")

Deliverables: Architecture doc (Week 7), working demo (Week 9), final presentation + report (Week 10).

---

## Required Tools & Platforms

- Python 3.10+, async programming (asyncio)
- OpenAI or Anthropic API
- OpenTelemetry Python SDK + Jaeger (Docker)
- MCP SDK (Python or TypeScript)
- Docker Compose (for multi-agent deployments and midterm)
- Redis or SQLite (agent state management)
- Git + GitHub for lab submissions
- Optional: LiteLLM (model routing), ChromaDB (vector store internals)

---

## How This Course Relates to Other Courses

| | EAI 6010 (Applications of AI) | **CS 6950 (This Course)** |
|---|---|---|
| **Program** | MPS (Professional Studies) | MS CS / MS AI |
| **Focus** | Applying AI to business problems | Engineering reliable AI agent infrastructure |
| **Depth** | Use APIs, evaluate results, deploy solutions | Build from scratch, understand internals, debug at the systems level |
| **Key skill** | Choosing the right AI approach for a problem | Designing agent architectures that work under failure, scale, and adversarial conditions |
| **Systems thinking** | "Does this API solve my problem?" | "Why did this agent loop? Where is the bottleneck? How do I prove it's safe?" |

---

## Instructor Background

Shrikant Tambe is a Senior SDE at AWS with 8 years building production AI and distributed systems. He created the open-source CloudWatch MCP Server (274K+ monthly downloads), designed multi-agent platforms on AWS Bedrock AgentCore, and built autonomous engineering pipelines that ship production code without human intervention. He authored research on AI system observability and reliability metrics for multi-agent systems.

## Recommended Readings & References

Each week includes suggested readings. None are mandatory textbooks — the field moves too fast for textbooks. Instead, students read a mix of foundational papers, technical documentation, and industry case studies.

**Foundational Papers:**
- Yao et al., "ReAct: Synergizing Reasoning and Acting in Language Models" (2023) — Week 1
- Vaswani et al., "Attention Is All You Need" (2017) — Background
- Wei et al., "Chain-of-Thought Prompting Elicits Reasoning in LLMs" (2022) — Week 1
- Wu et al., "AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation" (2023) — Week 4
- Park et al., "Generative Agents: Interactive Simulacra of Human Behavior" (2023) — Week 4
- Lewis et al., "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks" (2020) — Week 3

**Agent Protocols & Standards:**
- Model Context Protocol Specification v1.0 — https://modelcontextprotocol.io/specification
- OpenTelemetry GenAI Semantic Conventions — https://opentelemetry.io/docs/specs/semconv/gen-ai/
- Anthropic, "Building Effective Agents" (2024) — https://docs.anthropic.com/en/docs/build-with-claude/agent
- Google, "Agent Communication Protocols Landscape" (2025)

**Observability & Reliability:**
- Sigelman et al., "Dapper, a Large-Scale Distributed Systems Tracing Infrastructure" (2010) — Week 5
- Netflix, "Principles of Chaos Engineering" — https://principlesofchaos.org/ — Week 7
- Pal & Bhattacharya, "The Stochastic Gap: Agent Reliability as Blind-Spot Mass" (2025) — Week 7
- Tambe, "D-AER: Distributed Agent Execution Records" (2026, preprint) — Week 5
- TianPan, "SLO Error Budgets for Agent Systems" (2026) — Week 8

**Failure Analysis & Security:**
- Mazeika et al., "HarmBench: Standardized Evaluation of LLM Attacks and Defenses" (2024) — Week 9
- Perez et al., "Red Teaming Language Models with Language Models" (2022) — Week 9
- Inan et al., "Llama Guard: LLM-based Input-Output Safeguard" (2023) — Week 9
- DPBench, "95% Deadlock Rate in LLM-Based Coordination" (2025) — Week 7

**Industry Case Studies (discussed in class, not assigned):**
- The $47K LangChain agent loop (Fordel Studios, 2025)
- Zillow's AI home-buying system failure ($500M loss)
- AWS Bedrock AgentCore A2A Runtime architecture
- OpenAI's function calling evolution (2023–2026)

**Optional Textbook:**
- Chip Huyen, *Designing Machine Learning Systems* (O'Reilly, 2022) — Chapters 1, 9, 11

[← Back to home](/)
