---
layout: default
title: Shrikant Tambe
---

<div class="hero">
<img src="/assets/img/headshot.jpg" alt="Shrikant Tambe">
<div class="hero-text">
<h1>Shrikant Tambe</h1>
<p class="subtitle">Senior Software Development Engineer, Amazon Web Services<br>AI Agent Systems Researcher</p>
</div>
</div>

<nav>
<a href="#research">Research</a>
<a href="#publications">Publications</a>
<a href="#teaching">Teaching</a>
<a href="#blog">Blog</a>
<a href="#experience">Experience</a>
<a href="#contact">Contact</a>
</nav>

## Research
{: #research}

My research applies distributed systems observability principles to multi-agent AI systems — the thesis that **AI agent systems are distributed systems** and need the same rigor in tracing, reliability metrics, and operational tooling that we've spent 20 years building for microservices.

**Focus areas:**
- Multi-agent reasoning observability (D-AER framework)
- Cognitive SLOs for non-deterministic systems
- Emergent self-repair in multi-agent LLM systems
- The Agent Observability Lifecycle

I've surveyed 1,000+ recent papers in cs.AI and identified four wide-open gaps: multi-agent observability, cognitive SLOs, self-modifying agent monitoring, and cost of observability. My work addresses the first two.

## Publications
{: #publications}

<div class="pub">
<strong>Tambe, S.</strong> "D-AER: Distributed Agent Execution Records for Multi-Agent Reasoning Observability." <em>Under review</em>, 2026.<br>
Validated across 3 systems, N=1,400 LLM interactions, 6 Cognitive SLOs defined.
</div>

<div class="pub">
<strong>Tambe, S.</strong> "When and Why Multi-Agent LLM Systems Self-Repair." <em>In preparation</em>, 2026.
</div>

ORCID: [0009-0003-3432-3852](https://orcid.org/0009-0003-3432-3852)

## Teaching
{: #teaching}

Available for guest lectures and adjunct teaching in:
- **Applied AI Agent Systems** — multi-agent orchestration, observability, reliability, production deployment
- **Distributed Systems** — with modern AI/ML applications
- **Software Engineering in Practice** — production systems at AWS scale

My courses use real production case studies, hands-on assignments, and evaluation frameworks drawn from active research.

**Course Syllabi:**
- [CS 6950: Applied AI Agent Systems](/syllabus) — multi-agent orchestration, observability, reliability (CS track)
- [EAI 6010: Applications of Artificial Intelligence](/syllabus-eai6010) — applying modern AI to business problems across healthcare, finance, and operations (ML/AI track)

## Blog
{: #blog}

{% assign posts = site.posts | slice: 0, 5 %}
{% if posts.size > 0 %}
<ul class="post-list">
{% for post in posts %}
<li>
<span class="date">{{ post.date | date: "%B %d, %Y" }}</span><br>
<a class="title" href="{{ post.url }}">{{ post.title }}</a>
</li>
{% endfor %}
</ul>
{% if site.posts.size > 5 %}<p><a href="/blog">All posts →</a></p>{% endif %}
{% else %}
<p><em>Coming soon — writing on AI agent observability, distributed systems, and research notes.</em></p>
{% endif %}

## Experience
{: #experience}

### Amazon Web Services — 8 years
{: .experience-header}

I build query languages, AI agent platforms, and developer tooling at AWS scale. Three threads run through my work: **making complex systems accessible through language design**, **bringing AI agents from prototype to production**, and **designing systems that decompose safely at scale**.

**Autonomous Software Engineering Systems** (2025–present)
{: .role}

I designed Forge — a self-correcting autonomous pipeline where LLM agents take a feature specification and produce a shipped, reviewed code change with zero manual intervention. The architecture is a 5-phase state machine with async job queuing, crash-resilient agent sessions, and iterative self-repair from static analysis feedback. First end-to-end run delivered a production compiler feature in under 5 hours. This work directly informs my research on multi-agent system observability.

**AI Agent Platforms & Open-Source Developer Tooling** — CloudWatch (2024–2025)
{: .role}

I proposed and led delivery of the [CloudWatch MCP Server](https://github.com/awslabs/mcp) — an open-source Model Context Protocol integration that exposes CloudWatch APIs to AI agents and coding assistants. I authored the initial architecture and phased plan scoping MCP servers across all of CloudWatch, then led engineers across Seattle and Dublin to ship a unified server in 2 weeks. The server has been downloaded 482,000+ times and drove CloudWatch Logs API adoption to 1.1 million calls from MCP clients, creating measurable indirect revenue impact within 6 months of launch.

I designed Odyssey Hive — the sub-agent extensibility platform for CloudWatch's AI operations assistant. The core problem: integrating service-specific agents (EKS, RDS, OpenSearch), customer-hosted agents, and internal tooling agents into a single orchestration framework without fragmenting into per-agent custom logic. Hive provides three primitives: a registry with contract testing (validates agents return expected observation formats before activation), semantic discovery (selects applicable agents per investigation context from the pool of registered agents), and a secure execution layer with SigV4 authentication and per-investigation session isolation. The architecture uses AgentCore Runtime for compute (session support up to 8 hours, 100MB payloads, streaming) with a phased rollout: Phase 1 deploys Odyssey-managed agents via a lightweight interaction library, Phase 2 extends to service-team-hosted agents with contract testing gates, Phase 3 enables bring-your-own agents running in customer accounts with cross-account execution via investigation roles. The EKS troubleshooting agent shipped to production on this platform.

I led the Odyssey platform through its reInvent 2024 preview launch and into GA. I led delivery of Runbook Execution Agents — agents that extract procedures from customer-provided runbooks and execute them autonomously — in a 3-week timeline. I drove the 3P data source integration strategy — proposing a phased approach (OTEL as first format, single provider, reuse existing connectors) to resolve a multi-dimensional ambiguity across providers, data types, and backwards-compatible model changes.

**Cost Optimization & Operational Excellence** — CloudWatch Logs (2024)
{: .role}

I owned a cost optimization program end-to-end for CloudWatch Logs Frontend — defining scope, execution plan, and cross-team coordination with Kinesis, S3, and Finance. Out of $36.7M planned savings, the program captured $52.3M in projected annual savings and realized $36.2M YTD. I led 3 engineers across workstreams: Graviton instance migration ($10M+ savings, requiring heap memory tuning for the new architecture), Kinesis throughput reduction ($4M+ — I identified that shard count was uncharged and scoped the optimization to throughput only), and log compression algorithm change ($2M+, 26% reduction in compressed log size). I rolled out TLS 1.3 support across CloudWatch Logs with zero customer impact.

**Observability Query Language & Compiler Design** — CloudWatch Logs (2025–present)
{: .role}

I own feature development for ScrollQL, the query compiler powering CloudWatch Logs Insights — the primary log analysis surface for millions of AWS customers. ScrollQL compiles a SQL-like query language into execution plans over distributed log storage; I work across the full compiler stack from parser extensions through syntax tree rewrite rules to execution operators. I designed and shipped Lookup Tables end-to-end — a query-time enrichment primitive that performs hash-join lookups against customer-provided reference data, enabling log enrichment without data movement. I build aggregation functions that operate over streaming window semantics, and macro rewrite rules that expand high-level query patterns into optimized multi-stage execution plans.

**Service Architecture & Decomposition** — CloudWatch Logs (2022–2023)
{: .role}

I authored the high-level architecture for decomposing the monolithic CloudWatch Logs Frontend — a service handling 8M+ TPS across 70 APIs — into domain-specific microservices. I designed the orchestration model (evaluating and rejecting an API gateway approach in favor of direct service delegation for latency), the API grouping strategy (entity-based service boundaries with tightly-coupled entities co-located for caching efficiency), dependency isolation patterns (per-service thread pools, circuit breakers, rate-limited retries capped at 1% of failed requests), and a Data Access Layer abstraction with port/adapter pattern enabling zero-downtime traffic migration — services start in shadow mode with no-op adapters, then switch to live data access via dependency injection configuration. The phased execution plan I defined was adopted organization-wide for service extraction.

**Infrastructure Compliance at Scale** — AWS CloudFormation (2018–2022)
{: .role}

I designed and built the Hooks control plane service and led a team of 6 engineers to deliver CloudFormation Hooks to GA — a pre-provisioning compliance framework that intercepts stack operations and invokes customer-defined policy handlers before resources are created. I drove the design and implementation of blue/green hook integration with the Uluru Registry — bridging the provisioning engine with the type system. When the senior engineer leading the project moved to another initiative, I stepped into the technical leadership role — navigating team churn and mid-flight architectural changes while onboarding new engineers and driving the project through internal beta, external beta, and GA. I led the integration of Hooks as a new type into the CloudFormation Registry, and established the sprint process for the dedicated Policy-as-Code team that continued delivery after my transition.

### Research
{: .role}

My independent research bridges distributed systems and AI — treating multi-agent LLM systems as distributed systems that need the same observability, reliability contracts, and operational rigor we've built for microservices over two decades. Two papers in progress; details in [Publications](#publications).

### Education

**MS** — University of Utah, David Eccles School of Business (2016–2017) · **BE** — Computer Science

## Contact
{: #contact}

- ORCID: [0009-0003-3432-3852](https://orcid.org/0009-0003-3432-3852)
- LinkedIn: [linkedin.com/in/shrikanttambe](https://www.linkedin.com/in/shrikanttambe/)
- Email: [shrikant_tambe@outlook.com](mailto:shrikant_tambe@outlook.com)
