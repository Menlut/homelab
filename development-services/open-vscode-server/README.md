# OpenVSCode Server

OpenVSCode Server provides a browser-accessible development environment hosted
inside Docker.

## Implementation Highlights

- Builds a custom image based on the standard OpenVSCode Server image.
- Adds `openssh-client` for SSH-based development workflows.
- Uses an init process for cleaner child-process handling.
- Persists editor data, extensions, and workspace data outside the container.
- Mounts selected host and NAS paths for development access.
- Uses a connection token supplied through an environment variable.
- Adds a host-gateway entry for access to services running on the Docker host.

## Custom Docker Image

A Dockerfile defines the steps Docker uses to build an image.

The standard OpenVSCode Server image provides the browser-based development
environment, but this deployment also needs an SSH client. Rather than
installing that package manually every time the container is created, the
included Dockerfile creates a customized image with the required dependency
already installed.

The build:

1. Starts from the standard OpenVSCode Server image.
2. Temporarily switches to the root user to install `openssh-client`.
3. Cleans the package-manager cache to avoid keeping unnecessary build data.
4. Switches back to the normal `openvscode-server` user for runtime.

This makes the customization reproducible. If the container is removed or
moved to another compatible Docker host, the required environment can be
rebuilt directly from the Dockerfile rather than recreated manually.

It also keeps the customization documented in version control alongside the
Compose configuration that uses it.

## Dockerfile vs. Docker Compose

The two files serve different purposes:

- `Dockerfile.openvscode` defines **what is inside the custom image**.
- `compose.yaml` defines **how a container created from that image runs**,
  including ports, volumes, environment variables, and startup options.

Keeping these responsibilities separate makes the deployment easier to
understand, reproduce, and maintain.

## Security and Sanitization

The real connection token, host paths, SSH material, and private workspace
filename are not published.

The `openvscode-ssh` directory is explicitly ignored because private SSH keys
must never be stored in this public repository.

## Skills Demonstrated

- Dockerfile customization
- Custom image creation
- Reproducible development environments
- Linux package management
- Non-root container execution
- Browser-based remote development
- Bind mounts and persistent application data
- Secret and path sanitization