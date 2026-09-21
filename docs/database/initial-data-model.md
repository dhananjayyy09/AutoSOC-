# Initial Data Model Concepts

*Note: This is a conceptual schema and will be implemented iteratively via SQLAlchemy.*

## Core Entities

### User & Authentication
- `User`: id, email, hashed_password, role, created_at, updated_at
- `Role`: id, name, permissions

### Security Operations
- `Event`: id, timestamp, source, event_type, raw_data, parsed_data
- `Alert`: id, title, severity, status, source_event_ids, created_at, assigned_to
- `Incident`: id, title, status, severity, created_at, closed_at, resolution_summary

### Threat Intelligence & Context
- `IndicatorOfCompromise` (IoC): id, type (ip, hash, domain), value, confidence, tags
- `MitreTechnique`: id, technique_id, name, description, tactics

### Agent Operations
- `Investigation`: id, incident_id, agent_id, status, findings, created_at
- `AgentActionLog`: id, investigation_id, step, action_taken, reasoning (Explainability focus), result
