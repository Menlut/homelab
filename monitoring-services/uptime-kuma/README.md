# Uptime Kuma

Uptime Kuma provides service and endpoint availability monitoring for the
homelab.

## Implementation Highlights

- Persists monitoring state outside the container.
- Mounts the Docker socket read-only for Docker-aware monitoring.
- Enables `no-new-privileges`.
- Uses explicit memory reservations and limits.

## Security Notes

The Docker socket is a sensitive host interface and is exposed only for
container-aware monitoring. The dashboard is intended for trusted
administrative access.

## Skills Demonstrated

- Availability monitoring
- Docker-aware observability
- Persistent application state
- Container security options
- Resource management
