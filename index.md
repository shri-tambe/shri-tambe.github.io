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
<a href="#teaching">Teaching</a>
<a href="#blog">Blog</a>
<a href="#experience">Experience</a>
<a href="#contact">Contact</a>
</nav>

## Research
{: #research}

My research applies distributed systems observability principles to multi-agent AI systems — the thesis that **AI agent systems are distributed systems** and need the same rigor in tracing, reliability metrics, and operational tooling that we've spent 20 years building for microservices.

**Focus areas:**
- Multi-agent reasoning observability
- Reliability metrics for non-deterministic AI systems
- Production engineering for autonomous agent workflows

Paper in progress — details available upon request.

ORCID: [0009-0003-3432-3852](https://orcid.org/0009-0003-3432-3852)

## Teaching
{: #teaching}

I am actively seeking part-time teaching opportunities in the Seattle area. My courses are designed for graduate students and working professionals.

**Areas I can teach:**
- **Applied AI Agent Systems** — multi-agent orchestration, observability, reliability, production deployment
- **Applications of Artificial Intelligence** — applying modern AI to business problems across healthcare, finance, and operations
- **Distributed Systems** — with modern AI/ML applications

**Draft Course Syllabi** (proposed, not yet taught):
- [CS 6950: Applied AI Agent Systems](/syllabus-cs6950-ai-agent-systems) — multi-agent orchestration, observability, reliability (CS track)
- [EAI 6010: Applications of Artificial Intelligence](/syllabus-eai6010-applications-of-ai) — applying modern AI to business problems (ML/AI track)

## Blog
{: #blog}

I write about AI systems, observability, and distributed systems on Medium.

**Published:**
- [AWS CloudWatch MCP and Skills: Stop Querying, Start Reasoning](https://shri-tambe.medium.com/aws-cloudwatch-mcp-and-skills-stop-querying-start-reasoning-657184b951ea) — May 2025

**Coming soon:**
- Why AI Agents Are Distributed Systems

[All posts on Medium →](https://shri-tambe.medium.com/)

## Experience
{: #experience}

### Amazon Web Services — 12 years industry experience
{: .experience-header}

I build query languages, AI agent platforms, and developer tooling at AWS scale. Three threads run through my work: **making complex systems accessible through language design**, **bringing AI agents from prototype to production**, and **designing systems that decompose safely at scale**.

**AI Agent Platforms & Open-Source Developer Tooling** — CloudWatch (2024–2025)
{: .role}

I proposed and led delivery of the [CloudWatch MCP Server](https://github.com/awslabs/mcp) — an open-source Model Context Protocol integration that exposes CloudWatch APIs to AI agents and coding assistants. Led engineers across Seattle and Dublin to ship in 2 weeks. 274K+ monthly downloads; drove CloudWatch Logs API adoption to 2.91M cumulative calls from MCP clients.

I designed the sub-agent extensibility platform for CloudWatch's AI operations assistant — a registry with contract testing, semantic discovery, and secure execution layer with SigV4 authentication. The EKS troubleshooting agent shipped to production on this platform.

**Observability Query Language & Compiler Design** — CloudWatch Logs (2022–present)
{: .role}

I own feature development for the query compiler powering CloudWatch Logs Insights — the primary log analysis surface for millions of AWS customers. Leading an 8-engineer team delivering query-language parity with Splunk and Sumo Logic. Designed and shipped Lookup Tables (query-time enrichment via hash-join), aggregation functions over streaming windows, and macro rewrite rules for optimized execution plans.

**Service Architecture & Decomposition** — CloudWatch Logs (2022–2023)
{: .role}

Drove org-wide decomposition of 70+ APIs from a monolithic front-end (8M+ TPS) into independent micro-services. Designed a dedicated cache fleet for 9.3M req/s Frontend (48% cache reduction, 70% DynamoDB read reduction).

**Infrastructure Compliance at Scale** — AWS CloudFormation (2018–2022)
{: .role}

Tech lead for 6 engineers. Designed and delivered CloudFormation Hooks to GA — a pre-provisioning compliance framework. $77–100K/week revenue, 2.38M invocations/year. Architectural foundation for the dedicated Policy-as-Code team.

### Education

**MS** — University of Utah, David Eccles School of Business (2016–2017) · **BE** — Computer Science

## Contact
{: #contact}

- ORCID: [0009-0003-3432-3852](https://orcid.org/0009-0003-3432-3852)
- LinkedIn: [linkedin.com/in/shrikanttambe](https://www.linkedin.com/in/shrikanttambe/)
- GitHub: [github.com/shri-tambe](https://github.com/shri-tambe)
- Email: [shrikant_tambe@outlook.com](mailto:shrikant_tambe@outlook.com)
