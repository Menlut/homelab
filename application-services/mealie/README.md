# Mealie

Mealie is deployed as a self-hosted recipe manager and meal planner backed by
PostgreSQL.

## Architecture

The application and database use a dedicated bridge network. The PostgreSQL
container also joins the external database administration network so it can be
managed through the centralized pgAdmin service.

## Implementation Highlights

- Binds the application to loopback for controlled reverse-proxy access.
- Keeps application data on an environment-defined storage path.
- Keeps live PostgreSQL data in a local persistent directory.
- Uses a database health check before starting the application.
- Disables public signup in the current deployment.
- Externalizes the base URL, household defaults, and database credentials.

## Skills Demonstrated

- PostgreSQL-backed web applications
- Docker bridge and external networks
- Health-check dependencies
- Loopback-only service exposure
- Persistent storage
- Secret management
