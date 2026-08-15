# Media Services

Containerized services for media automation, processing, playback, request
management, and photo management.

## Services

| Stack | Purpose |
|---|---|
| [ARR Stack](arr-stack/) | VPN-routed download and media automation services. |
| [ARR FileFlows](arr-fileflows/) | Media processing with Intel hardware acceleration. |
| [Jellyfin and Seerr](player-seer/) | Media playback and request management. |
| [Immich](immich/) | Self-hosted photo and video management. |

## Design Approach

Selected ARR services share Gluetun's network namespace so their network
traffic follows the VPN container. FileFlows, Jellyfin, and Immich receive
access to Intel graphics hardware where the current deployment uses hardware
acceleration.

Persistent configuration, databases, cache data, and media storage remain
outside disposable application containers.

## Skills Demonstrated

- Multi-container orchestration
- Shared network namespaces
- VPN-routed application traffic
- Health-check based dependencies
- Hardware device passthrough
- PostgreSQL-backed applications
- Persistent media storage
- Resource allocation
- Environment-based secret management
