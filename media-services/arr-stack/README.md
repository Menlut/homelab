# ARR Stack

This stack combines Gluetun, qBittorrent, Prowlarr, Sonarr, Radarr, Bazarr, a
Gluetun web interface, and a qBittorrent port-sync service.

## Architecture

Gluetun provides the shared network namespace for the other ARR containers.
qBittorrent and the automation services use `network_mode:
service:arr-gluetun`, centralizing their network path through the VPN
container.

Health checks and conditional dependencies are used so dependent services wait
for Gluetun, and the port-sync service also waits for qBittorrent.

## Components

| Service | Role |
|---|---|
| Gluetun | VPN gateway and shared network namespace |
| Gluetun Web UI | Internal status/control interface |
| qBittorrent | Download client |
| Port Sync | Synchronizes the forwarded VPN port with qBittorrent |
| Prowlarr | Indexer management |
| Sonarr | TV automation |
| Radarr | Movie automation |
| Bazarr | Subtitle automation |

## Security and Sanitization

WireGuard credentials and qBittorrent credentials are environment variables
and are represented only by placeholders in `.env.example`.

The Gluetun control API is configured without authentication for the internal
shared-network workflow. It should remain isolated from untrusted clients.

## Skills Demonstrated

- Docker network namespaces
- VPN container routing
- Linux network capabilities and TUN devices
- Health checks and dependency ordering
- Secret management
- Multi-service media automation
- Resource management
