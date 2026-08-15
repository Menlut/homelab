# Homelab

Documentation and sanitized Docker Compose deployments for my self-hosted
homelab.

This repository demonstrates hands-on experience with Linux administration,
Docker, container networking, monitoring, remote development, reverse
proxying, DNS, secure remote access, local AI services, databases, and
self-hosted application management.

## Overview

The homelab runs containerized services on a Debian-based Docker host and is
organized by service category.

Administrative and internal services are accessed through a reverse proxy and
local DNS. For remote access, I chose Tailscale as a mesh VPN instead of
exposing administrative services through router port forwarding.

This approach reduces direct internet exposure while allowing trusted devices
to securely access selected homelab services.

## Repository Structure

### [Infrastructure Services](infrastructure-services/)

Core DNS, reverse proxy, dashboard, container-management, and database
administration services.

- [AdGuard Home](infrastructure-services/adguard/)
- [Caddy](infrastructure-services/caddy/)
- [Homepage](infrastructure-services/homepage/)
- [Portainer](infrastructure-services/portainer/)
- [pgAdmin](infrastructure-services/database-admin/)

### [Monitoring Services](monitoring-services/)

Host, container, hardware, and service-availability monitoring.

- [Beszel](monitoring-services/beszel/)
- [Uptime Kuma](monitoring-services/uptime-kuma/)

### [Media Services](media-services/)

Media automation, processing, playback, requests, and photo management.

- [ARR Stack](media-services/arr-stack/)
- [ARR FileFlows](media-services/arr-fileflows/)
- [Jellyfin and Seerr](media-services/player-seer/)
- [Immich](media-services/immich/)

### [Development Services](development-services/)

Browser-based and remote development tooling.

- [OpenVSCode Server](development-services/open-vscode-server/)

### [AI Services](ai-services/)

Local model-serving infrastructure used by applications on the homelab.

- [Ollama](ai-services/ollama/)

### [Application Services](application-services/)

Self-hosted applications with their supporting databases and integrations.

- [Mealie](application-services/mealie/)
- [Wardrowbe](application-services/wardrowbe/)

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
- Host, container, hardware, and service monitoring
- PostgreSQL and Redis-backed applications
- Local AI model serving
- Hardware acceleration and Linux device passthrough
- Remote development environments
- Git-based version control and technical documentation
- Resource management and operational troubleshooting

## Publishing Approach

Only sanitized Docker Compose files, example environment files, Dockerfiles,
and technical documentation are published.

Runtime data, real environment files, credentials, tokens, logs, private
certificates, SSH material, private network information, and deployment-specific
configuration are excluded.

The configurations in this repository document the current homelab design and
may require environment-specific changes before deployment.
