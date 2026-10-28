# 📁 Projects

Every project below is engineered to a production standard, not portfolio-toy
standard: automated tests, CI, typed code, Docker deployment, and a versioned
evaluation scorecard.

---

## 🤖 Agentic AI Systems

| Project | What it does | Highlights | Stack | Quality bar |
|---|---|---|---|---|
| **[LangGraph Multi-Agent Orchestrator](https://github.com/kanderson-ai-dev/langgraph-multiagent-orchestrator)** | Multi-tenant Supervisor–Workers platform: a company submits a report brief and the system assembles the right agent team for that report type | LLM Supervisor with dynamic routing and parallel `Send()` fan-out · bounded Writer ↔ Reviewer debate · per-job `budget_usd` enforced before every dispatch · SHA-256 hash-chained audit trail · real `interrupt()` human-in-the-loop that survives restarts | Python · LangGraph · FastAPI · SQLite · Docker | 415 tests, 92% coverage, `mypy --strict`, browser E2E, quality gates in CI |
| **[MCP Agent Toolkit](https://github.com/kanderson-ai-dev/mcp-agent-toolkit)** | Production-shaped Model Context Protocol system: an MCP server with four guarded tools and an agent that discovers and calls them at runtime | Runtime tool discovery via `tools/list` · versioned Prompt Registry with promotions gated by live A/B evaluation · hash-chained audit log · LLM-as-judge scorecard on a different model than the agent | Python · MCP SDK · FastAPI · React/Vite · Docker | 517 offline tests, 93% coverage, `mypy --strict`, Playwright e2e |
| **[Agentic RAG & Knowledge System](https://github.com/kanderson-ai-dev/agentic-rag-system)** | Self-RAG microservice that proves its answers instead of asserting them | Hybrid retrieval (vector + graph) · self-grading loop that rewrites weak queries · human escalation instead of hallucinating · RAGAS-style scorecard versioned in git and gated in CI | Python · LangGraph · FastAPI · Pinecone/Chroma · Neo4j | 394 tests + 27 browser e2e, 95% coverage, cost tracked per query |
| **[Guardrailed Agentic AI API](https://github.com/kanderson-ai-dev/agentic-api)** | Guardrailed, observable single-agent service behind a REST API | Input/output guardrails against prompt injection and prompt leakage (OWASP LLM01/LLM02) · multi-turn memory · SSE streaming · LangSmith/Langfuse tracing, JSON logs and Prometheus metrics | Python · LangGraph · FastAPI · SQLite · LangSmith | 179 tests, 98% coverage, CI green with zero secrets |

---

📩 **Want something like this for your business?** contact@kaarstenanderson.com
