# Immich

Immich provides self-hosted photo and video management backed by a database
and cache service.

## Components

| Container | Role |
|---|---|
| `immich-server` | Main Immich application service |
| `immich-microservices` | Background processing service in this deployment snapshot |
| `redis` | Valkey-backed cache/service dependency |
| `database` | PostgreSQL database with vector extensions |

## Implementation Highlights

- Mounts `/dev/dri` on the main server for hardware access.
- Stores uploaded media and database data outside disposable containers.
- Uses health checks for cache and database dependencies.
- Applies CPU and memory limits to the main server.
- Uses digest-pinned images for Valkey and PostgreSQL.
- Keeps the machine-learning service disabled in this deployment snapshot.

## Publishing Notes

Database credentials, storage locations, and the Immich version are represented
through `.env.example` placeholders.

## Skills Demonstrated

- Multi-service application deployment
- PostgreSQL and cache dependencies
- Digest-pinned container images
- Hardware device passthrough
- Persistent application data
- Environment-based configuration
