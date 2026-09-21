# System Architecture

## Overview
AutoSOC is an Explainable Multi-Agent AI Platform for Autonomous Security Operations and Threat Hunting. The system uses a modular monolithic backend designed for future scalability and agent orchestration.

## Data Flow
1. **Frontend**: (Future) React/Vue-based dashboard interacting with the backend via REST/WebSockets.
2. **FastAPI**: The core API gateway and backend orchestration layer.
3. **Event Ingestion**: Security events and logs are ingested, potentially queued via **Kafka** for high-throughput scenarios, and processed by the detection pipeline.
4. **PostgreSQL**: Relational database for structured data (users, alerts, incident metadata, system configurations).
5. **Redis**: In-memory data store used for caching, rate limiting, and celery/background task queues.
6. **Qdrant**: Vector database for storing threat intelligence embeddings, historical alert embeddings, and enabling RAG (Retrieval-Augmented Generation) capabilities for the agents.
7. **LangGraph Agent Layer**: (Future) State-machine based multi-agent system handling automated investigations and threat hunting.
8. **Security Tools**: (Future) External integrations (SIEMs, EDRs, Threat Intel feeds) exposed as tools for the agents.
9. **LLM Provider Abstraction**: A standardized interface allowing agents to interact seamlessly with OpenAI, xAI, Gemini, or Anthropic.
