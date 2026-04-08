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

I surveyed over 1,000 recent papers in cs.AI and cs.SE. The gap is stark:

- **Distributed tracing for agents:** Almost nothing. A few papers track token usage. None capture the *reasoning flow* across agent boundaries — the equivalent of a span propagating through service calls.
- **Cognitive SLOs:** Zero prior work. We have latency SLOs and error rate SLOs for APIs, but no equivalent for "did the agent reason correctly?" or "did delegation preserve intent?"
- **Cost of observability:** In traditional systems, we accept 1-3% overhead for tracing. Nobody has measured what observability costs in agent systems where the "computation" is an LLM inference call.

## D-AER: Distributed Agent Execution Records

My first paper introduces D-AER — a structured record format that captures what each agent in a multi-agent system *decided*, *why* it decided it, and *what happened* as a result. Think of it as a distributed trace, but for reasoning rather than request routing.

Each D-AER record captures:
- The agent's identity and role in the system
- The input it received (delegation context)
- The reasoning steps it took (tool calls, sub-delegations, internal chain-of-thought)
- The output it produced and confidence signals
- Timing, token usage, and cost metadata

Layered on top: six **Cognitive SLOs** that define what "healthy" looks like for an agent system — covering delegation fidelity, reasoning completeness, output consistency, and more.

I validated D-AER across three different multi-agent architectures, capturing 1,400+ LLM interactions. The framework detected failure modes that were invisible to existing monitoring: silent delegation drift, reasoning truncation under token pressure, and confidence-accuracy misalignment.

## What's next

I'm preparing this work for publication and drafting an OpenTelemetry Enhancement Proposal (OTEP) to bring agent observability into the OTel standard. If multi-agent systems are going to run in production — and they already are — they need production-grade observability.

More posts coming on Cognitive SLOs, the experiment methodology, and what I learned about emergent self-repair in multi-agent systems.

*If you're working on agent observability or have thoughts on this direction, I'd love to hear from you — [reach out via ORCID](https://orcid.org/0009-0003-3432-3852).*
