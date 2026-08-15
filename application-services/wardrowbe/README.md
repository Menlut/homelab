# Wardrowbe

Wardrowbe is deployed as a multi-container application with PostgreSQL, Redis,
a backend API, a web frontend, and a background worker.

## Architecture

```text
Frontend
   |
   v
Backend API ---- Redis
   |               |
   v               v
PostgreSQL      Worker
                   |
                   v
              Local AI service
```

## Implementation Highlights

- Uses PostgreSQL for persistent relational data.
- Uses Redis for application and worker coordination.
- Runs a separate worker process for background tasks.
- Supports OIDC configuration for authentication.
- Connects backend and worker services to the external AI-services network.
- Connects PostgreSQL to the centralized database-admin network.
- Uses health checks for PostgreSQL, Redis, and the backend.
- Externalizes application secrets, identity-provider values, and AI settings.

## Publishing Notes

All authentication secrets, database credentials, URLs, model names, and API
credentials are represented by placeholders in `.env.example`.

## Skills Demonstrated

- Multi-tier application architecture
- PostgreSQL and Redis
- Background workers
- OIDC configuration
- Docker health checks
- Cross-stack external networks
- Local AI integration
- Secret management
