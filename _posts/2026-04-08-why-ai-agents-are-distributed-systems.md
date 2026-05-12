---
layout: post
title: "Why AI Agent Systems Are Distributed Systems"
---

Last year I started building multi-agent AI systems at work — orchestrators dispatching tasks to specialized LLM agents, agents calling tools, tools calling other agents. The systems worked. Then they failed. And when they failed, I couldn't figure out *why*.

The debugging experience felt familiar. Not "new frontier of AI" familiar — more like "microservices in 2014" familiar. Requests disappearing between components. Latency spikes with no obvious source. Partial failures that cascaded unpredictably. The same classes of problems I'd spent years solving with distributed tracing, SLOs, and structured logging in traditional backend systems.

That's when the thesis clicked: **multi-agent AI systems are distributed systems**, and they need the same observability rigor we've spent two decades building for microservices.

## The gap is real

Consider what happens when an orchestrator agent delegates a research task to three sub-agents, aggregates their results, and produces a summary. If the summary is wrong, where did the error enter? Was it a bad delegation prompt? Did one sub-agent hallucinate? Did the aggregation step lose critical context? Did a tool call return stale data?

In a microservice architecture, we'd answer these questions with distributed traces, structured logs, and service-level objectives. In multi-agent AI systems today, we have... print statements. Maybe some token counts.

The gap is stark:

- **Distributed tracing for agents:** Almost nothing. A few tools track token usage. None capture the *reasoning flow* across agent boundaries — the equivalent of a span propagating through service calls.
- **Reliability metrics for non-deterministic systems:** We have latency SLOs and error rate SLOs for APIs, but no equivalent for "did the agent reason correctly?" or "did delegation preserve intent?"
- **Cost of observability:** In traditional systems, we accept 1-3% overhead for tracing. Nobody has measured what observability costs in agent systems where the "computation" is an LLM inference call.

## What I'm working on

I'm developing a framework that brings distributed systems observability principles to multi-agent AI — structured reasoning provenance, cross-agent trace correlation, and reliability metrics designed for non-deterministic systems. The work is validated across multiple architectures and is being prepared for publication.

If you're building multi-agent systems in production and struggling with the same debugging problems, I'd love to hear from you — [reach out via ORCID](https://orcid.org/0009-0003-3432-3852) or [LinkedIn](https://www.linkedin.com/in/shrikanttambe/).
