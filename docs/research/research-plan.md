# Research Plan

## Phase 1: Foundation & Infrastructure (Month 1-2)
- Validate basic data ingestion from mock security tools.
- Evaluate Kafka throughput vs direct REST API ingestion.
- **Focus**: Stability, modularity, and data modeling.

## Phase 2: Core Detection & Threat Intel (Month 3-4)
- Implement baseline detection logic and correlation engines.
- Integrate initial threat intelligence feeds.
- Research optimal vector embedding strategies for threat context in Qdrant.

## Phase 3: AI Agents & Orchestration (Month 5-6)
- Research and implement LangGraph state machines for investigative workflows.
- Evaluate different LLMs (OpenAI, Gemini, local models) for reasoning capabilities vs cost and latency.
- Implement RAG for providing agents with historical alert context and MITRE ATT&CK mappings.

## Phase 4: Explainability & UX (Month 7-8)
- Focus on making agent decisions transparent and explainable to security analysts.
- Develop the frontend dashboard to visualize attack graphs and agent thought processes.
- Final performance benchmarking and threat hunting scenario simulations.
