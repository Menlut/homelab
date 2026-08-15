# Development Services

Browser-based and remote development tooling hosted inside the homelab.

## Services

| Service | Purpose |
|---|---|
| [OpenVSCode Server](open-vscode-server/) | Browser-accessible development environment with SSH client support. |

## Design Approach

The development container keeps editor state and workspace data persistent,
mounts selected host storage, and protects the web interface with a connection
token supplied through an environment variable.

## Skills Demonstrated

- Custom Docker images
- Remote development environments
- Persistent workspaces
- Host/container filesystem integration
- Environment-based authentication
