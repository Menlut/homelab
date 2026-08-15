# pgAdmin

pgAdmin provides a centralized administrative interface for PostgreSQL
databases used by other homelab applications.

## Implementation Highlights

- Stores pgAdmin state in a named Docker volume.
- Binds the web interface to loopback so it can be reached through the
  homelab's controlled access path instead of being broadly exposed.
- Connects to an external Docker network used by PostgreSQL-backed
  applications.
- Keeps the administrator email and password in environment variables.

## Shared Database Network

Applications that need centralized database administration can attach their
PostgreSQL container to the external `database-admin-network`. pgAdmin can then
reach those databases without publishing their database ports on the host.

## Skills Demonstrated

- PostgreSQL administration
- Docker named volumes
- External Docker networks
- Loopback-only service binding
- Credential externalization
