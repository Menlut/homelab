# Monitoring Services

Monitoring and availability services used to observe the Docker host,
containers, storage devices, hardware, and application endpoints.

## Services

| Service | Purpose |
|---|---|
| [Beszel](beszel/) | Host, container, storage, and hardware monitoring. |
| [Uptime Kuma](uptime-kuma/) | Service and endpoint availability monitoring. |

## Design Approach

Beszel provides host-level and container-level telemetry, while Uptime Kuma
focuses on whether services and endpoints are reachable.

The stack exposes host resources such as the Docker socket and selected
devices only where required by the monitoring tools.

## Skills Demonstrated

- Host and container observability
- Availability monitoring
- Docker socket integration
- Hardware and storage monitoring
- Linux device and capability management
- Secret separation for monitoring agents
