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

My courses use real production case studies, hands-on agent-building assignments, and evaluation frameworks drawn from active research. [Syllabus available on request.](/syllabus)

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

**Amazon Web Services** — Senior Software Development Engineer (2018–present)

- **CloudWatch Logs (2022–present):** Full-stack Lookup Tables feature launch across 32 AWS regions. Built AI Agents Platform: Odyssey AI Assistant, SubAgent Registry, EKS/Runbook agents. 124 shipped code reviews in 15 months.
- **AWS CloudFormation (2018–2021):** Led CloudFormation Hooks from zero to GA launch. Built Registry Service, region expansion across all AWS partitions.

**Education:**
- MS — University of Utah, David Eccles School of Business (2016–2017)
- BE — Engineering / Computer Science

## Contact
{: #contact}

- ORCID: [0009-0003-3432-3852](https://orcid.org/0009-0003-3432-3852)
- LinkedIn: [linkedin.com/in/shrikanttambe](https://www.linkedin.com/in/shrikanttambe/)
- Email: [your-academic-email]
