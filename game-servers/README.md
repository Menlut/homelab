# Game Servers

Containerized dedicated multiplayer game servers hosted as on-demand homelab
workloads.

## Services

| Service | Purpose |
|---|---|
| [Valheim Server](valheim-server/) | Dedicated Valheim server with persistent configuration and optional mod support. |
| [Project Zomboid Server](project-zomboid-server/) | Dedicated Project Zomboid server with persistent server files and configuration. |

## Network Approach

The containers publish the protocol ports required by each game. The homelab
does not rely on router port forwarding for trusted remote administration.

## Skills Demonstrated

- UDP/TCP service hosting
- Persistent game-server state
- Environment-based configuration
- On-demand container lifecycle management
- Resource allocation for memory-intensive workloads
