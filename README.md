# Homelab

Documentation and sanitized Docker Compose deployments for my self-hosted
homelab.

This repository demonstrates hands-on experience with Docker, Linux,
networking, monitoring, media automation, remote development, reverse
proxying, DNS, and dedicated game-server hosting.

## Repository Structure

### Infrastructure Services

- [AdGuard Home](infrastructure-services/adguard/)
- [Caddy](infrastructure-services/caddy/)
- [Homepage](infrastructure-services/homepage/)
- [Portainer](infrastructure-services/portainer/)

### Monitoring Services

- [Beszel](monitoring-services/beszel/)
- [Uptime Kuma](monitoring-services/uptime-kuma/)

### Media Services

- [ARR Stack](media-services/arr-stack/)
- [ARR FileFlows](media-services/arr-fileflows/)
- [Player and Seerr](media-services/player-seer/)

### Development Services

- [Open VS Code Server](development-services/open-vscode-server/)

### Game Servers

- [Valheim Server](game-servers/valheim-server/)
- [Project Zomboid Server](game-servers/project-zomboid-server/)

## Publishing Approach

Only sanitized Docker Compose files, example environment files, and technical
documentation are published.

Runtime data, real environment files, credentials, tokens, logs, private
certificates, and deployment-specific configuration are excluded.