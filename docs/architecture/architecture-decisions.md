# Architecture Decisions

## 1. Modular Monolith vs Microservices
**Decision:** Modular Monolith using FastAPI.
**Rationale:** Given the team size (3 developers) and the 8-month timeline, a modular monolith minimizes operational overhead while maintaining logical separation. Modules (e.g., `alerts`, `agents`, `detection`) will have strict boundaries within the `app/` directory, allowing for future extraction into microservices if necessary.

## 2. LLM Provider Abstraction
**Decision:** Abstract LLM interactions behind a `ProviderAdapter` interface.
**Rationale:** 
- Vendor lock-in prevention.
- Flexibility to route different tasks to different models based on cost, speed, or reasoning capabilities.
- Concept: `Agent -> LLMService -> ProviderAdapter -> [OpenAI | xAI | Gemini | Anthropic]`

## 3. Persistent Data Storage
**Decision:** PostgreSQL as primary, Redis for ephemeral, Qdrant for vectors, Kafka for streaming.
**Rationale:** 
- **Postgres**: ACID compliance and relational structure are ideal for alerts, RBAC, and incident metadata.
- **Redis**: Fast caching and task queuing.
- **Qdrant**: Essential for RAG (Retrieval-Augmented Generation) in threat intelligence context retrieval.
- **Kafka**: Reliable, high-throughput event ingestion pipeline for security logs.
