# Portainer

Portainer provides a web-based interface for viewing and administering the
local Docker environment.

## Implementation Highlights

- Persists application data outside the container.
- Connects to the local Docker socket using a read-only mount.
- Enables `no-new-privileges`.
- Publishes both the legacy HTTP and Portainer HTTPS interfaces.
- Applies explicit memory reservations and limits.

## Security Notes

Docker socket access should be treated as privileged host access. Portainer is
therefore intended for trusted administrative access rather than public
exposure.

## Skills Demonstrated

- Docker administration
- Persistent container state
- Host resource integration
- Administrative-interface security
- Container resource management
