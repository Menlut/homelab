# Homepage

Homepage provides a centralized dashboard for accessing and monitoring
homelab services.

## Implementation Highlights

- Publishes the dashboard on a dedicated host port.
- Persists dashboard configuration and custom icons outside the container.
- Mounts the Docker socket read-only for container-aware integrations.
- Adds a host-gateway entry so the container can reach host services.
- Enables `no-new-privileges`.
- Uses explicit memory reservations and limits.

## Security Notes

The Docker socket is a sensitive host interface even when mounted read-only.
Live Homepage configuration is excluded because widgets and service
definitions may contain private hostnames, URLs, or API credentials.

## Skills Demonstrated

- Dashboard integration
- Docker metadata integration
- Container-to-host networking
- Security-conscious container settings
- Runtime-data separation
