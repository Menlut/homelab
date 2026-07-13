# Homelab

Documentation and sanitized Docker Compose deployments for my self-hosted
homelab.

This repository demonstrates hands-on experience with Linux administration,
Docker, container networking, monitoring, remote development, reverse
proxying, DNS, secure remote access, and self-hosted service management.

## Overview

The homelab runs containerized services on a Debian-based Docker host and is
organized by service category.

Administrative and internal services are accessed through a reverse proxy and
local DNS. For remote access, I chose Tailscale as a mesh VPN instead of
exposing services through router port forwarding.

This approach reduces direct internet exposure while allowing trusted devices
to securely access selected homelab services.

## Repository Structure

### [Infrastructure Services](infrastructure-services/)

Core networking, service discovery, reverse proxy, and container-management
components.

- [AdGuard Home](infrastructure-services/adguard/)
- [Caddy](infrastructure-services/caddy/)
- [Homepage](infrastructure-services/homepage/)
- [Portainer](infrastructure-services/portainer/)

### [Monitoring Services](monitoring-services/)

Host, container, and service-availability monitoring.

- [Beszel](monitoring-services/beszel/)
- [Uptime Kuma](monitoring-services/uptime-kuma/)

### [Media Services](media-services/)

Media management, automation, processing, playback, and request services.

- [ARR Stack](media-services/arr-stack/)
- [ARR FileFlows](media-services/arr-fileflows/)
- [Jellyfin and Seerr](media-services/player-seer/)

### [Development Services](development-services/)

Browser-based and remote development tools.

- [OpenVSCode Server](development-services/open-vscode-server/)

### [Game Servers](game-servers/)

Containerized dedicated multiplayer game servers.

- [Valheim Server](game-servers/valheim-server/)
- [Project Zomboid Server](game-servers/project-zomboid-server/)

## Technologies and Skills

- Debian Linux administration
- Docker and Docker Compose
- Reproducible containerized environments
- Container networking and persistent storage
- Reverse proxy configuration
- Local DNS and service discovery
- Secure remote access with a mesh VPN
- Host, container, and service monitoring
- Remote development environments
- Git-based version control and technical documentation
- Resource management and operational troubleshooting

## Publishing Approach

Only sanitized Docker Compose files, example environment files, and technical
documentation are published.

Runtime data, real environment files, credentials, tokens, logs, private
certificates, private network information, and deployment-specific
configuration are excluded.

The configurations in this repository are intended as documented examples and
may require environment-specific changes before deployment.