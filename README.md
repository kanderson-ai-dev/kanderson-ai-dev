
<div align="center">
  <img src="assets/banner.png" alt="Kaarsten Anderson — Agentic AI Developer" width="100%" />
</div>

<div align="center">

### I build production-grade AI agents — guardrailed, evaluated, observable, and shipped with the CI/CD discipline a real business needs before an agent touches production traffic.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kaarsten-anderson/)
[![Email](https://img.shields.io/badge/Email-kaarsten.anderson%40gmail.com-D14836?logo=gmail&logoColor=white)](mailto:kaarsten.anderson@gmail.com)

</div>

---

## 👋 About

8+ years as a full-stack developer (2019–present), the last three focused on LLM
applications and, since 2024, on multi-agent systems built with **LangGraph**.

I don't ship tool-calling demos — I ship the layer above the demo: input/output
guardrails against prompt injection (OWASP LLM Top 10), evaluation scorecards
gated in CI, cost-governed autonomy, human-in-the-loop escalation that survives
a restart, and the observability to prove all of it in production, not just in
a README claim.

- 🤖 **Agentic AI** — LangGraph multi-agent orchestration, Self-RAG, autonomous research agents, guardrailed agent APIs
- 🕷️ **Data extraction at scale** — production-shaped scraping pipelines, browser automation, scheduled monitoring services
- 🧪 **Evaluation-driven** — every system ships with a versioned quality scorecard (faithfulness, cost, latency) gated in CI, not vibes

📄 **[Check out all of my projects →](PROJECTS.md)**

---

## 🛠️ Stack

**Agentic AI / LLM**
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?logo=langgraph&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C)
![OpenAI](https://img.shields.io/badge/OpenAI%20API-412991?logo=openai&logoColor=white)
![LangSmith](https://img.shields.io/badge/LangSmith-observability-1C3C3C)
![Pinecone](https://img.shields.io/badge/Pinecone-vector%20store-000000)
![Neo4j](https://img.shields.io/badge/Neo4j-graph%20store-008CC1?logo=neo4j&logoColor=white)

**Backend / API**
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?logo=pydantic&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?logo=sqlalchemy&logoColor=white)

**Frontend**
![React](https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)

**Scraping / Automation**
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?logo=playwright&logoColor=white)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup4-43B02A)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)

**Infra / Quality**
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/CI-GitHub%20Actions-2088FF?logo=githubactions&logoColor=white)
![Pytest](https://img.shields.io/badge/pytest-0A9EDC?logo=pytest&logoColor=white)
![mypy](https://img.shields.io/badge/mypy--strict-blue)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white)

---

## 🚀 Featured Projects

### Agentic AI Systems

| Project | What it does | Stack |
|---|---|---|
| **[LangGraph Multi-Agent Orchestrator](https://github.com/kanderson-ai-dev/langgraph-multiagent-orchestrator)** | Multi-tenant Supervisor–Workers platform: dynamic agent teams, runtime `Send()` fan-out, cost-governed autonomy, hash-chained audit trail | LangGraph · FastAPI · Postgres |
| **[Autonomous Web Research Agent](https://github.com/kanderson-ai-dev/agentic-web-researcher)** | Planner dispatches parallel search/scrape workers, a critic re-plans, a writer synthesizes a cited report | LangGraph · FastAPI |
| **[Research Agent — Agents SDK port](https://github.com/kanderson-ai-dev/research-agent-sdk-port)** | The same research agent on a second framework — identical use case/API/scorecard, so LangGraph vs Agents SDK is compared with measured numbers | OpenAI Agents SDK · FastAPI |
| **[Agentic RAG & Knowledge System](https://github.com/kanderson-ai-dev/agentic-rag-system)** | Self-RAG loop: hybrid vector+graph retrieval, self-grading, human escalation instead of hallucinating | LangGraph · Pinecone · Neo4j |
| **[Guardrailed Agentic AI API](https://github.com/kanderson-ai-dev/agentic-api)** | Guardrailed single-agent service: OWASP LLM01/LLM02 defenses, multi-turn memory, SSE streaming | LangGraph · FastAPI |
| **[MCP Agent Toolkit](https://github.com/kanderson-ai-dev/mcp-agent-toolkit)** | MCP server + agent client over stdio: runtime tool discovery, sandbox/SELECT-only/LLM01 guardrails, request-ID-correlated observability | TypeScript · MCP SDK · OpenAI |

### Web Scraping & Data Automation

| Project | What it does | Stack |
|---|---|---|
| **[Enterprise Data Pipeline API](https://github.com/kanderson-ai-dev/enterprise-data-pipeline-api)** | Scheduled, self-healing scraping pipeline with Postgres history and an authenticated REST API | FastAPI · Postgres · Docker |
| **[Dynamic Scraper & AI Change Monitor](https://github.com/kanderson-ai-dev/dynamic-scraper-ai-monitor)** | Browser-driven monitor for JS-heavy sites — change detection with optional LLM extraction, multi-channel alerts | Playwright · SQLAlchemy |
| **[Web Scraper & Directory Extractor](https://github.com/kanderson-ai-dev/python-web-scraper-template)** | Schema-validated catalog/directory extractor — clean CSV/XLSX in a 1-2 hour engagement | BeautifulSoup · Pandas |

📄 **[See the full breakdown — architecture, evaluation metrics, and links for every project →](PROJECTS.md)**

---

<div align="center">

📩 **kaarsten.anderson@gmail.com** · 💼 Open to Agentic AI / LLM engineering engagements

</div>
