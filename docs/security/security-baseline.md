# Security Baseline

## 1. Secrets Management
- **NEVER** commit `.env` files or hardcoded credentials to version control.
- Use `.env.example` to declare required environment variables.
- API keys (OpenAI, xAI, etc.) must be injected at runtime.

## 2. API Security
- All sensitive endpoints must require authentication (e.g., JWT).
- Implement rate limiting (via Redis) to prevent abuse.
- Input validation on all endpoints using Pydantic models.

## 3. Dependency Management
- Regularly update `requirements.txt` and `package.json` to patch known vulnerabilities.
- Use explicit version pinning for production deployments.

## 4. Execution Environment
- Docker containers should not run as root where possible.
- Avoid exposing databases (Postgres, Qdrant) or message queues (Kafka, Redis) directly to the public internet. Use internal docker networks.
