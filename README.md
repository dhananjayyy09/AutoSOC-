# AutoSOC

An Explainable Multi-Agent AI Platform for Autonomous Security Operations and Threat Hunting.

## Overview
AutoSOC is a university major project designed to automate security operations and provide actionable, explainable threat hunting capabilities through a multi-agent AI architecture.

## Architecture
- **Backend:** FastAPI, PostgreSQL, Redis, Qdrant, Kafka
- **Frontend:** (To be implemented)
- **AI/Agents:** LangGraph (Planned)

## Development Setup

1. Copy `.env.example` to `.env` and fill in API keys if required (LLMs).
```bash
cp .env.example .env
```

2. Start the local infrastructure using Docker Compose:
```bash
docker-compose up -d
```

3. Setup backend environment:
```bash
cd backend
python -m venv venv
# On Windows
venv\Scripts\activate
# On Unix
# source venv/bin/activate
pip install -r requirements.txt
```

4. Run the backend locally:
```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```
