# Beszel

Beszel provides lightweight host and container monitoring through a hub and a
host-level agent.

## Components

| Container | Role |
|---|---|
| `beszel-hub` | Stores and presents monitoring data. |
| `beszel-agent` | Collects Docker, GPU, storage, and host metrics. |

## Implementation Highlights

- Persists hub and agent data outside the containers.
- Uses host networking for the agent.
- Provides the agent read-only access to the Docker socket and monitored
  storage.
- Exposes selected GPU and storage devices for hardware metrics.
- Adds the Linux capabilities required by the agent.
- Applies separate memory limits to the hub and agent.

## Security Notes

Agent authentication values are supplied through environment variables in the
public Compose file. Real keys and tokens are not published.

The agent has elevated host visibility, so its device, capability, and Docker
socket access are treated as meaningful security boundaries.

## Skills Demonstrated

- Host observability
- Docker monitoring
- Linux capabilities
- Device passthrough
- GPU and SMART monitoring
- Secret management
