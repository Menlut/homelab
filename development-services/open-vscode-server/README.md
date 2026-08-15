# OpenVSCode Server

OpenVSCode Server provides a browser-accessible development environment hosted
inside Docker.

## Implementation Highlights

- Builds a small custom image that adds `openssh-client`.
- Uses an init process for cleaner child-process handling.
- Persists editor data, extensions, and workspace data outside the container.
- Mounts selected host and NAS paths for development access.
- Uses a connection token supplied through an environment variable.
- Adds a host-gateway entry for access to services running on the Docker host.

## Security and Sanitization

The real connection token, host paths, SSH material, and private workspace
filename are not published.

The `openvscode-ssh` directory is explicitly ignored because private SSH keys
must never be stored in this public repository.

## Skills Demonstrated

- Dockerfile customization
- Browser-based remote development
- Linux SSH tooling
- Bind mounts and persistent application data
- Secret and path sanitization
