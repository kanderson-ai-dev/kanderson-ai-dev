<div align="center">

# 📂 Project Catalog

**Production-shaped reference implementations** — each one tested, CI'd, Dockerized, and built to be cloned, pointed at a new target, and adapted to a client's use case.

[← Back to profile](./README.md)

</div>

---

## �️ Web Scraping & Data Pipelines

| Project | What it does | Tech Stack | Links |
|---|---|---|---|
| **Python Web Scraper & Directory Extractor** | Turns any public catalog/directory site into a clean, schema-validated CSV/Excel dataset — designed to be cloned and shipped within a 1-2 hour engagement. | Python, BeautifulSoup, Pydantic, Pandas, `tenacity` | [Repo](https://github.com/kanderson-ai-dev/python-web-scraper-template) |
| **Dynamic Scraper & AI-Powered Change Monitor** | Watches JS-heavy, dynamically-paginated sites; detects price/stock changes via hash comparison and pushes real-time alerts to Discord/Slack/email. Optional LLM-based extraction for unstable markup. | Python, Playwright, SQLAlchemy, Pydantic, OpenAI-compatible LLMs | [Repo](https://github.com/kanderson-ai-dev/dynamic-scraper-ai-monitor) |
| **Enterprise Data Pipeline API** | Scheduled, self-healing scraping pipeline with proxy rotation, job history, and an authenticated REST API serving the collected data — deployable with one `docker compose up`. | Python, FastAPI, PostgreSQL, Alembic, APScheduler, Docker | [Repo](https://github.com/kanderson-ai-dev/enterprise-data-pipeline-api) |

## 🤖 Agentic AI & LLM Systems

| Project | What it does | Tech Stack | Links |
|---|---|---|---|
| **Agentic API** | Guardrailed, observable LangGraph agent behind a REST API — input/output screening against prompt injection (OWASP LLM01/LLM02), multi-turn memory, SSE streaming, and full observability (LangSmith, Prometheus, structured logs). | Python, FastAPI, LangGraph, OpenAI, LangSmith | [Repo](https://github.com/kanderson-ai-dev/agentic-api) |

---

<div align="center">

Need one of these adapted to your site or use case? **[Let's talk →](./README.md#-lets-work-together)**

</div>
