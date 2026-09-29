# 📁 Projects

All projects below are engineered to a production standard, not portfolio-toy
standard: automated tests, CI, typed code, Docker deployment, and — for the
agentic systems — a versioned evaluation scorecard. Two categories, listed by
depth within each.

---

## 🤖 Agentic AI Systems

A four-project ladder, each one a tier above the last: single guardrailed
agent → self-correcting RAG → hybrid multi-agent research → reusable
multi-tenant orchestration framework — plus the open-protocol toolkit those
agents' tool surfaces speak.

### 1. [LangGraph Multi-Agent Orchestrator](https://github.com/kanderson-ai-dev/langgraph-multiagent-orchestrator)

Multi-tenant Supervisor–Workers platform where a company submits a report
brief and the system assembles the right agent team for that report type.

- LLM Supervisor routes work dynamically (no fixed edges) and fans out in
  parallel via LangGraph `Send()` when the mandate calls for it
- Bounded Writer ↔ Reviewer debate that must terminate — proven by a
  dedicated test, not by luck
- Cost-governed autonomy: per-job `budget_usd` enforced before every dispatch,
  escalates to a human who can fund/approve/reject
- SHA-256 hash-chained audit trail — every finished report is tamper-evident
- Real `interrupt()` human-in-the-loop on a SQLite checkpointer — survives
  restarts
- **Stack:** LangGraph · FastAPI · Postgres-shaped state · Docker
- **Quality bar:** 136 tests, 90% coverage, `mypy --strict`, browser E2E, EDD
  quality gates in CI

### 2. [Autonomous Web Research Agent](https://github.com/kanderson-ai-dev/agentic-web-researcher)

Autonomous research agent: give it a topic, it plans, searches and scrapes
the live web in parallel, verifies every citation, and writes a defensible
report.

- Planner dispatches parallel search/scrape/document-parse workers
- Critic grades evidence and can trigger bounded re-planning rounds
- Every citation's quote is checked against the actual fetched source text —
  unverifiable claims are dropped and counted
- Indirect prompt-injection defense: scraped pages are treated as data, never
  instructions (OWASP LLM01)
- **Stack:** LangGraph · FastAPI · BeautifulSoup/Playwright
- **Quality bar:** 143 tests, 93% coverage, `mypy --strict`, offline EDD
  scorecard reproducible via `run_eval`

### + [Research Agent — OpenAI Agents SDK port](https://github.com/kanderson-ai-dev/research-agent-sdk-port) — the framework comparison

A **full-fidelity port** of the research agent above onto the **OpenAI
Agents SDK** — a controlled experiment: same use case, same API, same
frontend, same guardrails, same versioned scorecard, different agentic
runtime.

- `StateGraph`+`Send()`+reducers → `Agent`/`Runner` with `output_type`
  contracts + `asyncio.gather` fan-out + explicit merges
- Native `@input_guardrail`/`@output_guardrail` wiring — including the
  `run_in_parallel=False` fix that keeps guardrail-first real
- HITL without a checkpointer: serialized `PipelineContext` pause/resume
  instead of `interrupt()`+`AsyncSqliteSaver`
- LangSmith tracing via `OpenAIAgentsTracingProcessor`; offline `StubModel`
  implementing the SDK's `Model` interface
- **Stack:** OpenAI Agents SDK · FastAPI · Pydantic v2 · LangSmith
- **Quality bar:** 147 tests, 92% coverage, `mypy --strict`, identical
  scorecard gates — side-by-side table in the README

### 3. [Agentic RAG & Knowledge System](https://github.com/kanderson-ai-dev/agentic-rag-system)

Self-RAG microservice that proves its answers instead of asserting them.

- Hybrid retrieval — vector (Pinecone/Chroma) + graph (Neo4j/NetworkX) fusion
  to reduce hallucination
- Self-correction loop: grades retrieved context, rewrites the query when
  evidence is weak, escalates to a human when retries run out
- RAGAS-style scorecard versioned in git and gated in CI — faithfulness 0.90,
  answer relevancy 0.90 on the latest run
- **Stack:** LangGraph · FastAPI · Pinecone · Neo4j
- **Quality bar:** 144 tests, 96% coverage, cost tracked per query
  (≤ $0.01 target)

### 4. [Guardrailed Agentic AI API](https://github.com/kanderson-ai-dev/agentic-api)

The foundation of the ladder: a guardrailed, observable single-agent service
behind a REST API.

- Input/output guardrails against prompt injection and system-prompt leakage
  (OWASP LLM01/LLM02) — blocked requests never reach the LLM
- Multi-turn memory via a SQLite checkpointer, SSE streaming, retry/backoff
  on transient LLM errors
- Full observability: LangSmith tracing, structured JSON logs, Prometheus
  metrics, all correlated by request ID
- **Stack:** LangGraph · FastAPI · LangSmith
- **Quality bar:** 52 tests, 95% coverage, CI green with zero secrets

### + [MCP Agent Toolkit](https://github.com/kanderson-ai-dev/mcp-agent-toolkit) — the protocol layer

A standalone **Model Context Protocol** server + agent client in strict
TypeScript — the open standard the rest of the ladder's tool surfaces speak,
implemented end-to-end instead of bespoke bindings.

- Real MCP server (`@modelcontextprotocol/sdk`, stdio) exposing four guarded
  tools: `web_search`, read-only `db_query`, sandboxed `read_file`/`write_file`
- The agent discovers tools at runtime via `tools/list` — the protocol is
  the boundary; the recorded demo shows it recovering from a live SQL error
- Guardrails at the wire: single-SELECT guard + `readonly` connection,
  `realpath` path sandbox, output sanitization (OWASP LLM01), per-tool
  rate limiting
- Request-ID correlation via `params._meta`, pino JSON logs, Prometheus
  metrics, 100% offline test mode (`StubLLM`)
- **Stack:** TypeScript · MCP SDK · OpenAI tool-calling · SQLite · Docker
- **Quality bar:** 110 tests incl. real-stdio integration, 98.5% coverage,
  `tsc --strict`, CI green with zero secrets

---

## 🕷️ Web Scraping & Data Automation

Production-shaped extraction pipelines — the tier of scraping work that's
actually worth billing for: scheduling, persistence, resilience, and an API
around the extraction, not a script that dumps a CSV.

### 1. [Enterprise Data Pipeline API](https://github.com/kanderson-ai-dev/enterprise-data-pipeline-api)

A scheduled, self-healing scraping pipeline with a documented API on top.

- APScheduler runs cycles on an interval; every run is logged as a job with
  `pending → running → success | failed | blocked` states — `blocked` is a
  first-class operational signal, not a crash
- DB-backed rotating proxy pool with automatic deactivation after repeated
  failures
- Idempotent persistence — SHA-256 content hash means re-scrapes never create
  duplicates
- Authenticated REST API (`X-API-Key`), Prometheus metrics, Swagger docs
- **Stack:** FastAPI · PostgreSQL · Alembic · Docker Compose
- **Quality bar:** 42 tests fully offline (ephemeral Postgres via
  `testcontainers`, mocked HTTP)

### 2. [Dynamic Scraper & AI Change Monitor](https://github.com/kanderson-ai-dev/dynamic-scraper-ai-monitor)

Turns any JS-heavy, dynamically-paginated site into a monitored dataset with
change alerts.

- Playwright drives a real browser — AJAX pagination and infinite scroll work
  out of the box, where a static scraper gets zero results
- Optional LLM-based extraction for messy/markup-unstable pages (degrades
  cleanly to the deterministic parser if no API key is set)
- Hash-based change detection — one alert per real change, zero noise on
  identical re-scrapes
- Multi-channel alerts (Discord/Slack webhook, SMTP email)
- **Stack:** Playwright · SQLAlchemy 2.0 · SQLite/Postgres
- **Quality bar:** 50 tests, zero live network calls in CI

### 3. [Web Scraper & Directory Extractor](https://github.com/kanderson-ai-dev/python-web-scraper-template)

The fast, fixed-price tier: turn a public catalog or directory into a clean
dataset.

- Schema-validated output via Pydantic — no malformed prices or broken URLs
  in the export
- Never crashes on malformed HTML — safe fallbacks on every field extraction
- Detail-page enrichment for fields missing from listing pages, with graceful
  per-record failure handling
- Clean CSV (Excel-compatible) and formatted `.xlsx` export, zero manual
  cleanup
- **Stack:** BeautifulSoup4/lxml · Pandas · Pydantic
- **Quality bar:** unit-tested HTTP client, parser, and exporter; no live
  network needed in CI

---

<div align="center">

⬅️ [Back to profile](README.md)

</div>
