# AdGuard Home

AdGuard Home provides local DNS resolution and network-level filtering for
trusted homelab clients.

## Implementation Highlights

- Uses host networking so DNS can be served directly from the Docker host.
- Persists application work and configuration outside the container.
- Uses explicit memory reservations and limits.
- Participates in the internal hostname workflow used with Caddy.

## Publishing Notes

The live `adguard-work` and `adguard-conf` directories are intentionally
excluded. Runtime configuration can contain private DNS records, client
information, authentication data, and deployment-specific settings.

## Skills Demonstrated

- DNS administration
- Docker host networking
- Persistent storage
- Container resource management
- Separation of public configuration from private runtime state
