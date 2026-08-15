# Caddy

Caddy is the central reverse proxy for internal homelab web services.

## Implementation Highlights

- Uses host networking for direct access to services running on the Docker host.
- Builds a custom Caddy image with the Cloudflare DNS module.
- Uses a reusable access-control snippet to restrict administrative services to
  trusted clients.
- Mounts the Caddyfile read-only.
- Persists Caddy data and runtime configuration outside the container.
- Uses explicit memory reservations and limits.

## Custom Docker Image

A Dockerfile is a set of instructions used to build a reusable Docker image.
Instead of manually installing software inside a running container, the image
defines those changes as code so the same container can be rebuilt
consistently.

The standard Caddy image does not include every DNS provider module. This
deployment requires the Cloudflare DNS module, so the included Dockerfile
extends the standard Caddy build using `xcaddy`.

The Dockerfile uses a multi-stage build:

1. A Caddy builder image compiles a Caddy binary with the Cloudflare DNS
   module.
2. The completed binary is copied into the standard Caddy runtime image.

This approach provides several benefits:

- The custom build is reproducible and documented in version control.
- The container can be rebuilt instead of being manually modified.
- Only the required extension is added to the standard Caddy runtime.
- The build process remains separate from the final runtime environment.

## Routing and Access Control

Caddy provides a centralized entry point for web applications and routes
requests to the appropriate internal service.

Not every service is given the same level of access.

Administrative interfaces use a reusable Caddy snippet that checks the source
address against an allowlist of trusted local and mesh-VPN clients. Requests
from clients outside that allowlist receive an HTTP `403 Forbidden` response.

Other services that are intentionally available to a broader set of trusted
users can use normal reverse-proxy routing without the administrative
allowlist.

This provides a second layer of access control at the reverse proxy in
addition to authentication provided by the individual applications.

The included `Caddyfile.example` demonstrates this design using example
domains, addresses, and upstream services.

## Domain and DNS

This deployment uses a domain controlled by the administrator as part of the
local DNS, HTTPS, and reverse-proxy workflow.

The custom Caddy image includes the Cloudflare DNS module used by the
certificate workflow. Provider credentials are supplied through environment
variables rather than stored directly in the Caddyfile.

The production Caddyfile, real domain names, DNS records, trusted client
addresses, provider credentials, and certificate data are not published.

## Skills Demonstrated

- Reverse proxy architecture
- HTTP and HTTPS service routing
- Source-based access control
- Reusable Caddy configuration
- Multi-stage Docker builds
- Custom Docker images
- DNS-based certificate integration
- Environment-based secret management
- Configuration and runtime-data separation